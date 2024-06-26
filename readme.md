## 简介

我本身对玄学就有极大的兴趣爱好,加上祖上也有一些手段传给我(当然不是什么神通)

觉得可以收藏一些书籍,为日后学习钻研、查阅资料提供方便

也希望对这方面有兴趣的朋友可以参考

由于资料都是在网络中查找的 如果有什么错处可以帮我提出来 纠正错误 感激不尽


## 本地安装与提交格式注意事项

本站点采用的 [VitePress](https://vitepress.dev/) 建造

### 请先安装依赖:

[Node.js](https://nodejs.org/en) 版本 18 或更高版本。

#### 安装 pnpm 包管理器

Windows

```sh 
iwr https://get.pnpm.io/install.ps1 -useb | iex
```
MacOS

```sh 
brew install pnpm
```



#### 安装项目依赖

```sh
pnpm install
```



### 启动本地开发预览

```sh
pnpm run dev
```



### 文章目录

其中分为 `山、医、命、相、卜、相关经典` 等文件夹

对应的就是`山篇、医篇、命篇、相篇、卜篇、相关经典`分类

请将书籍放置到相应的目录下



### 提交格式

**书籍名称**:请用原名称替代 `例:道德经.md`

**(可选)书籍内容**:
请在该书籍最上方注明书籍标题,并采用以下格式

```md
---
title: 道德经
editLink: true
---

## 第 1 章

····
```

### 修改侧边栏显示书籍

进入`.vitepress/configs/sidebar.ts`目录

按照如下格式进行配置

```ts
// 灵宠
export function Sidelc() {
  return [
    {
      // text: '灵宠',
      // collapsed: true,
      base: '/灵宠/',
      items: [
        { text: '宠物篇', link: '宠物篇' },
        { text: '植物篇', link: '植物篇' }
      ]
    }
  ]
}
```

:::tip

- `text`:分类名称 (请勿修改)
- `collapsed`: 打开下拉开关选项(请勿修改)
- `base`: "/山/" (请勿修改)
- `items`:该分类下的文件路径配置
  :::

#### 例子

新上传书籍`《宅经》`
分类为`山篇`

请将书籍拖动至`src/山`文件夹下

并且在`.vitepress/configs/sidebar.ts`添加侧边栏路径
配置如下:

```ts
// 灵宠
export function Sidelc() {
  return [
    {
      // text: '灵宠',
      // collapsed: true,
      base: '/灵宠/',
      items: [
        { text: '宠物篇', link: '宠物篇' },
        { text: '植物篇', link: '植物篇' } //[!code ++]
      ]
    }
  ]
}
```

### 检查是否显示

做完上述步骤 **运行**

```sh
pnpm run dev
```

ok 现在就可以看到提交的书籍在侧边栏显示了

### 提交 PR
