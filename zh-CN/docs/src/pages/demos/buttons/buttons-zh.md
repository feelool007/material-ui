---
title: React 按钮组件
components: 按钮、图标按钮、基础按钮、缩放
---
# 按钮

<p class="description">按钮允许用户只需轻按一下即可采取行动并做出选择。</p>

[按钮](https://material.io/design/components/buttons.html) 传达用户可以执行的操作。 它们通常放置在整个UI中，例如： - 对话 - 模态窗口 - 表单 - 卡片 - 工具栏

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

### 使用图标和标签的按钮

有时您可能希望为某个按钮添加图标以增强应用程序的用户体验，因为我们比纯文本更容易识别徽标。 例如，如果您有删除按钮，则可以使用垃圾箱图标对其进行标记。

{{"演示": "pages/demos/buttons/IconLabelButtons.js"}}

## 自定义按钮

如果您一直在阅读[覆盖文档页面](/customization/overrides/) 但你不自信地跳进来， 以下是如何使用类更改Button的主要颜色的示例， 并使用主题; 以及Bootstrap样式按钮。

{{"演示": "pages/demos/buttons/CustomizedButtons.js"}}

## 复杂按钮

文本按钮，包含按钮，浮动操作按钮和图标按钮构建在同一组件之上：`ButtonBase`。 您可以利用此较低级别组件来构建自定义交互。

{{"演示": "pages/demos/buttons/ButtonBases.js"}}

## 第三方路由库

一个常见的用例是使用按钮触发导航到新页面。 `ButtonBase` 组件提供了一个处理此用例的属性：`component`。 鉴于我们的许多交互式组件都依赖于 `ButtonBase`，你应该这样做 能够在任何地方利用它：

```jsx
import { Link } from 'react-router-dom'
import Button from '@material-ui/core/Button';

<Button component={Link} to="/open-collective">
  链接
</Button>
```

或者如果您想避免属性冲突：

```jsx
import { Link } from 'react-router-dom'
import Button from '@material-ui/core/Button';

const MyLink = props => <Link to="/open-collective" {...props} />

<Button component={MyLink}>
  链接
</Button>
```

*注意：必须创建 `MyLink` 以防止意外卸载。 您可以在[此处](/guides/composition/#component-property)了解有关它的更多信息。*