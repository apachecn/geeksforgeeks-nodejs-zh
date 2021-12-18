# 如何使用 express-validator 验证输入字段中的输入是否只有十六进制数？

> 原文:[https://www . geesforgeks . org/如何验证输入字段中的输入是否有十六进制数字-仅使用快速验证器/](https://www.geeksforgeeks.org/how-to-validate-if-input-in-input-field-has-hexadecimal-number-only-using-express-validator/)

在 HTML 表单中，我们经常需要不同类型的验证。验证现有电子邮件、验证密码长度、验证确认密码、验证为仅允许整数输入，这些都是验证的一些示例。在某个输入字段中，只允许十六进制数字。我们还可以使用 express-validator 中间件验证这些输入字段，使其只接受全角字符串。

十六进制以十六为基数。由于大多数计算机都是由只能有两种稳定状态(如开或关)的元素组成的，所以我们用二进制(基数为二)来表示计算机中一组状态的位(二进制数字)。然而，人类更喜欢基数大于 2 的数字。因此，人们发现用更少的数字来写代表计算机内存的数字更方便，其中每个数字来自更大的集合(例如{0123456789ABCDEF}代表“十六进制”，它使用基数-16)。

**安装快速验证器的命令:**

```js
npm install express-validator

```

**使用快速验证器实现逻辑的步骤:**

*   安装快速验证中间件。
*   创建一个 validator.js 文件来编码所有的验证逻辑。
*   通过 validateInputField 验证输入:用“.”检查(输入字段名)和验证链
*   在路由中使用验证名称(validateInputField)作为一个中间件，作为一个验证数组。
*   从快速验证器中析构“验证结果”函数，用它来查找任何错误。
*   如果发生错误，重定向到传递错误信息的同一页。
*   如果错误列表为空，则允许用户访问后续请求。

**注意:**这里我们使用本地或自定义数据库来实现逻辑，同样的步骤也可以在 MongoDB 或 MySql 这样的常规数据库中实现逻辑。

**示例:**此示例说明了如何验证输入字段以仅允许十六进制数字。

**文件名–index . js**

```js
const express = require('express')
const bodyParser = require('body-parser')
const {validationResult} = require('express-validator')
const repo = require('./repository')
const { validateIdentificationNumber } = require('./validator')
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
  [validateIdentificationNumber],
  async (req, res) => {
    const errors = validationResult(req)

    if(!errors.isEmpty()) {
      return res.send(formTemplet({errors}))
    }

    const {name, idn} = req.body

    // New record
    await repo.create({
      'Name':name,
      'Identification Number':idn
    })
    res.send('<strong>Registered successfully..!!</strong>')
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

    // Filename where data are going to store
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
              <label class='label' id='idn'>
                Hexadecimal Identification Number
              </label>
            </div>
            <input class='input' type='text' name='idn' 
              placeholder=
              'Choose your hexadecimal Identification Number'
              for='idn'>
            <p class="help is-danger">
              ${getError(errors, 'idn')}
            </p>
          </div>
          <div>
            <button class='button is-primary'>Submit</button>
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

**Filename–validator . js:**该文件包含所有验证逻辑(验证输入字段只允许十六进制数字的逻辑)。

```js
const {check} = require('express-validator')
const repo = require('./repository')
module.exports = {

  validateIdentificationNumber : check('idn')

    // To delete leading and triling space
    .trim()

    // Validate identification number to 
    // accept only hexadecimal number
    .isHexadecimal()

    // Custom message
    .withMessage('Must be a hexadecimal number')   
}
```

**文件名–package . JSON**

![](img/bbbf3bf8b231c5f01f5ac9384cc87b83.png)

package.json 文件

**数据库:**

![](img/48c00c1d56e75ad77e6383858116de37.png)

数据库ˌ资料库

**输出:**

![](img/a43a871d619f7c3a29b11b58ff696cfa.png)

当标识号输入字段不是有效的十六进制数时，尝试提交表单数据

![](img/0c9bd380b5ebd9218ff23d299bd5b240.png)

试图提交标识号输入字段不是有效十六进制数的表单数据时的响应

![](img/5b5af4f0963c48d17f1d819ad0e3a0e1.png)

当标识号输入字段是有效的十六进制数时，尝试提交表单数据

![](img/d92f961f3092439aa28a260f52a530d9.png)

当试图提交标识号输入字段为有效十六进制数的表单数据时的响应

**成功提交表单后的数据库:**

![](img/833b0856b6c8add8276fe912a8fe2ac9.png)

成功提交表单后的数据库

**注意:**我们在 form.js 文件中使用了一些布尔玛类(CSS 框架)来设计内容。