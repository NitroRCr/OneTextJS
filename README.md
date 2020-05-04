# OneTextJS

在网页中让任意一个元素显示一个句子，来源于 [一言](https://github.com/lz233/OneText-Library) 库

然后每间隔20秒（默认）会自动替换为另一个句子

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

- `interval`：替换句子的间隔时间，单位为秒，默认值为`20`。当值为`0`时将不会替换
- `autoDash`：是否在作者和出处前添加破折号，默认为`true`
- `libs`：选用的库。数组，在`['official', 'netease', 'april', 'ext']`中任选一个或多个。默认为`['official', 'april']`（detail）或者 `['official', 'netease', 'april', 'ext']`。

Like this:

```javascript
var oneText = new OneText('.class-name', {interval: 30, autoDash: false, libs: ['official', 'ext']});
```

此外，还可以调用每个`OneText`对象的`set`方法来替换为另一个句子：

```javascript
oneText.set();
```

### Libs

- official：[lz差不多是条咸鱼了](https://github.com/lz233)的[OneText 官方库](https://github.com/lz233/OneText-Library)，

- netease：[imbrighter](https://github.com/2878444090)的[OneTextLibrary_Netease_Unoffical](https://github.com/2878444090/OneTextLibrary_Netease_Unoffical)

- april：[lz已经是条咸鱼了](https://github.com/XiaoMengXinX)的[OneText-Library](https://github.com/XiaoMengXinX/OneText-Library)中的`april.json`

- ext：动态调用[Hitokoto](https://hitokoto.cn/)的`API`

  所有的句子来源于以上的库，特别感谢以上的库