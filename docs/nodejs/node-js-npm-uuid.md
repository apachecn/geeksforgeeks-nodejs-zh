# 节点. js NPM uuid

> 原文:[https://www.geeksforgeeks.org/node-js-npm-uuid/](https://www.geeksforgeeks.org/node-js-npm-uuid/)

NPM(节点包管理器)是 Node.js 包的包管理器。有一个名为“shortid”的 NPM 包，用于创建简短的非顺序 url 友好的唯一 id。唯一的 id 是由密码性强的随机值创建的，这就是它非常安全的原因。它支持跨平台，如 Node、React Native、Chrome、Safari、Firefox 等。

**安装命令:**

```js
npm install uuid
```

**在本地文件**中导入包的语法

```js
const {v4 : uuidv4} = require('uuid')

```

**创建唯一 id 的语法**

```js
const newId = uuidv4()

```

shortid 模块上定义了一些方法来创建唯一的 id 和自定义 id。下面举例说明了一些方法:

<figure class="table">

| **方法** | **工作** |
| uuid.尼罗河 | 零 UUID 字符串(全零) |
| uuid.parse（） | 将 UUID 字符串转换为字节数组 |
| uuid.validate() | 测试一个字符串，看它是否是有效的 UUID |
| uuid.v1（） | 创建版本 1(时间戳)UUID |
| uuid.v3（） | 创建版本 3(命名空间 w/ MD5) UUID |
| uuid.v4（） | 创建版本 4(随机)UUID |
| uuid.v5（） | 创建版本 5(命名空间 w/ SHA-1) UUID |
| uuid.stringify（） | 将字节数组转换为 UUID 字符串 |

</figure>

**示例 1:** 这个示例说明了如何生成和使用 uuid 包来创建唯一的 id。

**filename-index.js:** 该文件包含创建唯一 id 的所有逻辑，并将其与用户信息一起附加并保存到数据库中。

```js
const express = require('express')
const bodyParser = require('body-parser')
const {v4 : uuidv4} = require('uuid')
const formTemplet = require('./form')
const repo = require('./repository')

const app = express()
const port = process.env.PORT || 3000

// The body-parser middleware to parse form data
app.use(bodyParser.urlencoded({extended : true}))

// Get route to display HTML form
app.get('/', (req, res) => {
  res.send(formTemplet({}))
})

// Post route to handle form submission logic and 
app.post('/', (req, res) => {
  // Fetching user inputs
  const {name, email} = req.body
  // Creating new unique id
  const userId = uuidv4()

  // Saving record to the database
  // with attaching userid to each record
  repo.create({
    userId,
    name,
    email
  }) 
  res.send('Information submitted!')
})

// Server setup
app.listen(port, () => {
  console.log(`Server start on port ${port}`)
})
```

**filename–repository . js:**该文件包含创建数据库和与之交互的所有逻辑。

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
  async create(attrs){
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

**filename–form . js:**这个文件包含了渲染表单的所有逻辑。

```js
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
        <form action='/' method='POST'>
          <div>
            <div>
              <label class='label' 
                id='str'>Name
              </label>
            </div>
            <input class='input' type='text' 
              name='name' placeholder='Name' 
              for='name'>
          </div>
          <div>
            <div>
              <label class='label' id='email'>
                Email
              </label>
            </div>
            <input class='input' type='email' 
              name='email' placeholder='Email' 
              for='email'>
          </div>
          <div>
            <button class='button is-info'>
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

**输出:**

![](img/c0ef8ee2e7479db1a16ad18a779bc41a.png)

提交信息 1

![](img/ba95447961ac75f8283f509ae6b486e5.png)

提交信息 2

**数据库:**

![](img/d7b0bc255e4cb5b8bcad5f7c9620795a.png)

提交信息后的数据库

**示例 2:** 这个示例说明了如何使用 uuid.parse()和 uuid.stringify()方法。

**filename-index.js:** 该文件包含创建唯一 id 的所有逻辑，并将其与用户信息一起附加并保存到数据库中，还将 id 转换为解析的字节，并将解析的字节转换为字符串 id。

```js
const express = require('express')
const bodyParser = require('body-parser')
const {
  v4 : uuidv4,
  parse:uuidParse,
  stringify : uuidStringify
} = require('uuid')

const formTemplet = require('./form')
const repo = require('./repository')

const app = express()
const port = process.env.PORT || 3000

// The body-parser middleware to parse form data
app.use(bodyParser.urlencoded({extended : true}))

// Get route to display HTML form
app.get('/', (req, res) => {
  res.send(formTemplet({}))
})

// Post route to handle form submission logic and 
app.post('/', (req, res) => {

  // Fetching user inputs
  const {name, email} = req.body
  // Creating new unique id
  const userId = uuidv4()
  const parsedId = uuidParse(userId)
  const stringfyId = uuidStringify(parsedId)
  console.log(`parsedId : ${parsedId}\n`)
  console.log(`StringifyId : ${stringfyId}\n`)

  // Saving record to the database
  // with attaching userid to each record
  repo.create({
    userId,
    name,
    email
  }) 
  res.send('Information submitted!')
})

// Server setup
app.listen(port, () => {
  console.log(`Server start on port ${port}`)
})
```

**filename–repository . js:**该文件包含创建数据库和与之交互的所有逻辑。

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
  async create(attrs){
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

**filename–form . js:**这个文件包含了渲染表单的所有逻辑。

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
        <form action='/' method='POST'>
          <div>
            <div>
              <label class='label' id='str'>
                Name
              </label>
            </div>
            <input class='input' type='text' 
              name='name' placeholder='Name' 
              for='name'>
          </div>
          <div>
            <div>
              <label class='label' id='email'>
                Email
              </label>
            </div>
            <input class='input' type='email' 
              name='email' placeholder='Email' 
              for='email'>
          </div>
          <div>
            <button class='button is-info'>
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

**输出:**

![](img/04a1e411ac6d27f1ebfe259a513e7a5c.png)

提交信息

![](img/d8c49920b09f612a256f892c1ca81d51.png)

已解析的 id 和字符串 id

**数据库:**

![](img/047e863715a5c894a843067ad1297606.png)

提交信息后的数据库

**注意:**我们在 form.js 文件中使用了一些布尔玛类来设计我们的内容。