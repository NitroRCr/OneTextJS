# OneTextJS

在网页中让任意一个元素显示一个句子，来源于 [OneText](https://github.com/lz233/OneText-Library) 库

然后每间隔10秒会自动替换为另一个句子

Like this:

![](https://n-source.netlify.com/img/OneTextJS-0.png)

## Usage

首先引入`jQuery`和`OneText.js`

然后将任意元素加上类名：`one-text`，即可应用于该元素，就这样简单。

也可以通过`JS`：

```javascript
var oneText = new OneText(selector);
```

其中`selector`为`CSS`选择器，与`jQuery`选择器相同。

## 特别感谢

所有句子来源于：

[OneText 官方库](https://github.com/lz233/OneText-Library)

[另一个库](https://github.com/2878444090/OneTextLibrary_Netease_Unoffical)