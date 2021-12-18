# Node.js process.config 属性

> 原文:[https://www . geesforgeks . org/node-js-process-config-property/](https://www.geeksforgeeks.org/node-js-process-config-property/)

**process.config 属性**是流程模块的内置应用编程接口，用于获取用于编译当前 node.js 代码的配置选项的 JavaScript 表示。

**语法:**

```js
process.config
```

**返回值:**该属性返回一个对象，该对象包含用于编译当前可执行 node.js 的 JavaScript 表示形式的配置。

下面的例子说明了在 Node.js 中 process.config 属性的使用:

**例 1:**

```js
// Node.js program to demonstrate the
// process.config Property

// Include process module
const process = require('process');

// Printing process.config property value
console.log(process.config);
```

**输出:**

```js
{ target_defaults:
   { cflags: [],
     default_configuration: 'Release',
     defines: [],
     include_dirs: [],
     libraries: [] 
   },
  variables:
   { asan: 0,
     build_v8_with_gn: false,
     coverage: false,
     debug_nghttp2: false,
     enable_lto: false,
     enable_pgo_generate: false,
     enable_pgo_use: false,
     force_dynamic_crt: 0,
     host_arch: 'x64',
     icu_data_in: '..\\..\\deps/icu-small\\source/data/in\\icudt64l.dat',
     icu_endianness: 'l',
     icu_gyp_path: 'tools/icu/icu-generic.gyp',
     icu_locales: 'en, root',
     icu_path: 'deps/icu-small',
     icu_small: true,
     icu_ver_major: '64',
     nasm_version: '2.14',
     node_byteorder: 'little',
     node_debug_lib: false,
     node_enable_d8: false,
     node_enable_v8_vtunejit: false,
     node_install_npm: true,
     node_module_version: 64,
     node_no_browser_globals: false,
     node_prefix: '/usr/local',
     node_release_urlbase: 'https://nodejs.org/download/release/',
     node_shared: false,
     node_shared_cares: false,
     node_shared_http_parser: false,
     node_shared_libuv: false,
     node_shared_nghttp2: false,
     node_shared_openssl: false,
     node_shared_zlib: false,
     node_tag: '',
     node_target_type: 'executable',
     node_use_bundled_v8: true,
     node_use_dtrace: false,
     node_use_etw: true,
     node_use_large_pages: false,
     node_use_openssl: true,
     node_use_pch: false,
     node_use_perfctr: true,
     node_use_v8_platform: true,
     node_with_ltcg: true,
     node_without_node_options: false,
     openssl_fips: '',
     openssl_no_asm: 0,
     shlib_suffix: 'so.64',
     target_arch: 'x64',
     v8_enable_gdbjit: 0,
     v8_enable_i18n_support: 1,
     v8_enable_inspector: 1,
     v8_no_strict_aliasing: 1,
     v8_optimized_debug: 0,
     v8_promise_internal_field_count: 1,
     v8_random_seed: 0,
     v8_trace_maps: 0,
     v8_typed_array_max_size_in_heap: 0,
     v8_use_snapshot: true,
     want_separate_host_toolset: 0 
   } 
}

```

**例 2:**

```js
// Node.js program to demonstrate the
// process.config Property

// Include process module
const process = require('process');

// Printing process.config property value
var no_conf = 0;
var conf = process.config;
for (var key in conf) {
    console.log(key);
    var sub_conf = conf[key];

    for (var attr in sub_conf){
        console.log("\t" + attr + "=>" + sub_conf[attr]);
        no_conf++;
    }
}

console.log("total no of configuration available is "
                    + no_conf);
```

**输出:**

```js
target_defaults
        cflags=>
        default_configuration=>Release
        defines=>
        include_dirs=>
        libraries=>
variables
        asan=>0
        build_v8_with_gn=>false
        coverage=>false
        debug_nghttp2=>false
        enable_lto=>false
        enable_pgo_generate=>false
        enable_pgo_use=>false
        force_dynamic_crt=>0
        host_arch=>x64
        icu_data_in=>..\..\deps/icu-small\source/data/in\icudt64l.dat
        icu_endianness=>l
        icu_gyp_path=>tools/icu/icu-generic.gyp
        icu_locales=>en, root
        icu_path=>deps/icu-small
        icu_small=>true
        icu_ver_major=>64
        nasm_version=>2.14
        node_byteorder=>little
        node_debug_lib=>false
        node_enable_d8=>false
        node_enable_v8_vtunejit=>false
        node_install_npm=>true
        node_module_version=>64
        node_no_browser_globals=>false
        node_prefix=>/usr/local
        node_release_urlbase=>https://nodejs.org/download/release/
        node_shared=>false
        node_shared_cares=>false
        node_shared_http_parser=>false
        node_shared_libuv=>false
        node_shared_nghttp2=>false
        node_shared_openssl=>false
        node_shared_zlib=>false
        node_tag=>
        node_target_type=>executable
        node_use_bundled_v8=>true
        node_use_dtrace=>false
        node_use_etw=>true
        node_use_large_pages=>false
        node_use_openssl=>true
        node_use_pch=>false
        node_use_perfctr=>true
        node_use_v8_platform=>true
        node_with_ltcg=>true
        node_without_node_options=>false
        openssl_fips=>
        openssl_no_asm=>0
        shlib_suffix=>so.64
        target_arch=>x64
        v8_enable_gdbjit=>0
        v8_enable_i18n_support=>1
        v8_enable_inspector=>1
        v8_no_strict_aliasing=>1
        v8_optimized_debug=>0
        v8_promise_internal_field_count=>1
        v8_random_seed=>0
        v8_trace_maps=>0
        v8_typed_array_max_size_in_heap=>0
        v8_use_snapshot=>true
        want_separate_host_toolset=>0
total no of configuration available is 65

```

**注意:**以上程序使用`node filename.js`命令编译运行。

**参考:**T2】https://nodejs.org/api/process.html#process_process_config