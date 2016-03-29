# todo

##list

* amd js package support

* 添加fis3-parser-cssnext支持
  可以参考https://github.com/lys623/fis3-parser-cssnext

* test match image
```js
// 所有图片加 hash
    fis.match('image', {
        useHash: true
    });
```
* test 发布开始事件，滤掉一些不发布的文件
```js
 fis.on('release:start', function (ret) {
        var src = ret.src;
        Object.keys(src).forEach(function (key) {
            var file = src[key];
            // 对于没有编译的预处理语言的样式文件不输出
            if (file.isCssLike && file.rExt === file.ext && file.ext !== '.css') {
                file.release = false;
            }
        });
    });
```
