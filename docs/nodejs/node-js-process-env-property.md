# node . js process . env Property

> 原文:[https://www.geeksforgeeks.org/node-js-process-env-property/](https://www.geeksforgeeks.org/node-js-process-env-property/)

**process.env 属性**是流程模块的内置应用编程接口，用于获取用户环境。

**语法:**

```js
process.env
```

**返回值:**该属性返回包含用户环境的对象。

下面的例子说明了 **process.env 属性**在 Node.js 中的使用:

**例 1:**

```js
// Node.js program to demonstrate the
// process.env Property

// Include process module
const process = require('process');

// Printing process.env property value
console.log(process.env);
```

**输出:**

```js
{ ALLUSERSPROFILE: 'C:\\ProgramData',
  APPDATA: 'C:\\Users\\gekcho\\AppData\\Roaming',
  cmake: 'D:\\programfiles\\Cmake\\bin\\cmake.exe',
  CommonProgramFiles: 'C:\\Program Files\\Common Files',
  'CommonProgramFiles(x86)': 'C:\\Program Files (x86)\\Common Files',
  CommonProgramW6432: 'C:\\Program Files\\Common Files',
  COMPUTERNAME: 'gekchos_lappy',
  ComSpec: 'C:\\Windows\\system32\\cmd.exe',
  DriverData: 'C:\\Windows\\System32\\Drivers\\DriverData',
  GTK_BASEPATH: 'C:\\Program Files (x86)\\GtkSharp\\2.12\\',
  HADOOP_HOME:
   'C:\\Users\\gekcho\\Downloads\\Compressed\\hadoop-3.1.0\\hadoop-3.1.0\\bin',
  HOMEDRIVE: 'C:',
  HOMEPATH: '\\Users\\gekcho',
  JAVA_HOME: 'C:\\Java\\jdk1.8.0_201',
  LOCALAPPDATA: 'C:\\Users\\gekcho\\AppData\\Local',
  LOGONSERVER: '\\\\gekchos_lappy',
  MAGICK_HOME: 'C:\\wamp64\\bin\\php\\php7.3.1\\ext\\ImageMagick',
  NUMBER_OF_PROCESSORS: '4',
  OneDrive: 'C:\\Users\\gekcho\\OneDrive',
  OneDriveConsumer: 'C:\\Users\\gekcho\\OneDrive',
  OS: 'Windows_NT',
  Path:
   'C:\\wamp64\\bin\\php\\php7.3.1\\ext\\ImageMagick;
    C:\\Program Files (x86)\\Common Files\\Oracle\\Java\\javapath;
    C:\\Windows\\system32;C:\\Windows;C:\\Windows\\System32\\Wbem;
    C:\\Windows\\System32\\WindowsPowerShell\\v1.0\\;
    C:\\Windows\\System32\\OpenSSH\\;D:\\programfiles\\Git\\cmd;
    D:\\programfiles\\Cmake\\bin;C:\\Program Files\\nodejs\\;
    C:\\Users\\gekcho\\Downloads\\Compressed\\hadoop-3.1.0\\hadoop-3.1.0\\bin;
    C:\\Java\\jdk1.8.0_201\\bin;
    C:\\Users\\gekcho\\Downloads\\Compressed\\spark-2.4.4-bin-hadoop2.7\\bin;
    C:\\Program Files (x86)\\GtkSharp\\2.12\\bin;
    C:\\Users\\gekcho\\AppData\\Local\\Microsoft\\WindowsApps;
    C:\\Users\\gekcho\\AppData\\Roaming\\npm',
  PATHEXT: '.COM;.EXE;.BAT;.CMD;.VBS;.VBE;.JS;.JSE;.WSF;.WSH;.MSC',
  PROCESSOR_ARCHITECTURE: 'AMD64',
  PROCESSOR_IDENTIFIER: 'Intel64 Family 6 Model 142 Stepping 9, GenuineIntel',
  PROCESSOR_LEVEL: '6',
  PROCESSOR_REVISION: '8e09',
  ProgramData: 'C:\\ProgramData',
  ProgramFiles: 'C:\\Program Files',
  'ProgramFiles(x86)': 'C:\\Program Files (x86)',
  ProgramW6432: 'C:\\Program Files',
  PROMPT: '$P$G',
  PSModulePath:
   'C:\\Program Files\\WindowsPowerShell\\Modules;
    C:\\Windows\\system32\\WindowsPowerShell\\v1.0\\Modules',
  PUBLIC: 'C:\\Users\\Public',
  python3:
   'C:\\Users\\gekcho\\AppData\\Local\\Programs\\Python\\Python37-32\\python.exe',
  SESSIONNAME: 'Console',
  SPARK_HOME:
   'C:\\Users\\gekcho\\Downloads\\Compressed\\spark-2.4.4-bin-hadoop2.7',
  SystemDrive: 'C:',
  SystemRoot: 'C:\\Windows',
  TEMP: 'C:\\Users\\gekcho\\AppData\\Local\\Temp',
  TMP: 'C:\\Users\\gekcho\\AppData\\Local\\Temp',
  USERDOMAIN: 'gekchos_lappy',
  USERDOMAIN_ROAMINGPROFILE: 'gekchos_lappy',
  USERNAME: 'gekcho',
  USERPROFILE: 'C:\\Users\\gekcho',
  windir: 'C:\\Windows' }

```

**范例 2:**

```js
// Node.js program to demonstrate the
// process.env Property

// Include process module
const process = require('process');

// Printing process.env property value
var no_env = 0;

// Calling process.env
var env = process.env;

// Itterating through all returned data
for (var key in env) {

    // Print value
    console.log(key + ":\t\t\t" + env[key]);
    no_env++;
}

// Printing count
console.log("total no of values available = "
            + no_env);

// Accessing one by one
console.log("operating system: " + env['OS']);
console.log("alluserprofile: " + env['ALLUSERSPROFILE']);
console.log("public directory: " + env['PUBLIC']);
```

**输出:**

```js
ALLUSERSPROFILE:        C:\ProgramData
APPDATA:                C:\Users\gekcho\AppData\Roaming
cmake:                  D:\programfiles\Cmake\bin\cmake.exe
CommonProgramFiles:     C:\Program Files\Common Files
CommonProgramFiles(x86):C:\Program Files (x86)\Common Files
CommonProgramW6432:     C:\Program Files\Common Files
COMPUTERNAME:           gekchos_lappy
ComSpec:                C:\Windows\system32\cmd.exe
DriverData:             C:\Windows\System32\Drivers\DriverData
GTK_BASEPATH:           C:\Program Files (x86)\GtkSharp\2.12\
HADOOP_HOME:            C:\Users\gekcho\Downloads\Compressed\hadoop-3.1.0\hadoop-3.1.0\bin
HOMEDRIVE:              C:
HOMEPATH:               \Users\gekcho
JAVA_HOME:              C:\Java\jdk1.8.0_201
LOCALAPPDATA:           C:\Users\gekcho\AppData\Local
LOGONSERVER:            \\gekchos_lappy
MAGICK_HOME:            C:\wamp64\bin\php\php7.3.1\ext\ImageMagick
NUMBER_OF_PROCESSORS:   4
OneDrive:               C:\Users\gekcho\OneDrive
OneDriveConsumer:       C:\Users\gekcho\OneDrive
OS:                     Windows_NT
Path:                   C:\wamp64\bin\php\php7.3.1\ext\ImageMagick;
C:\Program Files (x86)\Common Files\Oracle\Java\javapath;
C:\Windows\system32;C:\Windows;
C:\Windows\System32\Wbem;
C:\Windows\System32\WindowsPowerShell\v1.0\;
C:\Windows\System32\OpenSSH\;D:\programfiles\Git\cmd;
D:\programfiles\Cmake\bin;C:\Program Files\nodejs\;
C:\Users\gekcho\Downloads\Compressed\hadoop-3.1.0\hadoop-3.1.0\bin;
C:\Java\jdk1.8.0_201\bin;
C:\Users\gekcho\Downloads\Compressed\spark-2.4.4-bin-hadoop2.7\bin;
C:\Program Files (x86)\GtkSharp\2.12\bin;
C:\Users\gekcho\AppData\Local\Microsoft\WindowsApps;
C:\Users\gekcho\AppData\Roaming\npm
PATHEXT:               .COM;.EXE;.BAT;.CMD;.VBS;.VBE;.JS;.JSE;.WSF;.WSH;.MSC
PROCESSOR_ARCHITECTURE:AMD64
PROCESSOR_IDENTIFIER:  Intel64 Family 6 Model 142 Stepping 9, GenuineIntel
PROCESSOR_LEVEL:       6
PROCESSOR_REVISION:    8e09
ProgramData:           C:\ProgramData
ProgramFiles:          C:\Program Files
ProgramFiles(x86):     C:\Program Files (x86)
ProgramW6432:          C:\Program Files
PROMPT:                $P$G
PSModulePath:          C:\Program Files\WindowsPowerShell\Modules;
                       C:\Windows\system32\WindowsPowerShell\v1.0\Modules
PUBLIC:                C:\Users\Public
python3:               C:\Users\gekcho\AppData\Local\Programs\Python\Python37-32\python.exe
SESSIONNAME:           Console
SPARK_HOME:            C:\Users\gekcho\Downloads\Compressed\spark-2.4.4-bin-hadoop2.7
SystemDrive:           C:
SystemRoot:            C:\Windows
TEMP:                  C:\Users\gekcho\AppData\Local\Temp
TMP:                   C:\Users\gekcho\AppData\Local\Temp
USERDOMAIN:            gekchos_lappy
USERDOMAIN_ROAMINGPROFILE:gekchos_lappy
USERNAME:              gekcho
USERPROFILE:           C:\Users\gekcho
windir:                C:\Windows
total no of values available = 46
operating system: Windows_NT
alluserprofile: C:\ProgramData
public directory: C:\Users\Public

```

**例 3:**

```js
// Node.js program to demonstrate the
// process.env Property

// Include process module
const process = require('process');

// Printing process.env property value
var env = process.env;

console.log("operating system: " + env.OS);
console.log("alluserprofile: " + env.ALLUSERSPROFILE);
console.log("public directory: " + env.PUBLIC);

// Setting new data
env.gekcho = "gekcho custom data";
console.log("stored in env.gekcho: " + env.gekcho);

// Delete data
delete env.gekcho
console.log("stored in env.gekcho: " + env.gekcho);
```

**输出:**

```js
operating system: Windows_NT
alluserprofile: C:\ProgramData
public directory: C:\Users\Public
stored in env.gekcho: gekcho custom data
stored in env.gekcho: undefined

```

**注意:**以上程序使用`node filename.js`命令编译运行。

**参考:**T2】https://nodejs.org/api/process.html#process_process_env