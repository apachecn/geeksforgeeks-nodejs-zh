# 如何使用 express-validator 验证输入字段中的输入是否必须包含种子词？

> 原文:[https://www . geeksforgeeks . org/if-input-in-input-field-must-contains-a-seed-word-use-express-validator/](https://www.geeksforgeeks.org/how-to-validate-if-input-in-input-field-must-contains-a-seed-word-using-express-validator/)

在 HTML 表单中，我们经常需要不同类型的验证。验证现有电子邮件、验证密码长度、验证确认密码、验证为仅允许整数输入，这些都是验证的一些示例。在某个输入字段中，我们经常需要验证输入，以便它必须包含一个种子词，即输入可以是任何东西(任何字符串)，但必须包含一个特定的词(种子词)。我们还可以使用 express-validator 中间件验证这些输入字段，以便只接受那些包含种子词的值。

**安装快速验证器的命令:**

```js
npm install express-validator
```

**使用快速验证器实现逻辑的步骤:**

*   安装快速验证中间件。
*   创建一个 validator.js 文件来编码所有的验证逻辑。
*   通过验证输入验证输入:检查(输入字段名)和验证链是否包含带“.”的(种子)
*   如果要忽略区分大小写，请添加 options 对象参数{ignoreCase:true}。默认情况下，忽略设置为真。
*   在路由中使用验证名称(validateInputField)作为一个中间件，作为一个验证数组。
*   从快速验证器中析构“验证结果”函数，用它来查找任何错误。
*   如果发生错误，重定向到传递错误信息的同一页。
*   如果错误列表为空，则允许用户访问后续请求。

**注意:**这里我们使用本地或自定义数据库来实现逻辑，同样的步骤也可以在 MongoDB 或 MySql 这样的常规数据库中实现逻辑。

**示例:**此示例说明了如何验证输入字段，以仅允许包含种子词的值。

**文件名–index . js**

```js
const express = require('express')
const bodyParser = require('body-parser')
const {validationResult} = require('express-validator')
const repo = require('./repository')
const { validatePlayerName } = require('./validator')
const formTemplet = require('./form')

const app = express()
const port = process.env.PORT || 3000

// The body-parser middleware to parse form data
app.use(bodyParser.urlencoded({extended : true}))

// Get route to display HTML form
app.get('/', (req, res) => {
  res.send(formTemplet({}))
})

// Post route to handle form submission logic and 
app.post(
  '/info',
  [validatePlayerName],
  async (req, res) => {
    const errors = validationResult(req)

    if(!errors.isEmpty()) {
      return res.send(formTemplet({errors}))
    }

    const {name, dept, event, pname} = req.body

    // New record
    await repo.create({
      'Name':name,
      'Department':dept,
      'Event Name':event,
      'Player Name':pname,
    })
    res.send(
'<strong>Registered Successfully for the event!!</strong>')
})

// Server setup
app.listen(port, () => {
  console.log(`Server start on port ${port}`)
})
```

**Filename–repository . js:**该文件包含创建本地数据库并与之交互的所有逻辑。

```js
// Importing node.js file system module 
const fs = require('fs')

class Repository {

  constructor(filename) {

    // Filename where datas are going to store
    if(!filename) {
      throw new Error(
'Filename is required to create a datastore!')
    }

    this.filename = filename

    try {
      fs.accessSync(this.filename)
    } catch(err) {

      // If file not exist it is created
      // with empty array
      fs.writeFileSync(this.filename, '[]')
    }
  }

  // Get all existing records
  async getAll() {
    return JSON.parse(
      await fs.promises.readFile(this.filename, {
        encoding : 'utf8'
      })
    )
  }

  // Create new record
  async create(attrs) {
    // Fetch all existing records
    const records = await this.getAll()

    // All the existing records with new 
    // record push back to database
    records.push(attrs)
    await fs.promises.writeFile(
      this.filename,
      JSON.stringify(records, null, 2)   
    )
    return attrs
  }
}

// The 'datastore.json' file created at runtime 
// and all the information provided via signup form
// store in this file in JSON formet.
module.exports = new Repository('datastore.json')
```

**Filename–form . js:**该文件包含显示表单提交数据的逻辑。

```js
const getError = (errors, prop) => {
  try {
    return errors.mapped()[prop].msg
  } catch (error) {
    return ''
  } 
}

module.exports = ({errors}) => {
  return `
<!DOCTYPE html>
<html>

<head>
  <link rel='stylesheet' href=
'https://cdnjs.cloudflare.com/ajax/libs/bulma/0.9.0/css/bulma.min.css'>
  <style>
    div.columns {
      margin-top: 100px;
    }

    .button {
      margin-top: 10px
    }
  </style>
</head>

<body>
  <div class='container'>
    <div class='columns is-centered'>
      <div class='column is-5'>
        <form action='/info' method='POST'>
          <div>
            <div>
              <label class='label' id='name'>
                Name
              </label>
            </div>
            <input class='input' type='text' 
              name='name' placeholder='Vinit singh'
              for='name'>
          </div>
          <div>
            <div>
              <label class='label' id='dept'>
                Department
              </label>
            </div>
            <input class='input' type='text' 
              name='dept' placeholder='Department' 
              for='dept'>
          </div>
          <div>
            <div>
              <label class='label' id='event'>
                Event Name
              </label>
            </div>
            <input class='input' type='text' 
              name='event' placeholder='Event Name' 
              for='event'>
          </div>
          <div>
            <div>
              <label class='label' id='pname'>
                Player Name
              </label>
            </div>
            <input class='input' type='text' name='pname' 
              placeholder=
              "Player Name must contains the word 'jolite'"
              for='pname'>
            <p class="help is-danger">
              ${getError(errors, 'pname')}
            </p>
          </div>
          <div>
            <button class='button is-primary'>
              Submit
            </button>
          </div>
        </form>
      </div>
    </div>
  </div>
</body>

</html>
  `
}
```

**Filename–validator . js:**该文件包含所有验证逻辑(验证输入字段的逻辑，只允许包含种子字的值)。

```js
const {check} = require('express-validator')
const repo = require('./repository')
module.exports = {

  validatePlayerName : check('pname')

    // To delete leading and triling space
    .trim()

    // Validate player name to accept only
    // the string that contains the word 'jolite'
    // ignorecase is an optional attribute 
    // and it is by default set to false if 
    // ignorecase attribute set to be true, 
    // it ignores the case sensitivity 
    // of the required seed word
    .contains('jolite', { ignoreCase: true})

    // Custom message
    .withMessage(
"Player Name must contains the word 'jolite'")   
}
```

**文件名–package . JSON**

![](img/bbbf3bf8b231c5f01f5ac9384cc87b83.png)

package.json 文件

**数据库:**

![](img/363490d7cf2de358622ebc7cb965dc3e.png)

数据库ˌ资料库

**输出:**

![](img/4f6bfa5c2b8c4773505acb5db07b247d.png)

当玩家姓名输入字段不包含种子词“jolite”时，尝试提交表单数据

![](img/83fd62924a33d676558273e60e61b913.png)

当试图提交玩家姓名输入字段不包含种子词“jolite”的表单数据时的响应

![](img/bbd89593f91cfe2e7953b37c9e2ebc32.png)

当玩家姓名输入字段包含种子词“jolite”时，尝试提交表单数据

![](img/213dc25c4c4c8d8f4e76f5c2c5bd4483.png)

当玩家姓名输入字段包含种子词“jolite”(大写字母)时，尝试提交表单数据

![](img/560498065397d844f6955d5f6155b4fa.png)

当试图提交玩家姓名输入字段包含种子词“jolite”的表单数据时的响应

**成功提交表单后的数据库:**

![](img/4c33aeb5721e6dab93cfeffc26081190.png)

成功提交表单后的数据库

**注意:**我们在 form.js 文件中使用了一些布尔玛类(CSS 框架)来设计内容。