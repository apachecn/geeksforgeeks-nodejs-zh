# 使用 Node.js 中的 Google-play-刮板对安卓应用进行数据抓取

> 原文:[https://www . geeksforgeeks . org/data-scratch-for-Android-apps-use-Google-play-scratch-in-node-js/](https://www.geeksforgeeks.org/data-scraping-for-android-apps-using-google-play-scraper-in-node-js/)

最常见的刮网方法是我们在 Python 中使用的 selenium & beautifulsoup。尽管它可以帮助我们完成各种任务，但如果我们特别想提取谷歌 play 商店中已经存在的安卓应用的信息，用于研究甚至自用，还有另一种方法。

**谷歌游戏抓取器**是一个 Node.js 模块，通过提供使我们的工作变得容易的方法来帮助从谷歌游戏商店抓取应用数据。

**安装:**

```js
npm install google-play-scraper
```

**重要方法:**
**1。应用程序:**它返回与该应用程序相关的全部数据。

**参数:**

*   **appId:** 与 Google Play 上的应用相关联的 Id。这可以在《吗？URL 的 id=。
*   **lang:** 是可选参数。英语的默认值为“en”。如果我们想用不同的语言获取应用程序数据。我们可以为这个参数提供该语言的两个字母的代码。
*   **国家:**也是可选参数。美利坚合众国的默认值为“我们”。当我们正在查看的应用程序仅在特定国家/地区可用时，此参数非常有用。

**示例:**

```js
var gPlayScraper = require('google-play-scraper');

gPlayScraper.app({appId: 'free.programming.programming'})
    .then(console.log, console.log);
```

**输出:**

```js
[ { title: 'Learn DS & Algo, Programming Interview Preparation',
  description:
   'GeeksforGeeks is a one-stop destination for programmers.
   The app features 20000+ Programming Questions, 40, 000+....',
  descriptionHTML:
   'GeeksforGeeks is a one-stop destination for programmers.....',
  summary:
   'Learn Data Structures Algorithms, C Programming, C++,
    Java, Python, JS, Aptitude',
  installs: '500, 000+',
  minInstalls: 500000,
  score: 4.6594124,
  ...
  developer: 'GeeksforGeeks',
  developerId: 'GeeksforGeeks',
  developerEmail: 'support@geeksforgeeks.org',
  developerWebsite: 'https://www.geeksforgeeks.org/',
  developerAddress: 'Noida, UP, India',
  privacyPolicy: 'https://www.geeksforgeeks.org/privacy-policy/',
  developerInternalID: '5323597028845965498',
  genre: 'Education',
  genreId: 'EDUCATION',
  .....' ],
  .....
  url:
   'https://play.google.com/store/apps/details?id=free.programming.programming&hl=en&gl=us' } ]

```

**2。搜索:**它检索一个应用程序列表，这些应用程序按照给定的术语进行搜索。

**参数:**

*   **词条:**包含搜索词。
*   **num:** 我们希望检索的应用数量。它是一个可选参数，默认值为 20。请注意，该参数的最大值可以是 250。
*   **lang:** 是可选参数。英语的默认值为“en”。如果我们希望以不同的语言获取应用程序数据，我们可以为该参数提供该语言的两个字母的代码。
*   **国家:**也是可选参数。美利坚合众国的默认值为“我们”。当我们正在查看的应用程序仅在特定国家/地区可用时，此参数非常有用。
*   **价格:**我们可以通过“全部”来同时退回免费和付费应用，“免费”退回免费应用，“付费”退回付费应用。

**示例:**

```js
var gPlayScraper = require('google-play-scraper');

gPlayScraper.search({
    term: "tech",
    num: 2
  }).then(console.log, console.log);
```

**输出:**

```js
[ { title: 'CNET: Best Tech News, Reviews, Videos & Deals',
    appId: 'com.cbsinteractive.cnet',
    url:
     'https://play.google.com/store/apps/details?id=com.cbsinteractive.cnet',
    icon:
     'https://lh3.googleusercontent.com/DeIoPrQ4jp2STHmWzbWI8Ss8JRnPgFrmDoOLje2PXcpA7CQN8hFxOvxXCSOOEGLUUQ',
    developer: 'CBS Interactive, Inc.',
    developerId: 'CBS+Interactive, +Inc.',
    priceText: 'FREE',
    currency: undefined,
    price: 0,
    free: true,
    summary:
     'Breaking technology news and expert product how-tos,
      comparisons, advice & tips',
    scoreText: '4.0',
    score: 4 },
  { title: 'Tech Coach',
    appId: 'com.asurion.solutohome.verizon',
    ..
    score: 4.4551244 } ]

```

**3。建议:**它接受一个字符串输入，并返回一个包含五个建议的列表来完成我们的搜索查询。

**参数:**

*   **术语:**我们希望获得建议的术语。
*   **lang:** 是可选参数。英语的默认值为“en”。如果我们希望以不同的语言获取应用程序数据，我们可以为该参数提供该语言的两个字母的代码。
*   **国家:**也是可选参数。美利坚合众国的默认值为“我们”。当我们正在查看的应用程序仅在特定国家/地区可用时，此参数非常有用。

**示例:**

```js
var gPlayScraper = require('google-play-scraper');

gPlayScraper.suggest({term: 'algorithms'}).then(console.log);
```

**输出:**

```js
[ 'algorithms',
  'algorithms to live by',
  'algorithms and data structures',
  'algorithms explained and animated',
  "algorithms for rubik's cube" ]

```

**4。权限:**它返回一个应用可以访问的权限列表。

**参数:**

*   **appId:** 与 Google Play 上的应用相关联的 Id。这可以在《吗？URL 的 id=。
*   **lang:** 是可选参数。英语的默认值为“en”。如果我们希望以不同的语言获取应用程序数据，我们可以为该参数提供该语言的两个字母的代码。

**示例:**

```js
var gPlayScraper = require('google-play-scraper');

 // Let's analyse the permissions requested by SHAREit
gPlayScraper.permissions({appId: 'com.lenovo.anyshare.gps'}).
     .then(console.log, console.log);
```

**输出:**

```js
[ { permission: 'take pictures and videos', type: 'Camera' },
  { permission:
     "add or modify calendar events and send email to
      guests without owners' knowledge",
    type: 'Calendar' },
  { permission: 'record audio', type: 'Microphone' },
  { permission: 'read sensitive log data',
    type: 'Device & app history' },
  { permission: 'retrieve running apps',
    type: 'Device & app history' },
  ....
  { permission: 'send sticky broadcast', type: 'Other' },
  { permission: 'expand/collapse status bar', type: 'Other' },
  { permission: 'control vibration', type: 'Other' } ]

```

您可以查看的其他方法有:

*   **列表:**它返回 Google Play 的一个集合中的应用程序列表。
*   **开发人员:**它按照给定的开发人员名称返回应用程序列表。
*   **评论:**返回当前指定 app 的一整页评论。
*   **相似:**它返回与指定的应用程序相似的应用程序列表。
*   **类别:**返回谷歌 Play 商店上可用的类别列表。