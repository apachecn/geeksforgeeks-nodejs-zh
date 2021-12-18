# 如何使用快速验证器验证输入字段中的输入是否有 ASCII 字符？

> 原文:[https://www . geesforgeks . org/如何使用快速验证器验证输入字段中的输入是否包含 ascii 字符/](https://www.geeksforgeeks.org/how-to-validate-if-input-in-input-field-has-ascii-characters-using-express-validator/)

在 HTML 表单中，我们经常需要不同类型的验证。验证现有电子邮件、验证密码长度、验证确认密码、验证为仅允许整数输入，这些都是验证的一些示例。在某个输入字段中，只允许使用 ASCII 字符，即不允许使用任何非 Ascii 字符(例如:我们还可以使用 express-validator 中间件验证这些输入字段，使其只接受 ASCII 字符。

**安装快速验证器的命令:**

```
npm install express-validator
```

**使用快速验证器实现逻辑的步骤:**

*   安装快速验证中间件。
*   创建一个 validator.js 文件来编码所有的验证逻辑。
*   通过验证输入验证输入:在带有“.”的验证 isAscii()上检查(输入字段名)和链
*   在路由中使用验证名称(validateInputField)作为一个中间件，作为一个验证数组。
*   从快速验证器中析构“验证结果”函数，用它来查找任何错误。
*   如果发生错误，重定向到传递错误信息的同一页。
*   如果错误列表为空，则允许用户访问后续请求。

**注意:**这里我们使用本地或自定义数据库来实现逻辑，同样的步骤也可以在 MongoDB 或 MySql 这样的常规数据库中实现逻辑。

**示例:**此示例说明了如何验证输入字段以仅接受 ascii 字符。

**文件名–index . js**

```
const express = require('express')
const bodyParser = require('body-parser')
const {validationResult} = require('express-validator')
const repo = require('./repository')
const { validateAsciiCharacters } = require('./validator')
const formTemplet = require('./form')

const app = express()
const port = process.env.PORT || 3000

// The body-parser middleware to parse form data
app.use(bodyParser.urlencoded({extended : true}))

// Get route to display HTML form to submit ascii text
app.get('/', (req, res) => {
  res.send(formTemplet({}))
})

// Post route to handle form submission logic and 
app.post(
  '/register/ascii',
  [validateAsciiCharacters],
  async (req, res) => {
    const errors = validationResult(req)
    if(!errors.isEmpty()){
      return res.send(formTemplet({errors}))
    }
    const {submittedBy, ascii} = req.body
    await repo.create({submittedBy, ascii})
    res.send('Ascii Characters registered successfully')
})

// Server setup
app.listen(port, () => {
  console.log(`Server start on port ${port}`)
})
```

**Filename–repository . js:**该文件包含创建本地数据库并与之交互的所有逻辑。

```
// Importing node.js file system module 
const fs = require('fs')

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
    records.push(attrs)
    await fs.promises.writeFile(
      this.filename,
      JSON.stringify(records, null, 2)   
    )
    return attrs
  }
}

// The 'datastore.json' file created at 
// runtime and all the information provided
// via signup form store in this file in 
// JSON format.
module.exports = new Repository('datastore.json')
```

**Filename–form . js:**该文件包含显示表单提交 Ascii 文本的逻辑。

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
              <form action='/register/ascii' method='POST'>             
                <div>
                  <div>
                    <label class='label' id='submittedBy'>
                      Submitted By
                    </label>
                  </div>
                  <input class='input' type='text' 
                         name='submittedBy' 
                         placeholder='SubmittedBy' 
                         for='submittedBy'>
                </div>
                <div>
                  <div>
                    <label class='label' id='ascii'>
                      Ascii Characters
                    </label>
                  </div>
                  <input class='input' type='text' 
                         name='ascii' placeholder='Ascii 
                         characters' for='ascii'>
                  <p class="help is-danger">
                    ${getError(errors, 'ascii')}
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

**Filename–validator . js:**该文件包含所有验证逻辑(验证输入字段只接受 ascii 字符的逻辑)。

```
const {check} = require('express-validator')
const repo = require('./repository')
module.exports = {

  validateAsciiCharacters : check('ascii')

    // To delete leading and triling space
    .trim()

    // Validate minimum length of ascii text
    // Optional for this context
    .isLength({min:8})
    .withMessage(
'Please submit minimum 8 characters long Ascii text')

    // Validate input field to accept only ascii chars
    .isAscii()
    .withMessage('Must be Ascii characters only')

}
```

**文件名–package . JSON**

![](img/bbbf3bf8b231c5f01f5ac9384cc87b83.png)

package.json 文件

**数据库:**

![](img/a7c25272f880d39a9a400161fd8c0d05.png)

数据库ˌ资料库

**输出:**

![](img/e28650b407ef87a4f7e4cc1b49d40b3d.png)

当 ascii 字符输入字段包含非 Ascii 字符时，尝试提交表单

![](img/a6b021e2dbba83bc3e382bdef94e3d5d.png)

当试图提交 ascii 字符输入字段包含非 Ascii 字符的表单时的响应

![](img/1e8a772e2a5fcb3312ecb41de2f13483.png)

当 ascii 字符输入字段仅包含 Ascii 字符时，尝试提交表单

![](img/371096ee68cb6dc021f7648d41b72503.png)

试图提交 ascii 字符输入字段仅包含 Ascii 字符的表单时的响应

**成功提交表单后的数据库:**

![](img/e1a1216b23599a309257be1541de49f2.png)

成功提交表单后的数据库

**注意:**我们在注册. js 文件中使用了一些布尔玛类(CSS 框架)来设计内容。