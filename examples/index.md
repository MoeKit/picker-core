# Demo

---

````css
.basescroller-component {
  display: inline-block;
  position: relative;
  height: 238px;
  overflow: hidden;
  width: 100%;
}

.basescroller-scroller {
  position: absolute;
  left: 0;
  top: 0;
  width: 100%;
  z-index: 1;
}

.basescroller-mask {
  position: absolute;
  left: 0;
  top: 0;
  height: 100%;
  margin: 0 auto;
  width: 100%;
  z-index: 3;
  background: -webkit-gradient(linear,left bottom,left top,from(#f7f7f7),color-stop(0.52,rgba(245,245,245,0)),color-stop(0.48,rgba(245,245,245,0)),to(#f7f7f7));
  background: -webkit-linear-gradient(#f7f7f7,rgba(245,245,245,0)52%,rgba(245,245,245,0)48%,#f7f7f7);
  background: -moz-linear-gradient(#f7f7f7,rgba(245,245,245,0)52%,rgba(245,245,245,0)48%,#f7f7f7);
  background: linear-gradient(#ffffff,rgba(250,250,250,0)52%,rgba(250,250,250,0)48%,#ffffff);
}

.basescroller-item {
  text-align: center;
  font-size: 22px;
  height: 34px;
  line-height: 34px;
  color: #d6d6d6;
}

.basescroller-item.selected {
  color: black;
}

.basescroller-current-indicator {
  width: 100%;
  height: 32px;
  border-top: 1px solid #ccc;
  border-bottom: 1px solid #ccc;
  position: absolute;
  left: 0;
  top: 102px;
  z-index: 3;
}
````

````html
<div id="contact"></div>
````

````javascript
var Picker = require('picker-core');

var contactData = [
  {
    name: '张三',
    value: 0
  },
  {
    name: '李四',
    value: 1
  },
  {
    name: '张三',
    value: 2
  },
  {
    name: '李四',
    value: 3
  },
  {
    name: '张三',
    value: 4
  },
  {
    name: '李四',
    value: 5
  },
  {
    name: '张三',
    value: 6
  },
  {
    name: '李四',
    value: 7
  }
];

var contactScroller = new Picker({
  container: document.getElementById('contact'),
  className: 'contact-scroller',
  data: contactData,
  selectedCallback: function(contact) {
    console.log('Contact value: ' + contact)
  }
});
contactScroller.select(4);
````

````html
<div id="month"></div>
````

````css
.month-scroller {
  height: 100px;
}

.month-scroller .basescroller-item {
  height: 20px;
  line-height: 20px;
  font-size: 14px;
}

.month-scroller .basescroller-current-indicator {
  height: 18px;
  top: 40px;
}
````
````javascript
var Picker = require('picker-core');

var month = [1,2,3,4,5,6,7,8,9,10,11,12];

var monthScroller = new Picker({
  className: 'month-scroller a b c',
  itemHeight: 20,
  itemsNumber: 5
});

monthScroller.setSelectedCallback(function(month) {
  console.log('Month: ' + month);
});

// 要将滚动组件 DOM 元素 append 到页面元素的时候必须用 appendTo 方法
monthScroller.appendTo(document.getElementById('month'));
monthScroller.render(month);
monthScroller.select(3);
````