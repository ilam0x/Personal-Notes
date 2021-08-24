# Javascript

```javascript
const app = {
    mounted() {
      const _this = this.methods
      setTimeout(() => {
        _this.setLines()
      }, 0) 
      _this.setFontSize()
      _this.dialog()
      window.onresize = () => {
        _this.setFontSize()
        _this.setLines()
     }
    },
    methods: {
        setLines(){
        },
        dialog(){  
        },
        setFontSize(){            
        },
        
    }
```



``模板字符串，ES2015新增的符号，代替+拼接

```javascript
setLines() {
    let height = `${ parseInt($('.root').css('height')) / 2 }px`
    $('.line-lang-vertical').css({
        height: `calc(100% + ${ height })`,
        top: `-${ height }`
    })
},
```

## 点击弹出

```html
<span class="herf" herf="./2.png">  
<span class="herf" >  
<div class="dialog-wrapper">
      <div class="dialog">
        <div class="dialog-header">
          <div class="dialog-title"></div>
          <button class="dialog-close" onclick="app.methods.closed()">×</button>
        </div>
        <div class="dialog-body">
```

```javascript
      dialog() {
        $('.herf').click(function () {
          let herf = $(this).attr('herf')
          let html = ''
          // show image
          if (herf.indexOf("png")>0) { //判断有无herf，是否含有
            html = `<img style="width: 100vh;" src="${ herf }" alt="">`
          } else {

          //show text
            html = `<textarea name="" style="width: 100%;" id="" rows="10"></textarea>`
          }
          $('html').css({
            overflow: 'hidden',
            height: '100vh'
          })
          $('.dialog-wrapper').show()
          $('.dialog-title').text($(this).text())
          $('.dialog-body').html(html)
        })
      },
```







# css

```css
.btn button:not(:nth-child(1)) /*不是第一个*/

.node {
  padding: 10px 10px;
  display: inline-flex; /*内联弹性*/
  box-sizing: border-box;/*控制边框大小为设置的长宽不受padding限制*/
  border: 1px #000 solid;
  position: relative;
  background-color: rgb(244, 244, 245);
} 

.short {
  max-width: 200px; /*限制最大宽度*/
}

.node-top {
  width: 100%;
  height: calc(100% + 1rem);/*限制最大宽度 1rem = 16px, 根据根目录自适应*/
  position: absolute;
  left: 0;
  top: 0;
  transform: translateY(-100%);/*默认向下移动*/
  display: flex;
  flex-flow: column; /*flex内元素排列是row还是column*/
  align-items: center;
  justify-content: flex-end;/*flex内元素对齐方式*/
}
```

![image-20210806180339780](C:\Users\User\AppData\Roaming\Typora\typora-user-images\image-20210806180339780.png)

```css
/*线宽度2px,长度rem自适应*/
.line {
  display: inline-flex;
  width: 1rem;
  height: 2px;
  margin-right: 10px;
  background-color: #000;
  position: relative;
}
/*箭头*/
.line.line-top {
  width: 2px;
  height: 1rem;
  margin: 10px 0 0;
}
```

```javascript
let herf = $(this).attr('herf') /*get href value by using jquery*/
```

