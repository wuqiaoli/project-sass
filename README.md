## 项目介绍
主要记录scss 的常用功能

### 变量的声明与引用
    $highlight-color: blue  ; 
    $weight-bold:500;
    $font-size-20:20px;
    .syntax1{
        color: $highlight-color;  // 变量引用
        font-weight: $weight-bold;//变量引用
        font-size: $font-size-20;//变量引用
        margin-bottom: 20px;
    }

### css @import 与 sass @import 区别
    css @import 执行顺序：后果是只有执行到@import时，浏览器才会去下载其他css文件，这导致页面加载起来特别慢。
    sass @import 执行顺序：在生成css文件时就把相关文件导入进来

### 嵌套CSS 规则
    <div class="syntax3">
        <h1>嵌套CSS 规则</h1>
        <h2>h1h1h1h1h1h1h1h1h1h1</h2>
        <h3>h2h2h2h2h2hh2hh2h2h2hh2</h3>
        <h4>h3h3h3h3h3hh3h3h3h3h</h4>
        <div class="syntax3-solid">父选择器的标识符&;</div>
	</div>
    .syntax3{
        background-color: #eaf8ff;
        padding: 20px;
        border-radius: 10px;
        margin-bottom: 20px;
        h1,h2,h3,h4{
            color:#009848 ;
        }
        &-solid{
            border-bottom: 1px dashed #9c9c9c;
            &:hover{
                border-color: $highlight-color;
                color: #009848;
                cursor: pointer;
            }
        }
    }

### 混合器
    <div class="syntax4">
        <h1>混合器</h1>
        <h2>混合器传参#ff7216</h2>
        <h3>混合器传参#18acff</h3>
        <h4>默认参数值#fd1d1d</h4>
    </div>
    @mixin content-bg {
        background-color: #fff4ec;
        padding: 20px;
        border-radius: 10px;
    }

    @mixin content-color($color:#fd1d1d) {
        color: $color
    }
    .syntax4{
        @include content-bg;
        h1{
            @include content-color(#ff7216);
        }
        h2{
            @include content-color(#ff7216);
        }
        h3{
            @include content-color(#18acff);
        }
        h4{
            @include content-color;
        }
    }
