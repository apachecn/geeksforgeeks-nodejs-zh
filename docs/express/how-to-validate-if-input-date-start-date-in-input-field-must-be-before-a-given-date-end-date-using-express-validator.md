# 如何使用快速验证器验证输入字段中的输入日期(开始日期)是否必须在给定日期(结束日期)之前？

> 原文:[https://www . geesforgeks . org/如何使用快速验证器验证输入日期字段中的开始日期必须在给定日期之前结束日期/](https://www.geeksforgeeks.org/how-to-validate-if-input-date-start-date-in-input-field-must-be-before-a-given-date-end-date-using-express-validator/)

在 HTML 表单中，我们经常需要不同类型的验证。验证现有电子邮件、验证密码长度、验证确认密码、验证为仅允许整数输入，这些都是验证的一些示例。在某些情况下，我们希望用户键入一个必须早于某个给定日期的日期(例如:“开始日期”必须早于“结束日期”)，基于此，我们授予用户对请求的访问权限或拒绝对请求的访问权限。我们还可以使用 express-validator 中间件来验证这些输入字段。

**安装快递验证器的命令:**

```js
npm install express-validator
```

**使用快递验证器实现逻辑的步骤:**

*   Install the courier verifier middleware.
*   Create a validator.js file to encode all validation logic.
*   Use the custom validator to verify and get the end date as the request body.
*   Convert date strings to valid dates and compare them as needed.
*   Use the validation name (validateInputField) in the route as the middleware and as a validation array.
*   Destruct the' validationresult' function from express-validator and use it to find any errors.
*   If an error occurs, redirect to the same page where the error message is sent.
*   If the error list is empty, the user is allowed to access subsequent requests.

**注意:**这里我们使用本地或自定义数据库来实现逻辑，同样的步骤也可以在 MongoDB 或 MySql 这样的常规数据库中实现逻辑。

**示例:**此示例说明了如何验证输入字段，以仅允许给定日期之后的日期。

**文件名–index . js**

## 【JavaScript】

```js
const express = require('express')
const bodyParser = require('body-parser')
const {validationResult} = require('express-validator')
const repo = require('./repository')
const { validateStartDate } = require('./validator')
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
  '/project',
  [validateStartDate],
  async (req, res) => {
    const errors = validationResult(req)
    if(!errors.isEmpty()) {
      return res.send(formTemplet({errors}))
    }
    const {name, domain, sdate, edate, } = req.body

    // Fetch year, month, day of respective dates
    const [sd, sm, sy] = sdate.split('/')
    const [ed, em, ey] = edate.split('/')

    // New record
    await repo.create({
      'Project Name': name,
      'Project Domain': domain,
      'Start Date': new Date(sy, sm-1, sd).toDateString(),
      'End Date': new Date(ey, em-1, ed).toDateString()
    })

res.send(
'<strong>Project details stored successfully'
   + ' in the database</strong>');
})

// Server setup
app.listen(port, () => {
  console.log(`Server start on port ${port}`)
})
```

**Filename–repository . js:**该文件包含创建本地数据库并与之交互的所有逻辑。

## JavaScript

```js
// Importing node.js file system module
const fs = require('fs')

class Repository {

  constructor(filename) {

    // Filename where data are going to store
    if (!filename) {
      throw new Error(
'Filename is required to create a datastore!')
    }

    this.filename = filename

    try {
      fs.accessSync(this.filename)
    } catch(err) {

      // If file not exist it is created with empty array
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

// The'datastore.json' file created at
// runtime and all the information
// provided via signup form store
// in this file in JSON formet.
module.exports = new Repository('datastore.json')
```

**文件名–form . js:**该文件包含逻辑，用于显示提交项目数据的表单以及开始和结束日期。

## JavaScript

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
                <form action='/project' method='POST'>
                    <div>
                        <div>
                            <label class='label'
                                id='name'>
                                Project Name
                            </label>
                        </div>
                        <input class='input' type='text'
                            name='name' placeholder='Project Name'
                            for='name'>
                    </div>
                    <div>
                        <div>
                            <label class='label' id='domain'>
                                Project Domain
                            </label>
                        </div>
                        <input class='input' type='text'
                            name='domain' placeholder='Project Domain'
                            for='base64data'>
                    </div>
                    <div>
                        <div>
                            <label class='label' id='sdate'>
                                Start Date
                            </label>
                        </div>
                        <input class='input' type='text'
                            name='sdate' placeholder='dd/mm/yyyy'
                            for='sdate'>
                        <p class="help is-danger">
                            ${getError(errors, 'sdate')}
                        </p>
                    </div>
                    <div>
                        <div>
                            <label class='label' id='edate'>
                                End Date
                            </label>
                        </div>
                        <input class='input' type='text'
                            name='edate' placeholder='dd/mm/yyyy'
                            for='edate'>
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

**Filename–validator . js:**该文件包含所有验证逻辑(验证输入字段的逻辑，只接受给定日期之前的日期)。

## JavaScript

```js
const { check } = require('express-validator')
const repo = require('./repository')
module.exports = {

    validateStartDate: check('sdate')

        // To delete leading and triling space
        .trim()

        // Custom validator
        .custom((sdate, { req }) => {

            // Fetch year, month and day of
            // respective dates
            const [sd, sm, sy] = sdate.split('/')
            const [ed, em, ey] = req.body.edate.split('/')

            // Constructing dates from given
            // string date input
            const startDate = new Date(sy, sm, sd)
            const endDate = new Date(ey, em, ed)

            // Validate start date so that it must
            // comes before end date
            if (startDate >= endDate) {
                throw new Error(
'Start date of project must be before End date')
            }
            return true
        })
}
```