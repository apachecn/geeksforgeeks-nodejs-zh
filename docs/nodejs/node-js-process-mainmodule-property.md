# 节点. js 进程.主模块属性

> 原文:[https://www . geesforgeks . org/node-js-process-main module-property/](https://www.geeksforgeeks.org/node-js-process-mainmodule-property/)

**process.mainModule 属性**是流程模块的内置应用编程接口，用于获取主模块。这是获取 require.main 的另一种方法，但与 require.main 不同，process.mainModule 在运行时会动态更改。一般来说，我们可以假设这两个模块是相同的。

**语法:**

```js
process.mainModule
```

**返回值:**该属性返回一个包含主模块引用的对象。

下面的例子说明了在 Node.js 中 **process.mainModule 属性**的使用:

**例 1:**

```js
// Node.js program to demonstrate the
// process.mainModule Property

// Include process module
const process = require('process');

// Printing process.mainModule property value
console.log(process.mainModule);
```

**输出:**

```js
Module {
  id: '.',
  exports: {},
  parent: null,
  filename: 'C:\\nodejs\\g\\process\\mainmodule_1.js',
  loaded: false,
  children: [],
  paths:
   [ 'C:\\nodejs\\g\\process\\node_modules',
     'C:\\nodejs\\g\\node_modules',
     'C:\\nodejs\\node_modules',
     'C:\\node_modules' 
   ]
}

```

**例 2:**

```js
// Node.js program to demonstrate the
// process.mainModule Property

// Include process module
const process = require('process');

// Printing process.mainModule property value
var mainModule = process.mainModule;
for(mod in mainModule) {
    console.log(mod + ":" + mainModule[mod]);
}
```

**输出:**

```js
id:.
exports:[object Object]
parent:null
filename:/home/cg/root/6720369/main.js
loaded:false
children:
paths:/home/cg/root/6720369/node_modules, /home/cg/root/node_modules,
 /home/cg/node_modules, /home/node_modules, /node_modules
load:function (filename) {
  debug('load %j for module %j', filename, this.id);

  assert(!this.loaded);
  this.filename = filename;
  this.paths = Module._nodeModulePaths(path.dirname(filename));

  var extension = path.extname(filename) || '.js';
  if (!Module._extensions[extension]) extension = '.js';
  Module._extensions[extension](this, filename);
  this.loaded = true;
}
require:function (path) {
  assert(path, 'missing path');
  assert(typeof path === 'string', 'path must be a string');
  return Module._load(path, this, /* isMain */ false);
}
_compile:function (content, filename) {
  // Remove shebang
  var contLen = content.length;
  if (contLen >= 2) {
    if (content.charCodeAt(0) === 35/*#*/ &&
        content.charCodeAt(1) === 33/*!*/) {
      if (contLen === 2) {
        // Exact match
        content = '';
      } else {
        // Find end of shebang line and slice it off
        var i = 2;
        for (; i < contLen; ++i) {
          var code = content.charCodeAt(i);
          if (code === 10/*\n*/ || code === 13/*\r*/)
            break;
        }
        if (i === contLen)
          content = '';
        else {
          // Note that this actually includes the newline character(s) in the
          // new output. This duplicates the behavior of the regular expression
          // that was previously used to replace the shebang line
          content = content.slice(i);
        }
      }
    }
  }

  // create wrapper function
  var wrapper = Module.wrap(content);

  var compiledWrapper = vm.runInThisContext(wrapper, {
    filename: filename,
    lineOffset: 0,
    displayErrors: true
  });

  if (process._debugWaitConnect && process._eval == null) {
    if (!resolvedArgv) {
      // we enter the repl if we're not given a filename argument.
      if (process.argv[1]) {
        resolvedArgv = Module._resolveFilename(process.argv[1], null);
      } else {
        resolvedArgv = 'repl';
      }
    }

    // Set breakpoint on module start
    if (filename === resolvedArgv) {
      delete process._debugWaitConnect;
      const Debug = vm.runInDebugContext('Debug');
      Debug.setBreakPoint(compiledWrapper, 0, 0);
    }
  }
  var dirname = path.dirname(filename);
  var require = internalModule.makeRequireFunction.call(this);
  var args = [this.exports, require, this, filename, dirname];
  var depth = internalModule.requireDepth;
  if (depth === 0) stat.cache = new Map();
  var result = compiledWrapper.apply(this.exports, args);
  if (depth === 0) stat.cache = null;
  return result;
}

```

**注意:**以上程序使用`node filename.js`命令编译运行。

**参考:**[https://nodejs . org/API/process . html # process _ process _ main module](https://nodejs.org/api/process.html#process_process_mainmodule)