<!-- YAML
added: v0.7.9
-->

* {string}

返回平台特定的路径片段分隔符：

* Windows 上是 `\`。
* POSIX 上是 `/`。

例如，在 POSIX 上：

```js
'foo/bar/baz'.split(path.sep);
// 返回: ['foo', 'bar', 'baz']
```

在 Windows 上：

```js
'foo\\bar\\baz'.split(path.sep);
// 返回: ['foo', 'bar', 'baz']
```

在 Windows 上，斜杠字符（`/`）和反斜杠字符（`\`）都可作为路径分隔符。
`path` 的方法只使用反斜杠（`\`）。

