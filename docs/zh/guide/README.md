# 介绍

[![vue](https://img.shields.io/badge/vue-2.6.11-brightgreen.svg)](https://github.com/vuejs/vue)
[![element-ui](https://img.shields.io/badge/element--ui-2.14.1-brightgreen.svg)](https://github.com/ElemeFE/element)
[![GitHub stars](https://img.shields.io/github/stars/LiFuHai1106/vue-tagtree.svg?style=social&label=Stars)](https://github.com/PanJiaChen/vue-element-admin)

<!-- <CodingAD /> -->

[vue-tagtree](https://github.com/LiFuHai1106/vue-tagtree) 是一个树形选择器，它基于 [vue](https://github.com/vuejs/vue) 和 [element-ui](https://github.com/ElemeFE/element)实现，支持多选和单选。

## 预览
[https://lifuhai1106.github.io/vue-tagtree-site/tagtree/tagtree.html](https://lifuhai1106.github.io/vue-tagtree-site/tagtree/tagtree.html)

## 安装和使用

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

