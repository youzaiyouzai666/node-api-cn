<!-- YAML
added: v0.0.2
changes:
  - version: v10.0.0
    pr-url: https://github.com/nodejs/node/pull/12562
    description: The `callback` parameter is no longer optional. Not passing
                 it will throw a `TypeError` at runtime.
  - version: v7.6.0
    pr-url: https://github.com/nodejs/node/pull/10739
    description: The `path` parameter can be a WHATWG `URL` object using `file:`
                 protocol. Support is currently still *experimental*.
  - version: v7.0.0
    pr-url: https://github.com/nodejs/node/pull/7897
    description: The `callback` parameter is no longer optional. Not passing
                 it will emit a deprecation warning with id DEP0013.
-->

* `path` {string|Buffer|URL}
* `callback` {Function}
  * `err` {Error}

异步地移除文件或符号链接。
`callback` 只有一个参数 `err`。

```js
// 假设 'path/file.txt' 是一个普通文件。
fs.unlink('path/file.txt', (err) => {
  if (err) throw err;
  console.log('文件已删除');
});
```

`fs.unlink()` 不能移除目录。
要移除目录可使用 [`fs.rmdir()`]。

参见 unlink(2)。

