# 一个切换效果


需要引用 `jquery`

切换的效果由鼠标放到 类 `.ke-switch-title` 的子元素触发, 使用是 find ，而不是
**children**, 所以要注意子元素中 类`item`的使用



### 示例

[点击打开测试链接](https://demo.jsjiaocheng.com/001-base-switch/)

### html 结构

```html
<div class="  ke-switch">
	<div class="ke-switch-title">
		<a class="item" href="#">切换1</a>
		<a class="item" href="#">切换2</a>
		<a  href="#">more</a>
	</div>

	<div class="ke-switch-con">
		<div class="item">
			内容1
		</div>

		<div class="item">
			内容2
		</div>

	</div>
</div>
```




### js 代码
```js
$(function () {
	$(".ke-switch").each(function (n) {

		$(this).find('.ke-switch-title .item').eq(0).addClass('hover');
		$(this).find('.ke-switch-con .item').hide().eq(0).addClass('hover').show();

		$(".ke-switch").eq(n).find('.ke-switch-title .item').each(function (m) {
			$(this).hover(function () {
				$(".ke-switch").eq(n).find('.ke-switch-title .item').removeClass('hover').eq(m).addClass('hover');
				$(".ke-switch").eq(n).find('.ke-switch-con .item').hide().eq(m).show();
			});
		});

	});
});

```
