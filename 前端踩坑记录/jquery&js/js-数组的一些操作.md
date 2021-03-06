---
title: js-数组的一些操作
tags: js
notebook: 前端
---
# js-数组的一些操作
## 1.数据里添加数据
### 1.1.将对象添加到数组，Array.push()
格式大概是这样：**[{},{},{}]**
```
var a = new Array(),
    b = {
      num: '001',
      name: '001的名字'
    };
// 方法1：
a[0] = b //这样有个问题，你要知道这个坐标，index 然后指定赋值。不方便。
// 方法2
a.push(b) // Array.push() 可以将任何数据放到数组里。且按顺序放。
```
效果:
![](https://raw.githubusercontent.com/heihuahe/myGallery/master/noteImage/20190829170256.png)

### 1.2.一次性添加多个数据,push()
```
var arrayStr = ['001'];
arrayStr.push('002', '005')
```
效果：
![](https://raw.githubusercontent.com/heihuahe/myGallery/master/noteImage/20190829173443.png)
### 1.3.将数据添加到数组的开头（指定位置）,unshift()
```
var arrayStr = ['001'];
arrayStr.unshift('002', '005')
```
效果：
![](https://raw.githubusercontent.com/heihuahe/myGallery/master/noteImage/20190829173533.png)

### 1.4.将数组A的内容添加到数组B中,数组B的值发生变化,apply()
```
var arrayA = ['001','002'],
    arrayB = ['010', '011'];
arrayB.push.apply(arrayA,arrayB)
```
效果：
![](https://raw.githubusercontent.com/heihuahe/myGallery/master/noteImage/20190829173644.png)

**注意**：apply中参数顺序的意义是不一样的。比如，我们换个顺序
![](https://raw.githubusercontent.com/heihuahe/myGallery/master/noteImage/20190829173748.png)
总结：可以很明显地看出，**apply(arrayA, arrayB)就是把b的数据添加到A**，其他类比。看文档怎么介绍的：
![](https://raw.githubusercontent.com/heihuahe/myGallery/master/noteImage/20190829174520.png)
### 1.5.将数组A，数组B的内容添加到空数组C中，concat()
```
var arrayA = ['001','002'],
    arrayB = ['010', '011'],
    arrayC = arrayA.concat(arrayB)
```
效果：
![](https://raw.githubusercontent.com/heihuahe/myGallery/master/noteImage/20190829173828.png)

### 1.6 数组里存'键值对'

#### 方法一：push(json对象)
```
// 方法一
arr.push({
    key: value
})
```
效果：
![](https://raw.githubusercontent.com/heihuahe/myGallery/master/noteImage/.1544511983833.png)

#### 方法二：[key]赋值
```
// 方法二
var array = [];
array.push('1');
array['test'] = '2';
array['test2'] = [1,2,3,4,5]
console.log(array)
```
效果：
- 字符串
![](https://raw.githubusercontent.com/heihuahe/myGallery/master/noteImage/.1544511902234.png)
- 数组
![](https://raw.githubusercontent.com/heihuahe/myGallery/master/noteImage/.1544512124621.png)

## 2.数组里删除数据

### 2.1 删除指定数据 splice
```
//删除数组中指定元素
removeByValue(arr, val) {
  for (var i = 0; i < arr.length; i++) {
    if (arr[i] == val) {
      arr.splice(i, 1);
      break;
    }
  }
}
```

## 3. 数组转换
### 3.1 字符串数组转换成数字数组
```
var array = ['1', '2', '3']
array.map(Number) // array = [1,2,3]
```

### 3.2 数组转换成 字符串 `join(分隔符)`
比如：`[1,2,3] => "1,2,3"`
代码：
```
var array = [1,2,3]
var arrayStr = array.join(',') // arrayStr == "1,2,3"
```

然后 反转呢，也很简单。`split(分隔符)`
比如： `[1,2,3] <= "1,2,3"`
代码：
```
var arrayStr = "1,2,3"
var array = arrayStr.split(',') // arrayStr == [1,2,3]
```

### 参考资料
- [Function.prototype.apply()(MDN文档)](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/Function/apply)