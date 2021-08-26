# NI Programming Guide

[![standard-readme compliant](https://img.shields.io/badge/readme%20style-standard-brightgreen.svg?style=flat-square)](https://github.com/RichardLitt/standard-readme)

The programming guidebook of code development in Next-Innovation(NI).

The guidebook is designed by the rules:

- Speed-only is not everything,  both the speed and readability are.
- Under the premise of speed , readability is everything.
- Under the premise of readability,  shorter is better.

Every developer should follow the rules when programming and pushing the code. 

This guidebook contains:

1. Good VS-Code extensions.
2. The code style.
3. Commit message format.
4. Process of developing new functions.

![NEXT_Innovation](https://github.com/FRCNextInnovation/NI-Programming-Guide/blob/main/assets/Logo_Purple_Word_Transparent.png)

## Table of Contents
- [1. VS-Code-Extensions](#1.-VS-Code-Extensions)
- [2. Code-Style](#2. Code-Style)
  - [2.1 Source-File](#2.1-Source-File)
  - [2.2 Formatting](#2.2-Format)
  - [2.3 Naming](#2.3-Naming)
  - [2.4 Programming-Practices](#2.4-Programming-Practices)

## 1. VS-Code-Extensions

- [WPILIB](https://marketplace.visualstudio.com/items?itemName=wpilibsuite.vscode-wpilib)
- [Java Extension Pack](https://marketplace.visualstudio.com/items?itemName=vscjava.vscode-java-pack)
- [Bracket Pair Colorizer 2](https://marketplace.visualstudio.com/items?itemName=CoenraadS.bracket-pair-colorizer-2)
- [google-java-format](https://marketplace.visualstudio.com/items?itemName=ilkka.google-java-format)
- [Todo Tree](https://marketplace.visualstudio.com/items?itemName=Gruntfuggly.todo-tree)
- [GitLens — Git supercharged](https://marketplace.visualstudio.com/items?itemName=eamodio.gitlens)

## 2. Code-Style

### 2.1 Source-File

- Structure: 

  1. License or copyright information(if present).
  2. Package statement.
  3. [Import](#Import) statements.
  4. [Class](#Class) statements.

#### 2.1.1 License or copyright information

- Example:

#### 2.1.2 Package statement

- No line-wrapped.
- The package statement should be divided from Import statements by a blank line.

#### 2.1.3 Import statements

- Static import or otherwise are not used.

- No line-wrapped.

- Import from same package should be put together.

- Import from different package should be divided by a single blank line.

- Example:

  Bad:

  <img src="https://github.com/FRCNextInnovation/NI-Programming-Guide/blob/main/assets/Code/Import-Bad.png" alt="Import-Bad" style="zoom:67%;" />

  Good:

  <img src="https://github.com/FRCNextInnovation/NI-Programming-Guide/blob/main/assets/Code/Import-Good.png" alt="Import-Good" style="zoom:67%;" />

#### 2.1.4 Class

- The order of members don't have a single correct recipe to follow. What is important is that each class use some logical order. See some examples in [Programming-Practices](#Programming-Practices).

- Overloads should never split.

- Same kind of members should be put together and divided by a annotation in a specific style.

- Example:

  Bad:

  ![Source-File-Class-Format](https://github.com/FRCNextInnovation/NI-Programming-Guide/blob/main/assets/Code/Source-File-Class-Format.png)

  Good: 

  ![Source-File-Class-Format-Good](https://github.com/FRCNextInnovation/NI-Programming-Guide/blob/main/assets/Code/Source-File-Class-Format-Good.png)

### 2.2 Formatting

- Our format style follow the Google's format style of Java, you can check it here: [Google Java Style Guide - Formatting](https://google.github.io/styleguide/javaguide.html#s4-formatting).
- In fact all formatting works can be done by the Extension -- [google-java-format](https://marketplace.visualstudio.com/items?itemName=ilkka.google-java-format).

### 2.3 Naming

#### 2.3.1 Rules common to all identifiers

Identifiers use only ASCII letters and digits.  Under the premise of readability of the names,  shorter is better.

#### 2.3.2 Rules by identifier type

##### 2.3.2.1 Package names

- lowercase.

- Example:

  ![Package-names](https://github.com/FRCNextInnovation/NI-Programming-Guide/blob/main/assets/Code/Package-names.png)

##### 2.3.2.2 Class & Interface names 

- UpperCamelCase.

- Names of concrete class don't have prefixes or suffixes.

- Names of abstract class should have a "Base" prefix.

- Names of interface should have a "I" prefix.

- Example:

  ![Class-Names](https://github.com/FRCNextInnovation/NI-Programming-Guide/blob/main/assets/Code/Class-Names.png)

##### 2.3.2.3 Method names

- lowerCamelCase

- Names of same kind of methods should start in same words, for example: A chassis subsystem may have several setters to control motors in different mode(Open-Loop, Velocity, Position), so their names should all start by "set".

- Example:

  ![Method-Name](https://github.com/FRCNextInnovation/NI-Programming-Guide/blob/main/assets/Code/Method-Name.png)

  ##### 2.3.2.4 Constant names

- UPPER_AND_UNDER_SCORE_CASE

- Example:

  ![Constant-Name](https://github.com/FRCNextInnovation/NI-Programming-Guide/blob/main/assets/Code/Constant-Name.png)

##### 2.3.2.5 Non-constant field names

- lowerCamelCase

- Whatever the variables is public or private, don't add any prefixes or suffixes.

- Example:

  ![Non-Constant-Variables-Name](https://github.com/FRCNextInnovation/NI-Programming-Guide/blob/main/assets/Code/Non-Constant-Variables-Name.png)

##### 2.3.2.6 Local variable names

- lower_and_under_score_case

- Example:

  ![Parameter-Name](https://github.com/FRCNextInnovation/NI-Programming-Guide/blob/main/assets/Code/Parameter-Name.png)

### 2.4 Programming-Practices