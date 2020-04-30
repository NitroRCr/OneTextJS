# OneTextJS

在网页中让任意一个元素显示一个句子，来源于 [OneText](https://github.com/lz233/OneText-Library) 库

然后每间隔10秒（默认）会自动替换为另一个句子

Like this:

![](https://n-source.netlify.com/img/OneTextJS-0.png)

## Usage

首先引入`jQuery`和`OneText.js`

然后将任意元素加上类名：`one-text`，即可应用于该元素，就这样简单。

Like this:

```html
<p class="one-text"></p>
```

### Detail

上述方法只会显示一个句子，如果想要显示作者等信息，大概需要这样：

```html
<div class="one-text">
    <div class="text"></div> <!-- 句子会显示在这里 -->
    <div class="by"></div> <!-- 可选，在这里显示作者 -->
    <div class="from"></div> <!-- 可选，显示出处 -->
    <div class="time"></div> <!-- 可选，显示时间 -->
</div>
```

也就是说，一个`.one-text`元素可以有`.text`, `.by`等子元素，以显示详细信息。

### 通过JS应用

使用JS应用有更多的选项：

```javascript
new OneText(selector, [config]);
```

其中`selector`为`CSS`选择器，与`jQuery`选择器相同。所有与`selector`匹配的元素都会被应用。如果匹配多个元素，则这几个元素显示的内容会是相同的。

`config`为可选的设置，可选参数有：

- `interval`：替换句子的间隔时间，单位为秒，默认值为`10`。当值为`0`时将不会替换

- `autoDash`：是否在作者和出处前添加破折号，默认为`true`

Like this:

```javascript
var oneText = new OneText('.class-name', {interval: 20, autoDash: false});
```

此外，还可以调用每个`OneText`对象的`set`方法来替换为另一个句子：

```javascript
oneText.set();
```

## 特别感谢

所有句子来源于：

[OneText 官方库](https://github.com/lz233/OneText-Library)

[另一个库](https://github.com/2878444090/OneTextLibrary_Netease_Unoffical)