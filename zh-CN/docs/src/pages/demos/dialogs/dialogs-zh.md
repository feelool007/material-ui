---
title: React对话框组件
components: 对话框、对话框标题、对话框内容、对话框内容文本、对话框操作、幻灯片
---
# 对话框

<p class="description">对话框用来给用户一个任务，可以提示关键信息、可以让用户进行确认、或者包含多个任务。</p>

[对话框](https://material.io/design/components/dialogs.html) 是 [模态](/utils/modal/) 窗体的一种类型, 通过显示在应用程序内容的前面，来提供关键信息的显示，或者要求用户进行确认和判断。 对话框在出现时会禁用应用程序的所有功能, 并在屏幕上保持固定, 直到被确认、被取消或已采取其他必要的操作。

对话框会带有目的性地中断用户体验，请谨慎使用。

## 单对话框

单对话框可以提供有关列表项的详细信息或操作。 例如, 它们可以显示头像、图标、解释或交互操作 (如添加帐户)。

Touch mechanics: - Choosing an option immediately commits the option and closes the menu - Touching outside of the dialog, or pressing Back, cancels the action and closes the dialog

{{"demo": "pages/demos/dialogs/SimpleDialog.js"}}

## Alerts

Alerts are urgent interruptions, requiring acknowledgement, that inform the user about a situation.

Most alerts don't need titles. They summarize a decision in a sentence or two by either: - Asking a question (e.g. "Delete this conversation?") - Making a statement related to the action buttons

Use title bar alerts only for high-risk situations, such as the potential loss of connectivity. Users should be able to understand the choices based on the title and button text alone.

If a title is required:

- Use a clear question or statement with an explanation in the content area, such as "Erase USB storage?".
- Avoid apologies, ambiguity, or questions, such as “Warning!” or “Are you sure?”

{{"demo": "pages/demos/dialogs/AlertDialog.js"}}

You can also swap out the transition, the next example uses `Slide`.

{{"demo": "pages/demos/dialogs/AlertDialogSlide.js"}}

## Confirmation dialogs

Confirmation dialogs require users to explicitly confirm their choice before an option is committed. For example, users can listen to multiple ringtones but only make a final selection upon touching “OK.”

Touching “Cancel” in a confirmation dialog, or pressing Back, cancels the action, discards any changes, and closes the dialog.

{{"demo": "pages/demos/dialogs/ConfirmationDialog.js"}}

## Full-screen dialogs

{{"demo": "pages/demos/dialogs/FullScreenDialog.js"}}

## Form dialogs

Form dialogs allow users to fill out form fields within a dialog. For example, if your site prompts for potential subscribers to fill in their email address, they can fill out the email field and touch 'Submit'

{{"demo": "pages/demos/dialogs/FormDialog.js"}}

## Responsive full-screen

You may make a `Dialog` responsively full screen the dialog using `withMobileDialog`. By default, `withMobileDialog()(Dialog)` responsively full screens *at or below* the `sm` [screen size](/layout/basics/). You can choose your own breakpoint for example `xs` by passing the `breakpoint` argument: `withMobileDialog({breakpoint: 'xs'})(Dialog)`.

{{"demo": "pages/demos/dialogs/ResponsiveDialog.js"}}

## Accessibility

Be sure to add `aria-labelledby="id..."`, referencing the modal title, to the `Dialog`. Additionally, you may give a description of your modal dialog with the `aria-describedby="id..."` property on the `Dialog`.

## Scrolling long content

When dialogs become too long for the user’s viewport or device, they scroll. - `scroll=paper` the content of the dialog scrolls within the paper element. - `scroll=body` the content of the dialog scrolls within the body element.

Try the demo below to see what we mean:

{{"demo": "pages/demos/dialogs/ScrollDialog.js"}}