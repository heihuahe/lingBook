---
title: Handlebar使用记录
tags: 
notebook: 
---
# Handlebar使用记录

## compare
其实和condition的功能很像，但是这个compare只能比较'=='的状态。
**适合在radio控件里判断选中**。
```
<label>
    <input name="is_write" type="radio" value="1" {{#compare is_write "1"}}checked{{/compare}}/>
    <span>是</span>
</label>
<label>
    <input name="is_write" type="radio" value="0" {{#compare is_write "0"}}checked{{/compare}}/>
    <span>否</span>
</label>
```

!!!这个有浏览器兼容性问题，谷歌可以，火狐时好时坏，差评！



