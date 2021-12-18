# node . js . OS . getpriority()方法

> 原文:[https://www . geesforgeks . org/node-js-OS-get priority-method/](https://www.geeksforgeeks.org/node-js-os-getpriority-method/)

**os.getPriority()方法**是 os 模块内置的应用编程接口，用于获取 pid 指定的进程调度优先级。

**语法:**

```js
os.getPriority( pid )
```

**参数:**该方法接受如上所述的单个参数，描述如下:

*   **pid:** 是一个可选参数，指定要返回调度优先级的进程 id。它的默认值是 0。

**返回值:**该方法返回一个整数值，指定 pid 指定的进程的调度优先级。如果进程 id (pid)的值设置为 0，则返回当前进程的调度优先级。

下面的例子说明了 **os.getPriority()方法**在 Node.js 中的使用:

**例 1:**

## java 描述语言

```js
// Node.js program to demonstrate the   
// os.getPriority() Method

// Require os module
const os = require('os');

// Printing os.getPriority() value
try {

    // Printing priority of current process
    console.log(os.getPriority());
}catch(err){
    console.log(i + ": error occured" + err);
}
```

**输出:**

```js
0
```

**例 2:**

## java 描述语言

```js
// Node.js program to demonstrate the   
// os.getPriority() Method

// Require os module
const os = require('os');

// Accessing  ps-list module to
// get process details
const psList = require('ps-list');

// Calling psList function defined
// in ps-list module
psList().then(data => {

    // Printing all the process information
    // from returned data
    console.log(data);

    // Iterating through each element
    // of the returned data
    data.forEach(function(element){
        try{

            // Getting priority of selected process
            var process_priority=os.getPriority(element.pid);

            // Printing pid priority and process name 
            console.log("pid:" + String(element.pid)
                + "\t priority:" + String(process_priority)
                + "\t name:" + String(element.name));
        }catch(err){

            // There will be error like operation
            // not permitted, so omitting error to
            // get clean output printing error
            // generated from os.getPriority() function
            //console.log("pid:"+String(element.pid)+
            //"\t priority: error \t name:"
            //+String(element.name)); console.log(err);
      }
  });
});
```

**输出:**

```js
[ { name: '[System Process]', pid: 0, ppid: 0 },
  { name: 'System', pid: 4, ppid: 0 },
  { name: 'Registry', pid: 96, ppid: 4 },
  { name: 'smss.exe', pid: 392, ppid: 4 },
  { name: 'csrss.exe', pid: 640, ppid: 624 },
  { name: 'wininit.exe', pid: 752, ppid: 624 },
  { name: 'csrss.exe', pid: 768, ppid: 744 },
  { name: 'services.exe', pid: 824, ppid: 752 },
  { name: 'lsass.exe', pid: 832, ppid: 752 },
  { name: 'svchost.exe', pid: 956, ppid: 824 },
  { name: 'WUDFHost.exe', pid: 964, ppid: 824 },
  { name: 'svchost.exe', pid: 992, ppid: 824 },
  { name: 'fontdrvhost.exe', pid: 72, ppid: 752 },
  { name: 'svchost.exe', pid: 548, ppid: 824 },
  { name: 'svchost.exe', pid: 868, ppid: 824 },
  { name: 'winlogon.exe', pid: 1104, ppid: 744 },
  { name: 'fontdrvhost.exe', pid: 1164, ppid: 1104 },
  { name: 'dwm.exe', pid: 1240, ppid: 1104 },
  { name: 'svchost.exe', pid: 1300, ppid: 824 },
  { name: 'svchost.exe', pid: 1328, ppid: 824 },
  { name: 'svchost.exe', pid: 1360, ppid: 824 },
  { name: 'svchost.exe', pid: 1376, ppid: 824 },
  { name: 'svchost.exe', pid: 1480, ppid: 824 },
  { name: 'svchost.exe', pid: 1588, ppid: 824 },
  { name: 'svchost.exe', pid: 1640, ppid: 824 },
  { name: 'svchost.exe', pid: 1676, ppid: 824 },
  { name: 'svchost.exe', pid: 1684, ppid: 824 },
  { name: 'svchost.exe', pid: 1740, ppid: 824 },
  { name: 'svchost.exe', pid: 1836, ppid: 824 },
  { name: 'svchost.exe', pid: 1884, ppid: 824 },
  { name: 'svchost.exe', pid: 1948, ppid: 824 },
  { name: 'svchost.exe', pid: 1956, ppid: 824 },
  { name: 'svchost.exe', pid: 2024, ppid: 824 },
  { name: 'dasHost.exe', pid: 2084, ppid: 2024 },
  { name: 'svchost.exe', pid: 2124, ppid: 824 },
  { name: 'svchost.exe', pid: 2184, ppid: 824 },
  { name: 'svchost.exe', pid: 2196, ppid: 824 },
  { name: 'svchost.exe', pid: 2268, ppid: 824 },
  { name: 'svchost.exe', pid: 2360, ppid: 824 },
  { name: 'atiesrxx.exe', pid: 2400, ppid: 824 },
  { name: 'atieclxx.exe', pid: 2496, ppid: 2400 },
  { name: 'svchost.exe', pid: 2504, ppid: 824 },
  { name: 'svchost.exe', pid: 2512, ppid: 824 },
  { name: 'svchost.exe', pid: 2524, ppid: 824 },
  { name: 'Memory Compression', pid: 2588, ppid: 4 },
  { name: 'svchost.exe', pid: 2664, ppid: 824 },
  { name: 'igfxCUIService.exe', pid: 2688, ppid: 824 },
  { name: 'svchost.exe', pid: 2728, ppid: 824 },
  { name: 'svchost.exe', pid: 2736, ppid: 824 },
  { name: 'svchost.exe', pid: 2924, ppid: 824 },
  { name: 'svchost.exe', pid: 2952, ppid: 824 },
  { name: 'RtkAudioService64.exe', pid: 2096, ppid: 824 },
  { name: 'svchost.exe', pid: 2824, ppid: 824 },
  { name: 'svchost.exe', pid: 2820, ppid: 824 },
  { name: 'svchost.exe', pid: 3180, ppid: 824 },
  { name: 'svchost.exe', pid: 3188, ppid: 824 },
  { name: 'svchost.exe', pid: 3264, ppid: 824 },
  { name: 'svchost.exe', pid: 3364, ppid: 824 },
  { name: 'svchost.exe', pid: 3464, ppid: 824 },
  { name: 'svchost.exe', pid: 3500, ppid: 824 },
  { name: 'svchost.exe', pid: 3508, ppid: 824 },
  { name: 'svchost.exe', pid: 3556, ppid: 824 },
  { name: 'spoolsv.exe', pid: 3564, ppid: 824 },
  { name: 'svchost.exe', pid: 3736, ppid: 824 },
  { name: 'mDNSResponder.exe', pid: 3820, ppid: 824 },
  { name: 'armsvc.exe', pid: 3828, ppid: 824 },
  { name: 'OfficeClickToRun.exe', pid: 3840, ppid: 824 },
  { name: 'IntelCpHDCPSvc.exe', pid: 3856, ppid: 824 },
  { name: 'svchost.exe', pid: 3864, ppid: 824 },
  { name: 'svchost.exe', pid: 3884, ppid: 824 },
  { name: 'esif_uf.exe', pid: 3932, ppid: 824 },
  { name: 'svchost.exe', pid: 3940, ppid: 824 },
  { name: 'wlanext.exe', pid: 3948, ppid: 3464 },
  { name: 'mongod.exe', pid: 4028, ppid: 824 },
  { name: 'MDZkM.exe', pid: 4056, ppid: 824 },
  { name: 'rundll32.exe', pid: 4084, ppid: 824 },
  { name: 'svchost.exe', pid: 3076, ppid: 824 },
  { name: 'rundll32.exe', pid: 3068, ppid: 4084 },
  { name: 'RtkBtAudioServ.exe', pid: 3720, ppid: 824 },
  { name: 'conhost.exe', pid: 4108, ppid: 3948 },
  { name: 'svchost.exe', pid: 4116, ppid: 824 },
  { name: 'SynTPEnhService.exe', pid: 4144, ppid: 824 },
  { name: 'svchost.exe', pid: 4152, ppid: 824 },
  { name: 'MsMpEng.exe', pid: 4180, ppid: 824 },
  { name: 'svchost.exe', pid: 4220, ppid: 824 },
  { name: 'svchost.exe', pid: 4228, ppid: 824 },
  { name: 'svchost.exe', pid: 4244, ppid: 824 },
  { name: 'RtkBtManServ.exe', pid: 4604, ppid: 824 },
  { name: 'svchost.exe', pid: 4616, ppid: 824 },
  { name: 'IntelCpHeciSvc.exe', pid: 4624, ppid: 824 },
  { name: 'svchost.exe', pid: 5344, ppid: 824 },
  { name: 'svchost.exe', pid: 5648, ppid: 824 },
  { name: 'svchost.exe', pid: 6064, ppid: 824 },
  { name: 'svchost.exe', pid: 1348, ppid: 824 },
  { name: 'svchost.exe', pid: 1780, ppid: 824 },
  { name: 'svchost.exe', pid: 4092, ppid: 824 },
  { name: 'NisSrv.exe', pid: 6464, ppid: 824 },
  { name: 'sihost.exe', pid: 6716, ppid: 1948 },
  { name: 'svchost.exe', pid: 6724, ppid: 824 },
  { name: 'svchost.exe', pid: 6732, ppid: 824 },
  ... 90 more items ]
pid:0    priority:0      name:[System Process]
pid:6716         priority:0      name:sihost.exe
pid:6724         priority:0      name:svchost.exe
pid:6732         priority:0      name:svchost.exe
pid:6884         priority:0      name:svchost.exe
pid:6988         priority:0      name:taskhostw.exe
pid:6236         priority:-14    name:ctfmon.exe
pid:652  priority:0      name:explorer.exe
pid:6112         priority:-7     name:SynTPEnh.exe
pid:7420         priority:-7     name:SynTPHelper.exe
pid:7744         priority:0      name:svchost.exe
pid:8140         priority:0      name:schtasks.exe
pid:8148         priority:0      name:conhost.exe
pid:7728         priority:0      name:ShellExperienceHost.exe
pid:1804         priority:0      name:SearchUI.exe
pid:7920         priority:0      name:RuntimeBroker.exe
pid:1792         priority:0      name:RuntimeBroker.exe
pid:1264         priority:0      name:SkypeBackgroundHost.exe
pid:1256         priority:0      name:igfxEM.exe
pid:6208         priority:0      name:YourPhone.exe
pid:2368         priority:10     name:SettingSyncHost.exe
pid:8220         priority:0      name:CastSrv.exe
pid:8508         priority:0      name:RuntimeBroker.exe
pid:8864         priority:0      name:RadeonSettings.exe
pid:8916         priority:0      name:RuntimeBroker.exe
pid:2544         priority:0      name:SkypeApp.exe
pid:6812         priority:0      name:RuntimeBroker.exe
pid:2252         priority:0      name:svchost.exe
pid:1144         priority:0      name:smartscreen.exe
pid:7260         priority:0      name:SecurityHealthSystray.exe
pid:7284         priority:0      name:RtkNGUI64.exe
pid:8172         priority:0      name:IDMan.exe
pid:2716         priority:0      name:chrome.exe
pid:5020         priority:0      name:chrome.exe
pid:6004         priority:0      name:chrome.exe
pid:5916         priority:-7     name:chrome.exe
pid:5912         priority:0      name:chrome.exe
pid:5072         priority:0      name:chrome.exe
pid:2132         priority:0      name:chrome.exe
pid:7808         priority:0      name:chrome.exe
pid:9012         priority:0      name:jusched.exe
pid:6520         priority:19     name:chrome.exe
pid:5308         priority:19     name:chrome.exe
pid:8312         priority:0      name:cmd.exe
pid:3016         priority:0      name:conhost.exe
pid:7740         priority:0      name:IEMonitor.exe
pid:1472         priority:0      name:GameBar.exe
pid:292  priority:0      name:RuntimeBroker.exe
pid:1132         priority:0      name:GameBarFT.exe
pid:2224         priority:19     name:chrome.exe
pid:7360         priority:19     name:chrome.exe
pid:1060         priority:19     name:chrome.exe
pid:7816         priority:0      name:chrome.exe
pid:7640         priority:19     name:chrome.exe
pid:7480         priority:19     name:chrome.exe
pid:9016         priority:0      name:jucheck.exe
pid:1996         priority:0      name:notepad++.exe
pid:3248         priority:0      name:WindowsInternal.ComposableShell.Experiences.TextInput.InputApp.exe
pid:4584         priority:19     name:chrome.exe
pid:3540         priority:0      name:chrome.exe
pid:6160         priority:19     name:chrome.exe
pid:7068         priority:0      name:ApplicationFrameHost.exe
pid:8028         priority:0      name:SystemSettings.exe
pid:2752         priority:0      name:PaintStudio.View.exe
pid:6576         priority:0      name:RuntimeBroker.exe
pid:1708         priority:0      name:Calculator.exe
pid:1496         priority:0      name:node.exe
```

**注意:**以上程序将使用 node filename.js 命令编译运行。

**参考:**[https://nodejs . org/API/OS . html # OS _ OS _ get riority _ PID](https://nodejs.org/api/os.html#os_os_getpriority_pid)