# NI 编程指南

[![Next-Innovation](https://img.shields.io/badge/Next-Innovation-blueviolet?style=flat)](https://github.com/FRCNextInnovation) [![standard-readme compliant](https://img.shields.io/badge/readme%20style-standard-brightgreen.svg?style=flat)](https://github.com/RichardLitt/standard-readme) [![Lang](https://img.shields.io/badge/Lang-zh--CN-Green?style=flat)]()

本篇文档是一份用于**Next-Innovation(NI)**内部的程序开发指南。

本篇指南基于以下原则编写:

- 不要因为盲目追求运行速度而忽略了代码的易读性。
- 在不过分降低运行速度的前提下，首要考虑代码易读性。
- 在保证代码易读性的前提下，尽量使用少的语句和字母。

NI的每一位程序开发者都应当在工作中遵循以上约定。 

本篇指南的内容包括: 

1. 推荐的VS-Code插件。
2. 代码风格规范。

![NEXT_Innovation](https://github.com/FRCNextInnovation/NI-Programming-Guide/blob/main/assets/Logo_Purple_Word_Transparent.png)

## 目录
- [NI 编程指南](#ni-编程指南)
  * [1. VS-Code-插件](#1-vs-code-插件)
  * [2. 代码风格规范](#2-代码风格规范)
    + [2.1 源文件](#21-源文件)
      - [2.1.1 许可与版权信息](#211-许可与版权信息)
      - [2.1.2 Package 语句](#212-package-语句)
      - [2.1.3 Import 语句](#213-import-语句)
      - [2.1.4 Class](#214-class)
    + [2.2 代码格式](#22-代码格式)
    + [2.3 命名](#23-命名)
      - [2.3.1 对所有标识符的通用约定](#231-对所有标识符的通用约定)
      - [2.3.2 对不同类型标识符的约定](#232-对不同类型标识符的约定)
        * [2.3.2.1 Package 命名](#2321-package-命名)
        * [2.3.2.2 Class & Interface 命名](#2322-class---interface-命名)
        * [2.3.2.3 Method 命名](#2323-method-命名)
        * [2.3.2.4 Constant 命名](#2324-constant-命名)
        * [2.3.2.5 Non-constant 变量命名](#2325-non-constant-变量命名)
        * [2.3.2.6 局部变量命名](#2326-局部变量命名)
    + [2.4 最佳实践](#24-最佳实践)
  * [维护者](#维护者)
  * [贡献者](#贡献者)

## 1. VS-Code-插件

- [WPILIB](https://marketplace.visualstudio.com/items?itemName=wpilibsuite.vscode-wpilib)
- [Java Extension Pack](https://marketplace.visualstudio.com/items?itemName=vscjava.vscode-java-pack)
- [Bracket Pair Colorizer 2](https://marketplace.visualstudio.com/items?itemName=CoenraadS.bracket-pair-colorizer-2)
- [google-java-format](https://marketplace.visualstudio.com/items?itemName=ilkka.google-java-format)
- [Todo Tree](https://marketplace.visualstudio.com/items?itemName=Gruntfuggly.todo-tree)
- [GitLens — Git supercharged](https://marketplace.visualstudio.com/items?itemName=eamodio.gitlens)

## 2. 代码风格规范

### 2.1 源文件

- 文件结构: 

  1. 许可与版权信息(如果有的话)。
  2. [Package](#212-package-语句) 语句。
  3. [Import](#213-import-语句) 语句。
  4. [Class](#214-class) 语句。

#### 2.1.1 许可与版权信息

- 示例:

#### 2.1.2 Package 语句

- 不允许换行。
- Package语句与Import语句直接需要用一个空行隔开。

#### 2.1.3 Import 语句

- 不允许使用野引用(如`static import`之类的引用形式)。

- 不允许换行。

- import的包具有相同路径的语句应当被放置在一起。

- import的包来自不同路径的语句应当用一个空行隔开。

- 示例:

  反例:

  <img src="https://github.com/FRCNextInnovation/NI-Programming-Guide/blob/main/assets/Code/Import-Bad.png" alt="Import-Bad" style="zoom:67%;" />

  正例:

  <img src="https://github.com/FRCNextInnovation/NI-Programming-Guide/blob/main/assets/Code/Import-Good.png" alt="Import-Good" style="zoom:67%;" />

#### 2.1.4 Class

- 类成员的编写顺序并没有严格的标准，只要遵循一个相对合理的有逻辑顺序就可以了. 你可以在 [Programming-Practices](#Programming-Practices) 查看一些示例。

- 相同方法的重载应当被放置在一起。

- 相同类型的成员(共同和分别完成相同或者类似的工作)应当被放置在一起, 且完成不同工作的成员之间应当用一个特殊样式的注释把他们分隔开。

- 示例:

  反例:

  ![Source-File-Class-Format](https://github.com/FRCNextInnovation/NI-Programming-Guide/blob/main/assets/Code/Source-File-Class-Format.png)

  正例: 

  ![Source-File-Class-Format-Good](https://github.com/FRCNextInnovation/NI-Programming-Guide/blob/main/assets/Code/Source-File-Class-Format-Good.png)

### 2.2 代码格式

- NI的代码格式遵循Google Java的代码格式。详情请查看: [Google Java Style Guide - Formatting](https://google.github.io/styleguide/javaguide.html#s4-formatting)。
- 事实上99%的代码格式化工作可以由插件帮我们自动完成 -- [google-java-format](https://marketplace.visualstudio.com/items?itemName=ilkka.google-java-format)。

### 2.3 命名

#### 2.3.1 对所有标识符的通用约定

标识符只使用ASCII字符和数字来完成。请时刻注意，在保证标识符含义易于理解的前提下，请尽量使用短的单词组合。

#### 2.3.2 对不同类型标识符的约定

##### 2.3.2.1 Package 命名

- `lowercase`

- 示例:

  ![Package-names](https://github.com/FRCNextInnovation/NI-Programming-Guide/blob/main/assets/Code/Package-names.png)

##### 2.3.2.2 Class & Interface 命名 

- `UpperCamelCase`

- 实现类的名称不应有前缀或者后缀。

- 抽象类的名称需要有一个 "base" 作为前缀。

- 接口的名称需要有一个 "I" 作为前缀。

- 示例:

  ![Class-Names](https://github.com/FRCNextInnovation/NI-Programming-Guide/blob/main/assets/Code/Class-Names.png)

##### 2.3.2.3 Method 命名

- `lowerCamelCase`

- 相同类型的方法(共同和分别完成相同或者类似的工作)的名称应当以一个相同的单词或者字母作为开头。 比如说, 底盘子系统可能有多种set方法，用于以不同的控制模式来操纵电机(Open-Loop, Velocity, Position), 那这些方法的名称都应当以"set"这个单词开头。

- 示例:

  ![Method-Name](https://github.com/FRCNextInnovation/NI-Programming-Guide/blob/main/assets/Code/Method-Name.png)

  ##### 2.3.2.4 Constant 命名

- `UPPER_AND_UNDER_SCORE_CASE`

- 示例:

  ![Constant-Name](https://github.com/FRCNextInnovation/NI-Programming-Guide/blob/main/assets/Code/Constant-Name.png)

##### 2.3.2.5 Non-constant 变量命名

- `lowerCamelCase`

- 无论是公开变量还是私有变量，名称都不能有前缀或者后缀。

- 示例:

  ![Non-Constant-Variables-Name](https://github.com/FRCNextInnovation/NI-Programming-Guide/blob/main/assets/Code/Non-Constant-Variables-Name.png)

##### 2.3.2.6 局部变量命名

- `lower_and_under_score_case`

- 示例:

  ![Parameter-Name](https://github.com/FRCNextInnovation/NI-Programming-Guide/blob/main/assets/Code/Parameter-Name.png)

### 2.4 最佳实践

- 能使用 `@Override` 请一定要用。
- 为所有与IO相关的方法使用 `synchronized` 关键字。
- 不要忽略对异常抛出的处理。
- 请时刻清楚的考虑每个成员的初始化的顺序。

## 维护者

[@Rocky_](https://github.com/RockyXRQ) [@ljy1992](https://github.com/ljy1992)

## 贡献者

:heart: 诚挚感谢每一位为本篇文档做出贡献的朋友！ :heart:

[@Rocky_](https://github.com/RockyXRQ) [@ljy1992](https://github.com/ljy1992) [@yukikisss](https://github.com/yukikisss)