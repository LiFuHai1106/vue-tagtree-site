# 介绍

[![vue](https://img.shields.io/badge/vue-2.6.11-brightgreen.svg)](https://github.com/vuejs/vue)
[![element-ui](https://img.shields.io/badge/element--ui-2.14.1-brightgreen.svg)](https://github.com/ElemeFE/element)
[![GitHub stars](https://img.shields.io/github/stars/LiFuHai1106/vue-tagtree.svg?style=social&label=Stars)](https://github.com/PanJiaChen/vue-element-admin)

<!-- <CodingAD /> -->

[vue-tagtree](https://github.com/LiFuHai1106/vue-tagtree) 是一个树形选择器，它基于 [vue](https://github.com/vuejs/vue) 和 [element-ui](https://github.com/ElemeFE/element)实现，支持多选和单选。

## 预览
[https://lifuhai1106.github.io/vue-tagtree-site/tagtree/tagtree.html](https://lifuhai1106.github.io/vue-tagtree-site/tagtree/tagtree.html)

## 安装和使用

#### 1、npm

```bash
# 安装
npm install vue-tagtree

# 使用
<tagtree 
        title="栏目选择"
        width="300"
        :dataList="columnList"
        :props="defaultProps"
        nodeKey="subjectUuid"
></tagtree>

import tagtree from 'vue-tagtree'
import 'vue-tagtree/dist/tagtree.css'
export default {
  components: {
    tagtree
  },
  data() {
    return {
      defaultProps: {
        label: "name",
        children: "subjectList",
      },
      columnList: [
        {
          name: "栏目1",
          subjectUuid: "1",
          subjectList: [
            {
              name: "栏目1-1",
              subjectUuid: "1-1",
            },
          ],
        },
        {
          name: "栏目2",
          subjectUuid: "2",
          subjectList: [],
        },
      ]
    };
  }
};
```

2、html

```
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
    <link rel="stylesheet" href="https://unpkg.com/element-ui/lib/theme-chalk/index.css">
    <link rel="stylesheet" href="tagtree.css">
    <script src="https://unpkg.com/vue/dist/vue.js"></script>
    <script src="https://unpkg.com/element-ui/lib/index.js"></script>
    <script src="tagtree.umd.js"></script>
</head>

<body>
    <div id="app">
        <tagtree title="栏目选择" width="300" :data-list="columnList" :props="defaultProps" node-key="subjectUuid"></tagtree>
    </div>

    <script>
        new Vue({
            el: '#app',
            components: {
                tagtree
            },
            data: function() {
                return {
                    defaultProps: {
                        label: "name",
                        children: "subjectList",
                    },
                    columnList: [{
                        name: "栏目1",
                        subjectUuid: "1",
                        subjectList: [{
                            name: "栏目1-1",
                            subjectUuid: "1-1",
                        }, ],
                    }, {
                        name: "栏目2",
                        subjectUuid: "2",
                        subjectList: [],
                    }, ]
                }
            },
            methods: {}
        })
    </script>
</body>

</html>
```

## API

##### 1、Attributes属性

| 属性             | 说明                   | 类型    | 默认值                                 |
| ---------------- | ---------------------- | ------- | -------------------------------------- |
| title            | 弹窗标题               | String  | 如“栏目选择”                           |
| width            | 框的宽度               | String  | “800”                                  |
| dialogWidth      | 弹窗宽度               | String  | “40%”                                  |
| nodeKey          | 节点id                 | String  | “Id”                                   |
| dataList         | 数据，必填             | Array   |                                        |
| defaultChecked   | 默认选中节点，id数组   | Array   | 如["1","2"]                            |
| defaultExpandAll | 节点是否全部展开       | Boolean | false                                  |
| dialogModal      | 开启遮罩层             | Boolean | true                                   |
| props            | 自定义树节点属性，必填 | Object  | { label: "label",children: "children"} |
| checkStrictly    | 父子节点是否相互关联   | Boolean | true                                   |
| tagClosable      | 标签是否可关闭         | Boolean | true                                   |
| dialogLoading    | 弹窗loading            | Boolean | false                                  |
| disableChildren  | 父节点选中禁用子节点   | Boolean | false                                  |
| disableParent    | 禁用所有父节点         | Boolean | false                                  |
| oneChecked       | 单选                   | Boolean | false                                  |

##### 2、Events事件

| 事件名             | 说明              | 值         |
| ------------------ | ----------------- | ---------- |
| @update-data       | 选中后的值        |            |
| @showDialogTagtree | 说明点击了tagtree | 可赋值true |

