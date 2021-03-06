<!-- YAML
added: v7.1.0
changes:
  - version: v8.0.0
    pr-url: https://github.com/nodejs/node/pull/10236
    description: The `source` parameter can now be a `Uint8Array`.
-->

* `source` {Buffer|Uint8Array} `Buffer` 或 `Uint8Array`。
* `fromEnc` {string} 当前字符编码。
* `toEnc` {string} 目标字符编码。

将指定的 `Buffer` 或 `Uint8Array` 从一个字符编码重新编码到另一个字符，并返回新的 Buffer。

如果 `fromEnc` 或 `toEnc` 指定了无效的字符编码，或者无法从 `fromEnc` 转换为 `toEnc`，则抛出异常。

`buffer.transcode()` 支持的字符编码有 `'ascii'`、`'utf8'`、`'utf16le'`、`'ucs2'`、`'latin1'` 与 `'binary'`。

如果指定的字节序列无法用目标字符编码表示，则转码过程会使用替代的字符。例如：

```js
const buffer = require('buffer');

const newBuf = buffer.transcode(Buffer.from('€'), 'utf8', 'ascii');
console.log(newBuf.toString('ascii'));
// 输出: '?'
```

因为欧元符号（`€`）无法在 US-ASCII 中表示，所以在转码 `Buffer` 时使用 `?` 代替。

该属性是在 `require('buffer')` 返回的 `buffer` 模块上，而不是在 `Buffer` 全局变量或 `Buffer` 实例上。

