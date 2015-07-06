# picker

---

[![spm version](http://moekit.com/badge/picker-core)](http://moekit.com/package/picker-core)

滚动选择组件。

Thx to: http://spmjs.io/package/anima-basescroller

---


## Usage

```js
var Picker = require('picker-core');
var nameScroller = new Picker(options);

// use Picker
```

## API

### 实例化选项 options

* container `DOM Object` 组件插入的容器 *[optional]*
* data `array<string|number|object>` 组件数据集 *[optional]*
 * object 包含 name 和 value，表示显示值和实际取值
* selectedCallback `function` 选中后的回调函数，回调参数有两个： *[optional]*
 * current 当前选中的值
 * prev 之前的值
* itemHeight `number` 每个可选项的高度值，单位 px，默认值为 34。添加此选项需要修改样式表中 .scroller-item 下的 height 和 line-height 为 __itemHeight__；.current-indicator 下的 height 为 __itemHeight - 2__（1px 的 border-top 和 border-bottom）。同时建议设置 .scroller-item 合适的 font-size。  *[optional]*
* itemsNumber `number` 组件可见条目的数量，__必须为奇数__，默认值为 7。添加此选项需要修改样式表中 .scroller-component 的 height 为 __itemsNumber * itemHeight__；以及 .current-indicator 下的 top 为 __itemHeight * (itemsNumber - 1) / 2__。 *[optional]*
* className `string` 组件元素 class，用于自定义组件样式，支持以空格分隔的多个 class *[optional]*

### 实例方法

* selectByIndex(index) 通过索引选择一项
 * @param index {number} 非负索引值 __*[required]*__
* select(value) 通过值选中一项
 * @param value {string|number} __*[required]*__
* selectThenCallback(value) 选中后注册的回调函数，参数同 select
* getValue() 获取当前的选中值
* setSelectedCallback(selectedCallback) 设置选中后的回调函数，传入回调函数的参数同实例化选项中的 selectedCallback
* render(data) 重新渲染组件，参数 data 同实例化选项中的 data
* appendTo(container) 将组件插入到一个 DOM 元素中
