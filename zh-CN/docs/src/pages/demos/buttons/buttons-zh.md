---
title: React 按钮组件
components: 按钮、图标按钮、基础按钮、缩放
---
# 按钮

<p class="description">按钮允许用户只需轻按一下即可采取行动并做出选择。</p>

[按钮](https://material.io/design/components/buttons.html) 传达用户可以执行的操作。 它们通常放置在整个UI中，例如： - 对话 - 模态窗口 - 形式 - 卡片 - 工具栏

## 文本按钮

[文本按钮](https://material.io/design/components/buttons.html#text-button) 通常用于不太明显的操作, 包括那些位于:

- 在对话框中
- 在卡片

在卡片中，文本按钮有助于保持对卡片内容的重视。

{{"演示": "pages/demos/buttons/TextButtons.js"}}

## 轮廓按钮

[轮廓按钮](https://material.io/design/components/buttons.html#outlined-button) 是中等强调按钮。 它们包含重要的操作， 但不是应用程序中的主要操作。

### 备选方案

轮廓按钮也是包含按钮的低重点替代品， 或更高的重点替代文本按钮。

{{"演示": "pages/demos/buttons/OutlinedButtons.js"}}

## 控制按钮

[控制按钮](https://material.io/design/components/buttons.html#contained-button) 高度强调, 区别于他们使用的海拔和填充。 它们包含对应用程序具有主要作用的操作。

此演示的最后一个示例显示了如何使用上传按钮。

{{"演示": "pages/demos/buttons/ContainedButtons.js"}}

## 浮动操作按钮

[浮动动作按钮](https://material.io/design/components/buttons-floating-action-button.html) (晶圆) 在屏幕上执行主要的或最常用的操作。 它出现在所有屏幕内容的前面, 通常作为圆形形状, 其中心有一个图标。 工厂有三种类型: 常规、迷你和扩展。

如果它是最适合呈现屏幕主要操作的方式，则仅使用FAB。

每个屏幕仅建议一个浮动操作按钮来表示最常见的操作。

{{"演示": "pages/demos/buttons/FloatingActionButtons.js"}}

默认情况下，浮动操作按钮会在屏幕上显示为扩展材料。

跨越多个横向屏幕（例如标签式屏幕）的浮动操作按钮应该短暂消失， 然后如果其动作改变则重新出现。

可以使用缩放转换来实现此目的。 注意，既然退出和进入 动画同时被触发，我们使用`enterDelay`来允许传出的浮动动作按钮 动画在新人进入之前完成。

{{"暗示": "pages/demos/buttons/FloatingActionButtonZoom.js"}}

## 图标按钮

图标按钮通常位于应用栏和工具栏中。

图标也适用于允许选择单个选项的切换按钮或 取消选择，例如向项目添加或删除星标。

{{"演示": "pages/demos/buttons/IconButtons.js"}}

## 尺寸

花式更大或更小的按钮？ 使用 `size` 或 `mini` 属性。

{{"演示": "pages/demos/buttons/ButtonSizes.js"}}

### Buttons with icons and label

Sometimes you might want to have icons for certain button to enhance the UX of the application as we recognize logos more easily than plain text. For example, if you have a delete button you can label it with a dustbin icon.

{{"demo": "pages/demos/buttons/IconLabelButtons.js"}}

## Customized Buttons

If you have been reading the [overrides documentation page](/customization/overrides/) but you are not confident jumping in, here are examples of how you can change the main color of a Button using classes, and using a theme; and of a Bootstrap style Button.

{{"demo": "pages/demos/buttons/CustomizedButtons.js"}}

## Complex Buttons

The Text Buttons, Contained Buttons, Floating Action Buttons and Icon Buttons are built on top of the same component: the `ButtonBase`. You can take advantage of this lower level component to build custom interactions.

{{"demo": "pages/demos/buttons/ButtonBases.js"}}

## Third-party routing library

One common use case is to use the button to trigger a navigation to a new page. The `ButtonBase` component provides a property to handle this use case: `component`. Given that a lot of our interactive components rely on `ButtonBase`, you should be able to take advantage of it everywhere:

```jsx
import { Link } from 'react-router-dom'
import Button from '@material-ui/core/Button';

<Button component={Link} to="/open-collective">
  Link
</Button>
```

or if you want to avoid properties collisions:

```jsx
import { Link } from 'react-router-dom'
import Button from '@material-ui/core/Button';

const MyLink = props => <Link to="/open-collective" {...props} />

<Button component={MyLink}>
  Link
</Button>
```

*Note: Creating `MyLink` is necessary to prevent unexpected unmounting. You can read more about it [here](/guides/composition/#component-property).*