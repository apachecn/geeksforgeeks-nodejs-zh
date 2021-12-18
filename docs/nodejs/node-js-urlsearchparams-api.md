# node . js urlsearchparams API

> 哎哎哎:# t0]https://www . geeksforgeeks . org/node-js-urlsearchparams-API/

Node.js 是一个开源项目，广泛用于动态 web 应用程序的开发。Node.js 中的 URLSearchParams API 允许对 URL 查询进行读写操作。

URLSearchParams 类是一个全局对象，与以下四个构造函数之一一起使用。

**施工人员:**

1.  **新的 URLSearchParams():** 无参数构造函数实例化新的空 URLSearchParams 对象。
2.  **new URLSearchParams(string):** Accepts a string as an argument to instantiate a new URLSearchParams object.

    ```js
    var params = new URLSearchParams('user=abc&q=xyz');
    console.log(params.get('user'));
    console.log(params.get('q'));
    ```

    **输出:**

    ```js
    abc
    xyz
    ```

3.  **new URLSearchParams(obj):** Accepts an object with a collection of key-value pairs to instantiate a new URLSearchParams object. The key-value pair of obj are always coerced to strings. Duplicate keys are not allowed.

    ```js
    const params = new URLSearchParams({
      user: 'ana',
      course: ['math', 'chem', 'phys']
    });
    console.log(params.toString());
    ```

    **输出:**

    ```js
    user=ana&course=math%2Cchem%2Cphys
    ```

4.  **new URLSearchParams(iterable):** Accepts an iterable object having a collection of key-value pairs to instantiate a new URLSearchParams object. Iterable can be any iterable object. Since URLSearchParams is iterable, an iterable object can be another URLSearchParams, where the constructor will create a clone of the provided URLSearchParams. Duplicate keys are allowed.

    ```js
    // Using a Map object as it is iterable
    const map = new Map();
    map.set('West Bengal', 'Kolkata');
    map.set('Karnataka', 'Bengaluru');
    params = new URLSearchParams(map);
    console.log(params.toString());
    ```

    **输出:**

    ```js
    West+Bengal=Kolkata&Karnataka=Bengaluru
    ```

**访问网址查询:**

*   **urlSearchParams.get(name):** Returns the value of the first name-value pair that matches with the argument passed. If no such pair exists, null is returned.

    ```js
    const myURL = new URL(
      'https://example.org/?abc=123&abc=526');

    console.log(myURL.searchParams.get('abc'));
    ```

    **输出:**

    ```js
    123
    ```

*   **urlSearchParams.getAll(name):** Returns all the value of the name-value pair that matches with the argument passed. If no such pair exists, null is returned.

    ```js
    const myURL = new URL(
      'https://example.org/?abc=123&abc=526');
    console.log(myURL.searchParams.getAll('abc'));
    ```

    **输出:**

    ```js
    [ '123', '526' ]
    ```

*   **urlSearchParams.has(name):** Returns true if the argument passed matches with any existing name of the name-value pair else returns false.

    ```js
    const myURL = new URL(
      'https://example.org/?abc=123&xyz=526');
    console.log(myURL.searchParams.has('abc'));
    console.log(myURL.searchParams.has('pqr'));
    ```

    **输出:**

    ```js
    true
    false
    ```

**操纵网址查询:**

*   **urlSearchParams.set(name, value):** Sets the value in the URLSearchParams object associated with name to the specified value. If more than one name-value pairs exists, whose names are same as the ‘name’ argument, then the only value of first matching pair is changed, rest all are removed.

    ```js
    const params = new URLSearchParams(
        'abc=123&xyz=526&abc=258');
    console.log(params.toString());
    params.set('abc', 'opq');
    console.log(params.toString());
    ```

    **输出:**

    ```js
    abc=123&xyz=526&abc=258
    abc=opq&xyz=526
    ```

*   **urlSearchParams.append(name, value):** Appends a new name-value pair to the existing URLSearchParams query.

    ```js
    const params = new URLSearchParams('xyz=123');
    params.append('foo', '789');
    params.append('xyz', 'zoo');
    params.append('foo', 'def');
    console.log(params.toString());
    ```

    **输出:**

    ```js
    xyz=123&foo=789&xyz=zoo&foo=def
    ```

*   **urlSearchParams.delete(name):** Removes all name-value pairs whose name is same as ‘name’ argument.

    ```js
    const params = new URLSearchParams(
      'xyz=123&foo=789&xyz=zoo&foo=def');
    console.log(params.toString());
    params.delete('foo');
    console.log(params.toString());
    ```

    **输出:**

    ```js
    xyz=123&foo=789&xyz=zoo&foo=def
    xyz=123&xyz=zoo
    ```

*   **urlSearchParams.sort():** Sorts the existing name-value pairs in-place by their names using a stable sorting algorithm.

    ```js
    const params = new URLSearchParams(
      'query=node&type=search&abc=programs');
    params.sort();
    console.log(params.toString());
    ```

    **输出:**

    ```js
    abc=programs&query=node&type=search
    ```

*   **urlSearchParams.toString():** Returns the URL search parameters as a string, with characters percent-encoded wherever necessary.

    ```js
    const params = new URLSearchParams(
      'query=node&type=search&passwd[]=3456');
    console.log(params.toString());
    ```

    **输出:**

    ```js
    query=node&type=search&passwd%5B%5D=3456
    ```

**迭代网址查询:**

*   **urlSearchParams.entries():** Returns an iterator over the entry set of the param object.

    ```js
    const params = new URLSearchParams(
        'query=node&type=search&passwd=3456');
    for(var pair of params.entries()) {
       console.log(pair[0]+ '-->'+ pair[1]); 
    }
    ```

    **输出:**

    ```js
    query-->node
    type-->search
    passwd-->3456
    ```

*   **urlSearchParams.keys():** Returns an iterator over the key set of the param object.

    ```js
    const params = new URLSearchParams(
        'query=node&type=search&passwd=3456');
    for(var key of params.keys()) {
       console.log(key); 
    }
    ```

    **输出:**

    ```js
    query
    type
    passwd
    ```

*   **urlSearchParams.values():** Returns an iterator over the value set of the param object.

    ```js
    const params = new URLSearchParams(
        'query=node&type=search&passwd=3456');
    for(var value of params.values()) {
       console.log(value); 
    }
    ```

    **输出:**

    ```js
    node
    search
    3456
    ```

*   **urlSearchParams.forEach(fn[, arg]):** fn is a function invoked for each name-value pair in the query and arg is an object to be used when ‘fn’ is called. It iterates over each name-value pair in the query and invokes the function.

    ```js
    const myURL = new URL(
      'https://example.com/?a=b&c=d&d=z');
    myURL.searchParams.forEach(
      (value, name, searchParams) => {
    console.log(name, value, 
      myURL.searchParams === searchParams);
    });
    ```

    **输出:**

    ```js
    a b true
    c d true
    d z true
    ```

*   **urlSearchParams[Symbol.iterator]():**

    ```js
    const params=new URLSearchParams(
        'firstname=john&lastname=beck&gender=male');
    for (const [name, value] of params) {
      console.log(name, value);
    }
    ```

    **输出:**

    ```js
    firstname john
    lastname beck
    gender male

    ```