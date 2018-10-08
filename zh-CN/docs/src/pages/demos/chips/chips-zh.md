---
title: React纸片组件
components: 纸片, 纸片视图
---
# 纸片

<p class="description">纸片视图是用来表示输入框、属性或操作的紧凑元素。</p>

[纸片](https://material.io/design/components/chips.html) 允许用户输入信息、进行选择、筛选内容或触发操作。

虽然我们将纸片包含在这里作为独立组件，但更常见的作法是用在表单中作为一种用户输入，因此本篇演示的内容并不会显示具体的上下文关联内容。

## 纸片, 纸片视图

以下是纸片的一个例子, 使用了图像头像, SVG 图标头像, "字母" 和 (字符串) 头像。

- 带有 `onClick` 属性的纸片定义了获得焦点时更改外观，尝试鼠标进行悬浮, 然后单击。
- Chips with the `onDelete` property defined will display a delete icon which changes appearance on hover.

{{"demo": "pages/demos/chips/Chips.js"}}

### Outlined Chips

Outlined chips offer an alternative style.

{{"demo": "pages/demos/chips/OutlinedChips.js"}}

## Chip Playground

{{"demo": "pages/demos/chips/ChipsPlayground.js"}}

## Chip array

An example of rendering multiple Chips from an array of values. Deleting a chip removes it from the array. Note that since no `onClick` property is defined, the Chip can be focused, but does not gain depth while clicked or touched.

{{"demo": "pages/demos/chips/ChipsArray.js"}}