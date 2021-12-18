# 如何使用 express-validator 验证输入字段中的输入是否具有 base 32 编码字符串？

> 原文:[https://www . geeksforgeeks . org/if-in-input-field-has-base-32-encoded-string-use-express-validator/](https://www.geeksforgeeks.org/how-to-validate-if-input-in-input-field-has-base-32-encoded-string-using-express-validator/)如何验证

在 HTML 表单中，我们经常需要不同类型的验证。验证现有电子邮件、验证密码长度、验证确认密码、验证为仅允许整数输入，这些都是验证的一些示例。如果在某个输入字段中只允许 32 进制编码的字符串，即不允许任何其他形式的不构成 32 进制编码字符串的字符串。我们还可以使用 express-validator 中间件验证这些输入字段，使其只接受 base 32 编码的字符串。

**安装快递验证器的命令:**

```
npm install express-validator
```

**使用快递验证器实现逻辑的步骤:**

*   Install the courier verifier middleware.
*   Create a validator.js file to encode all validation logic.
*   Validate the input by validateInputField: check (enter the field name) and chain on the validation isBase32 () with "."
*   Use the validation name (validateInputField) in the route as the middleware and as a validation array.
*   Destruct the' validationresult' function from express-validator and use it to find any errors.
*   If an error occurs, redirect to the same page where the error message is sent.
*   If the error list is empty, the user is allowed to access subsequent requests.

**注意:**这里我们使用本地或自定义数据库来实现逻辑，同样的步骤也可以在 MongoDB 或 MySql 这样的常规数据库中实现逻辑。

**示例:**此示例说明了如何验证输入字段，使其只接受 32 进制编码的字符串。

**文件名–index . js**

## 【JavaScript】

```
const express = require('express')
const bodyParser = require('body-parser')
const {validationResult} = require('express-validator')
const repo = require('./repository')
const { validateBase32Data } = require('./validator')
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
  '/data',
  [validateBase32Data],
  async (req, res) => {
    const errors = validationResult(req)
    if(!errors.isEmpty()){
      return res.send(formTemplet({errors}))
    }
    const {name, base32data} = req.body
    await repo.create({
      name,
      base32data
    })
 res.send('<h2>Base 32 data decoded and Stored'
    + ' successfully in the database</h2>')
})

// Server setup
app.listen(port, () => {
  console.log(`Server start on port ${port}`)
})
```

**Filename–repository . js:**该文件包含创建本地数据库并与之交互的所有逻辑。

## JavaScript

```
// Importing node.js file system module
const fs = require('fs')
const base32Decode = require('base32-decode')
var ab2str = require('arraybuffer-to-string')

class Repository {
   constructor(filename) {

    // The filename where datas are going to store
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
  async getAll(){
    return JSON.parse(
      await fs.promises.readFile(this.filename, {
        encoding : 'utf8'
      })
    )
  }

  // Create new record
  async create(attrs){
    const records = await this.getAll()

    // Decoding base 32 encoded string
    const arrayBuff = base32Decode(
            attrs.base32data, 'RFC4648')

    // The uint8 array raw form of decoded string
    const uint8 = new Uint8Array(arrayBuff)

    // The uint8 array raw form to string
    const data = ab2str(uint8)
    const record = {
      name:attrs.name,
      data
    }
    records.push(record)
    await fs.promises.writeFile(
      this.filename,
      JSON.stringify(records, null, 2)  
    )
    return record
  }
}

// The 'datastore.json' file created at runtime
// and all the information provided via signup form
// store in this file in JSON format.
module.exports = new Repository('datastore.json')
```

**文件名-表单. js:** 该文件包含显示 HTML 表单的逻辑。

## JavaScript

```
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
        <link rel='stylesheet'
href='https://cdnjs.cloudflare.com/ajax/libs/bulma/0.9.0/css/bulma.min.css'>
        <style>
          div.columns{
            margin-top: 100px;
          }
          .button{
            margin-top : 10px
          }
        </style>
      </head>
      <body>
        <div class='container'>
          <div class='columns is-centered'>
            <div class='column is-5'>
              <form action='/data' method='POST'>           
                <div>
                  <div>
                    <label class='label' id='name'>Name</label>
                  </div>
                  <input class='input' type='text' name='name'
                  placeholder='Submitted By' for='name'>
                </div>
                <div>
                  <div>
                    <label class='label' id='base32data'>
                      Base 32 data
                    </label>
                  </div>
                  <input class='input' type='text'
                         name='base32data'
                         placeholder='Base 32 Encode data'
                         for='citizen'>
                  <p class="help is-danger">
                    ${getError(errors, 'base32data')}
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

**Filename–validator . js:**该文件包含所有的验证逻辑(验证输入字段只接受基本编码 32 字符串的逻辑)。

## JavaScript

```
const {check} = require('express-validator')
const repo = require('./repository')
module.exports = {

  validateBase32Data : check('base32data')

    // To delete leading and triling space
    .trim()

    // Validate input field to accept only base32 string
    .isBase32()

    // Custom message
    .withMessage('Must be a Base 32 encoded string')
}
```