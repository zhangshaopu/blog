---
title: Markdown Syntax Guide
date: 2019-03-11
hero: "/images/hero-2.jpg"
excerpt: Sample article showcasing basic Markdown syntax and formatting for HTML elements.
tags: [hugo]
categories: [hugo]

---
This article offers a sample of basic Markdown syntax that can be used in Hugo content files, also it shows whether basic HTML elements are decorated with CSS in a Hugo theme.
![asdf](/images/hero-2.jpg)
<!--more-->

## Headings

The following HTML `<h1>`—`<h6>` elements represent six levels of section headings. `<h1>` is the highest section level while `<h6>` is the lowest.

# H1
## H2
### H3
#### H4
##### H5
###### H6

## Paragraph

Xerum, quo qui aut unt expliquam qui dolut labo. Aque venitatiusda cum, voluptionse latur sitiae dolessi aut parist aut dollo enim qui voluptate ma dolestendit peritin re plis aut quas inctum laceat est volestemque commosa as cus endigna tectur, offic to cor sequas etum rerum idem sintibus eiur? Quianimin porecus evelectur, cum que nis nust voloribus ratem aut omnimi, sitatur? Quiatem. Nam, omnis sum am facea corem alique molestrunt et eos evelece arcillit ut aut eos eos nus, sin conecerem erum fuga. Ri oditatquam, ad quibus unda veliamenimin cusam et facea ipsamus es exerum sitate dolores editium rerore eost, temped molorro ratiae volorro te reribus dolorer sperchicium faceata tiustia prat.

Itatur? Quiatae cullecum rem ent aut odis in re eossequodi nonsequ idebis ne sapicia is sinveli squiatum, core et que aut hariosam ex eat.

## Blockquotes

The blockquote element represents content that is quoted from another source, optionally with a citation which must be within a `footer` or `cite` element, and optionally with in-line changes such as annotations and abbreviations.

#### Blockquote without attribution

> Tiam, ad mint andaepu dandae nostion secatur sequo quae.
> **Note** that you can use *Markdown syntax* within a blockquote.

#### Blockquote with attribution

> Don't communicate by sharing memory, share memory by communicating.
> — <cite>Rob Pike[^1]</cite>


[^1]: The above quote is excerpted from Rob Pike's [talk](https://www.youtube.com/watch?v=PAAkCSZUG1c) during Gopherfest, November 18, 2015.

## Tables

Tables aren't part of the core Markdown spec, but Hugo supports supports them out-of-the-box.

   Name | Age
--------|------
    Bob | 27
  Alice | 23

#### Inline Markdown within tables

| Inline&nbsp;&nbsp;&nbsp;     | Markdown&nbsp;&nbsp;&nbsp;  | In&nbsp;&nbsp;&nbsp;                | Table      |
| ---------- | --------- | ----------------- | ---------- |
| *italics*  | **bold**  | ~~strikethrough~~&nbsp;&nbsp;&nbsp; | `code`     |

## Code Blocks

#### Code block with backticks

```html
html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Example HTML5 Document</title>
</head>
<body>
  <p>Test</p>
</body>
</html>
```

#### Code block with Hugo's internal highlight shortcode
{{< highlight html >}}
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Example HTML5 Document</title>
</head>
<body>
  <p>Test</p>
</body>
</html>
{{< /highlight >}}

## List Types

#### Ordered List

1. First item
2. Second item
3. Third item

#### Unordered List

* List item
* Another item
* And another item

#### Nested list

* Item
1. First Sub-item
2. Second Sub-item

## Other Elements — abbr, sub, sup, kbd, mark

<abbr title="Graphics Interchange Format">GIF</abbr> is a bitmap image format.

H<sub>2</sub>O

X<sup>n</sup> + Y<sup>n</sup> = Z<sup>n</sup>

Press <kbd><kbd>CTRL</kbd>+<kbd>ALT</kbd>+<kbd>Delete</kbd></kbd> to end the session.

Most <mark>salamanders</mark> are nocturnal, and hunt for insects, worms, and other small creatures.

## 图片
![图片描述](http://img.blog.fandong.me/2017-08-26-Markdown-Advance-Video.jpg)

## Markdown嵌套视频
<video id="video" controls="" preload="none" poster="http://img.blog.fandong.me/2017-08-26-Markdown-Advance-Video.jpg">
      <source id="mp4" src="http://img.blog.fandong.me/2017-08-26-Markdown-Advance-Video.mp4" type="video/mp4">
      </video>

```
<video id="video" controls="" preload="none" poster="http://img.blog.fandong.me/2017-08-26-Markdown-Advance-Video.jpg">
      <source id="mp4" src="http://img.blog.fandong.me/2017-08-26-Markdown-Advance-Video.mp4" type="video/mp4">
      </video>
```

## 嵌套bilibili视频

<iframe height="400" width="600" src="//player.bilibili.com/player.html?aid=54774652&cid=95807300&page=1" scrolling="no" border="0" frameborder="no" framespacing="0" allowfullscreen="true"> </iframe>

```
<iframe height="400" width="600" src="//player.bilibili.com/player.html?aid=54774652&cid=95807300&page=1" scrolling="no" border="0" frameborder="no" framespacing="0" allowfullscreen="true"> </iframe>
```



## Markdown嵌套音频
<audio id="audio" controls="" preload="none">
      <source id="mp3" src="http://qiniu.cloud.fandong.me/Music_iP%E8%B5%B5%E9%9C%B2%20-%20%E7%A6%BB%E6%AD%8C%20%28Live%29.mp3">
      </audio>
      

```
<audio id="audio" controls="" preload="none">
      <source id="mp3" src="http://qiniu.cloud.fandong.me/Music_iP%E8%B5%B5%E9%9C%B2%20-%20%E7%A6%BB%E6%AD%8C%20%28Live%29.mp3">
      </audio>
```

## 想在别的地方让别人给你的仓库Star的美好方式
<iframe
    style="margin-left: 2px; margin-bottom:-5px;"
    frameborder="0" scrolling="0" width="100px" height="20px"
    src="https://ghbtns.com/github-btn.html?user=fandongtongxue&repo=fandongtongxue.github.io&type=star&count=true" >
</iframe>

 参数	 必传	 类型	   备注
user	true	String	用户名
repo	true	String	仓库名字
type	true	String	star
count	true	String	数量

```
<iframe
  style="margin-left: 2px; margin-bottom:-5px;"
  frameborder="0" scrolling="0" width="100px" height="20px"
  src="https://ghbtns.com/github-btn.html?user=fandongtongxue&repo=fandongtongxue.github.io&type=star&count=true" >
</iframe>
```