今天在[鸿神](http://blog.csdn.net/lmj623565791)公众号看到一篇自定义view的文章，效果还是很不错的，唯一的缺点就是文字颠倒了，本想给作者提个pre，可惜作者并没有将项目上传至github，于是自己建了一个。[原博客在此](http://www.jianshu.com/p/fe65f5d7a60b)，  我想作者可以谅解吧O(∩_∩)O~

- 原来的效果图

![原来的效果图](http://upload-images.jianshu.io/upload_images/2144156-e91c62262c75ceb0?imageMogr2/auto-orient/strip)

- 修改后的效果图

![修改后的效果图](http://img.blog.csdn.net/20161010175352223)

- 代码对比
```java
for (int i = 0; i < 12; i++) {
    String number = 6 + i < 12 ? String.valueOf(6 + i) : (6 + i) > 12
            ? String.valueOf(i - 6) : "12";
    mCanvas.save();
    mCanvas.translate(0, mRadius * 5.5f / 7);
    mCanvas.rotate(-i * 30);
    mCanvas.drawText(number, 0, 0, mPointerPaint);
    mCanvas.restore();
    mCanvas.rotate(30);
}
```
```java
for (int i = 0; i < 12; i++) {
    String number = 6 + i < 12 ? String.valueOf(6 + i) : (6 + i) > 12
            ? String.valueOf(i - 6) : "12";
    mCanvas.drawText(number, 0, mRadius * 5.5f / 7, mPointerPaint);
    mCanvas.rotate(30);
}
```
