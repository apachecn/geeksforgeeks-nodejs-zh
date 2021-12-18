# 如何仅使用 express-validator 验证输入字段中的输入是否有全角字符串？

> 原文:[https://www . geesforgeks . org/如何验证输入字段中的输入是否具有全宽字符串-仅使用快速验证器/](https://www.geeksforgeeks.org/how-to-validate-if-input-in-input-field-has-full-width-string-only-using-express-validator/)

在 HTML 表单中，我们经常需要不同类型的验证。验证现有电子邮件、验证密码长度、验证确认密码、验证为仅允许整数输入，这些都是验证的一些示例。在某个输入字段中，只允许全角字符串。我们还可以使用 express-validator 中间件验证这些输入字段，使其只接受全角字符串。

**安装快速验证器的命令:**

```js
npm install express-validator

```

**使用快速验证器实现逻辑的步骤:**

*   安装快速验证中间件。
*   创建一个 validator.js 文件来编码所有的验证逻辑。
*   通过验证输入验证输入:检查(输入字段名)和验证链是带“.”的宽度()
*   在路由中使用验证名称(validateInputField)作为一个中间件，作为一个验证数组。
*   从快速验证器中析构“验证结果”函数，用它来查找任何错误。
*   如果发生错误，重定向到传递错误信息的同一页。
*   如果错误列表为空，则允许用户访问后续请求。

**注意:**这里我们使用本地或自定义数据库来实现逻辑，同样的步骤也可以在 MongoDB 或 MySql 这样的常规数据库中实现逻辑。

**示例:**此示例说明了如何验证输入字段以仅允许全角字符串。

**文件名–index . js**

```js
const express = require('express')
const bodyParser = require('body-parser')
const {validationResult} = require('express-validator')
const repo = require('./repository')
const { validateMessage } = require('./validator')
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
  [validateMessage],
  async (req, res) => {
    const errors = validationResult(req)

    if(!errors.isEmpty()) {
      return res.send(formTemplet({errors}))
    }

    const {name, msg} = req.body

    // New record
    await repo.create({
      'Name':name,
      'Message':msg
    })
    res.send(
'<strong>Message send to admin successfully</strong>')
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

**Filename–form . js:**该文件包含显示表单的逻辑。

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
              <label class='label' id='msg'>
                Message to admin
              </label>
            </div>
            <input class='input' type='text' name='msg' 
              placeholder='Message in full width string'
              for='msg'>
            <p class="help is-danger">
              ${getError(errors, 'msg')}
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

**Filename–validator . js:**该文件包含所有验证逻辑(验证输入字段只允许全角字符串的逻辑)。

```js
const {check} = require('express-validator')
const repo = require('./repository')
module.exports = {

  validateMessage : check('msg')

    // To delete leading and triling space
    .trim()

    // Validate message to accept only
    // the full width string
    .isFullWidth()

    // Custom message
    .withMessage('Must be a full width string')   
}
```

**在线将普通字符串转换为全宽字符串:**

![](img/638e80c42b87d17b101db7541df9cc95.png)

在线将普通字符串转换为全角字符串

**文件名–package . JSON**

![](img/bbbf3bf8b231c5f01f5ac9384cc87b83.png)

package.json 文件

**数据库:**

![](img/6690375e4f1f58663f3cddc823ad5256.png)

数据库ˌ资料库

**输出:**

![](img/88450c44bb12dee77c08b93509167f0b.png)

当消息输入字段不包含全角字符串时，尝试提交表单数据

![](img/a7f651d9f5118ca9315817dc3838f8f4.png)

尝试提交消息输入字段不包含全角字符串的表单数据时的响应

![](img/9271c1476c01a113d63f36b13dc19ecf.png)

当消息输入字段包含全宽字符串时，尝试提交表单数据

![](img/1cd83d487aaaf0b903ca3bdd4cbdbd5a.png)

尝试提交消息输入字段包含全角字符串的表单数据时的响应

**成功提交表单后的数据库**

![](img/f8a8d80bd926c9357eecedd3b37d3df9.png)

成功提交表单后的数据库

**注意:**我们在 form.js 文件中使用了一些布尔玛类(CSS 框架)来设计内容。