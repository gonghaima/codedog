# 自适应的椭圆

## 椭圆

给元素设置相同宽高以及一半长度的 border-radius，可以得到一个圆形。

我们期望能达到这个效果：宽高相等，显示为一个圆；宽高不等，显示一个椭圆。

说到 border-radius，有一个鲜为人知的真相：他可以 **单独指定水平和垂直半径**，只要用一个斜杠 `/` 分割这两个值即可。

```css
.myDiv {
  width: 150px;
  height: 200px;
  background: red;
  border-radius: 50% / 50%;
}
```

## 半椭圆

border-radius 对应的各个展开式属性（如果要对其分别设置水平和垂直半径，不需要用 `/`，空格即可）：

- border-top-left-radius
- border-top-right-radius
- border-bottom-right-radius
- border-bottom-left-radius

真正简洁的方法还是使用 border-radius 这个简写属性，我们可以向它一次性提供用空格分开的多个值。当 border-radius 的值为 10px / 5px 20px 时，其效果相当于 10px 10px 10px 10px / 5px 20px 5px 20px。

```html
<style>
  .myDiv {
    width: 150px;
    height: 200px;
    background: red;
    border-radius: 50% / 100% 100% 0 0;
  }
</style>
<div class="myDiv"></div>
```

## 四分之一椭圆

要创建一个四分之一椭圆，**其中一个角的水平和垂直半径值都需要是 100%，而其他三个角都不能设为圆角**。

```html
<style>
  .myDiv {
    width: 150px;
    height: 200px;
    background: red;
    border-top-left-radius: 100%;

  /*  还可以这样
    border-top-left-radius: 100% 100%;
    border-radius: 100% 0 0 0;*/
  }
</style>
<div class="myDiv"></div>
```