# check-tab.md
该项目在HTML5内被创建。

# 项目分析

## 实现内容

- 点击事件
- 下拉框

## 逻辑流程

- 设置默认状态
    - 默认nav样式
    - 默认的列表显示
- 点击事件
    - 隐藏所有样式以及列表
    - 显示当前点击样式以及列表

# 项目详情
重点解析JavaScript实现。

1.  设置默认状态

            var navs = document.querySelectorAll('nav a');  // 获取所有navs
            for(var i = 0; i < navs.length; i ++)   {   // 遍历
                if (key == i) {
                    navs[i].classList.add('active');    // 添加active样式
                    var secId = navs[i].dataset['cont'];    // 获取当前nav的sectionID
                    document.querySelector('#' + secId).style.display = 'block';    // 显示当前section
                }

2. 点击事件
     - 隐藏所有样式以及列表

                navs[i].onclick = function(){   // 添加点击事件
                    var currentNav = document.querySelector('.active'); // 获取当前显示样式的类
                    var currentId = currentNav.dataset['cont']; // 获取该类的sectionid
                    currentNav.classList.remove('active');  // 移除该类样式
                    document.querySelector('#' + currentId).style.display = 'none';   // 隐藏该类section

    - 显示当前点击样式以及列表

                    this.classList.add('active');   // 添加被点击类样式
                    var myId = this.dataset['cont'];
                    document.querySelector('#' + myId).style.display = 'block'; // 显示被点击类section
                }
            } 

# 除了什么错误？
# 学到了什么？

- `box-sizing`_border-box : 表示包括边框的盒子。
- `overflow`_hidden: 裁剪
- `(function)(0)`: 表示立即启用方法。
- `document.querySelect()`空号内
    - 直接输出使用`''`
    - 变量输出直接写入
- 批量样式时使用class添加样式，方便修改
- `document`和`classList`中
    - document获取class需要前置点
    - classList处理class不需要前置点
- 使用`this`关键词代替当前事件

# 项目思考

- 该项目使用变量接受处理

         var navs = document.querySelectorAll('nav a');
> 这样的方式更易于项目的修改。
