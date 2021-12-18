# 使用 Passportjs 和 passport-local-mongose 进行 Node.js 认证

> 原文:[https://www . geesforgeks . org/node-js-authentication-use-passportjs-and-passport-local-mongose/](https://www.geeksforgeeks.org/node-js-authentication-using-passportjs-and-passport-local-mongoose/)

Passport 是节点的认证中间件。它被设计为服务于一个单一的目的，即验证请求。将用户密码作为原始字符串存储在数据库中是不切实际的，但将密码散列后存储到数据库中是一种很好的做法。但是使用 passport-local-mongose，您不必使用加密模块对密码进行哈希运算，passport-local-mongose 将为您做一切事情。如果使用 passport-local-mongose，这个模块将在数据库中自动生成盐和散列字段。您将没有密码字段，而是有盐和散列。

**为什么需要加盐密码**

如果用户简单地散列他们的密码，并且如果数据库中的两个用户具有相同的密码，那么他们将具有相同的散列。如果任何一个密码被黑客攻击，那么黑客可以使用相同的密码访问每个帐户，因为拥有相同密码的用户将拥有相同的哈希字段。
所以在我们散列它之前，我们预先准备一个唯一的字符串。不是秘密，只是一些独特的东西。所以每种盐的杂烩是完全不同的。

**执行操作的步骤**

首先让我们生成一个快速应用程序，然后安装所需的模块

```
> npm install passport passport-local mongoose passport-local-mongoose --save

```

**1。首先创建如下目录结构:**

```
--model
----user.js
--route
----user.js
--app.js

```

**2。创建定义用户模式的模型/用户. js 文件**

```
// importing modules
var mongoose = require('mongoose');
var Schema = mongoose.Schema;
var passportLocalMongoose = require('passport-local-mongoose');

var UserSchema = new Schema({   
    email: {type: String, required:true, unique:true},
    username : {type: String, unique: true, required:true},
});

// plugin for passport-local-mongoose
UserSchema.plugin(passportLocalMongoose);

// export userschema
 module.exports = mongoose.model("User", UserSchema);
```

请注意，在这个模式中，我们没有像平时那样添加任何密码字段。这是因为护照本地猫鼬不需要。在这里，我们没有添加任何方法来散列我们的密码或比较我们的密码，因为护照本地猫鼬会为我们做所有这些。

**3。在 app.js 中配置 Passport/Passport-Local:**

首先，在 app.js 中，您必须初始化 passport

```
app.use(passport.initialize());
app.use(passport.session());
```

passport 将保持持久的登录会话。为了使持久会话在 passport 中工作，必须将经过身份验证的用户序列化到会话中，并在发出后续请求时反序列化。带着护照-本地猫鼬

```
passport.serializeUser(User.serializeUser());
passport.deserializeUser(User.deserializeUser());
```

如果您没有在 passport 中使用 passport-local-mongose，序列化和反序列化代码可能会略有不同。

现在我们必须确定护照的策略。对于护照本地猫鼬的代码是

```
const User = require('./models/user');

const LocalStrategy = require('passport-local').Strategy;
passport.use(new LocalStrategy(User.authenticate()));
```

如果您只使用 passport 而不使用 passport-local-mongose，则本地策略可能会有很大不同(即)您必须编写代码来比较密码和所有密码。这里就这 2 行就够了

**4。创建路线/用户. js 文件:**

首先导入用户模式以及其他必要的模块

```
// importing modules 
const express = require('express'); 
const router = express.Router(); 

// importing User Schema 
const User = require('../model/user');
```

**5。用于注册:**

现在注册代码应该是

```
router.post('/login', function(req, res) {

    Users=new User({email: req.body.email, username : req.body.username});

          User.register(Users, req.body.password, function(err, user) {
            if (err) {
              res.json({success:false, message:"Your account could 
              not be saved. Error: ", err}) 
            }else{
              res.json({success: true, message: "Your account has 
               been saved"})
            }
          });
});
```

在上面的代码中，我们没有在新用户中定义密码。相反，我们对用户使用密码。Register()是一个护照-本地-猫鼬函数。现在，如果您检查数据库中保存的用户，它将如下所示

```
{
    "_id" : ObjectId("5ca8b66535947f4c1e93c4f1"),
    "username" : "username you gave",
    "email" : "email you gave",
    "salt" : "4c8f6e009c4523b23553d9479e25254b266c3b7dd2dbc6d4aaace01851c9687c",
    "hash" : "337de0df58406b25499b18f54229b9dd595b70e998fd02c7866d06d2a6b25870d23650
cdda829974a46e3166e535f1aeb6bc7ef182565009b1dcf57a64205b5548f6974b77c2e3a3c6aec5360d
55f9fcd3ffd6fb99dce21aab021aced72881d3720f6a0975bfece4922282bb748e0412955e0afa2fb8c9
f5055cac0fb01a4a2288af2ce2a6563ed9b47852727749c7fe031b6b7fbb726196dbdfeeb6766d5cba6a
055f66eeacce685daef8b6c1aed0108df511c92d49150efb6473ee71c5149dd06bfb4f73cb60f9815af0
1e02fde8d8ed822bb3a55f040237cf80de0b1534de6bbafcb53f882c6eb03de4b4aa307828974eb51261
661efb5155e68ad0e593c0f5fab7d690c2257df4369e9d5ac7e2fc93b5b014260c6f8fbb01034b3f85ec
f11e086e9bf860f959d0e2104a1f825d286c99d3fc6f62505d1fde8601345c699ea08dcc071e5547835c
16957d3830998a10762ebd143dc557d6a96e4b88312e1e4c51622fef3939656c992508e47ddc148696df
3152af76286d636d4814a0dc608f72cd507c617feb77cbba36c5b017492df5f28a7a3f3b7881caf6fb4a
9d6231eca6edbeec4eb1436f1e45c27b9c2bfceccf3a9b42840f40c65fe499091ba6ebeb764b5d815a43
d73a888fdb58f821fbe5f7d92e20ff8d7c98e8164b4f10d5528fddbcc7737fd21b12d571355cc605eb36
21f5f266f8e38683deb05a6de43114",
    "__v" : 0
}

```

您可以注意到根本没有密码字段，而是 passport-local-mongose 为您创建了 salt 和 hash，您也不必在模式中定义 salt 和 hash 字段。护照-本地-猫鼬将保持你的用户名唯一，即如果用户名已经存在，它会给“用户存在错误”。

**5。登录方式:**

现在登录

```
userController.doLogin = function(req, res) {
  if(!req.body.username){
    res.json({success: false, message: "Username was not given"})
  } else {
    if(!req.body.password){
      res.json({success: false, message: "Password was not given"})
    }else{
      passport.authenticate('local', function (err, user, info) { 
         if(err){
           res.json({success: false, message: err})
         } else{
          if (! user) {
            res.json({success: false, message: 'username or password incorrect'})
          } else{
            req.login(user, function(err){
              if(err){
                res.json({success: false, message: err})
              }else{
                const token =  jwt.sign({userId : user._id, 
                   username:user.username}, secretkey, 
                      {expiresIn: '24h'})
                res.json({success:true, message:"Authentication 
                    successful", token: token });
              }
            })
          }
         }
      })(req, res);
    }
  }
};
```

**6。重置或更改密码:**

您可以使用 passport-local-mongose 中的 2 个简单功能重置或更改密码。它们是**设置密码功能和更改密码功能**。通常，当用户忘记密码时使用设置密码，当用户想要更改密码时使用更改密码。

setPassword 的代码是

```
// user is your result from userschema using mongoose id
 user.setPassword(req.body.password, function(err, user){ ..

```

用于更改密码

```
// user is your result from userschema using mongoose id
  user.changePassword(req.body.oldpassword, req.body.newpassword, function(err) ...

```

您可以在路由器文件中直接调用它们