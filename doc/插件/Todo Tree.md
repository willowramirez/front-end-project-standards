<!--
 * @LastEditors: Tao Yang
 * @Description: 暂无描述
 * @FilePath: /front-end-project-standards/doc/插件/Todo Tree.md
 * @Date: 2022-06-12 19:39:16
 * @LastEditTime: 2022-06-12 20:22:04
 * @Author: Tao Yang
-->
### 仓库地址
[GitHub](https://github.com/Gruntfuggly/todo-tree)

### 配置规范
```json
  // settings.json
  {
    // ...,
    "todo-tree.regex.regex": "(\/\/|#|<!--|;|\/\\*|^|^\\s*(-|\\d+.))\\s*($TAGS)",
    "todo-tree.general.tags": [
      "TODO",
      "FIXME",
      "BUG",
      "[ ]",
      "[x]"
    ],
    "todo-tree.highlights.customHighlight" : {
      "TODO" : {
        "gutterIcon" : true,
        "icon" : "check",
        "foreground" : "#FFEA00",
        "type" : "whole-line",
        "iconColour" : "#FFEA00",
        "fontWeight" : "600",
      },
      "FIXME" : {
        "gutterIcon" : true,
        "icon" : "beaker",
        "foreground" : "#FF69B4",
        "type" : "tag",
        "iconColour" : "#FF69B4",
        "fontWeight" : "600"
      },
      "BUG": {
        "gutterIcon": true,
        "icon": "bug",
        "foreground": "#EE4B2B",
        "type": "tag",
        "iconColour": "#EE4B2B",
        "fontWeight": "600"
      },
      "[ ]": {
        "gutterIcon": true,
        "icon": "tasklist",
        "foreground": "#FFFFFF",
        "type": "tag",
        "iconColour": "#FFFFFF",
        "fontWeight": "600"
      },
      "[x]": {
        "gutterIcon": true,
        "icon": "tasklist",
        "foreground": "#000000",
        "type": "tag",
        "iconColour": "#000000",
        "fontWeight": "600",
        // "type": "whole-line",
        // "textDecoration": "line-through",
      },
    },
  }
```