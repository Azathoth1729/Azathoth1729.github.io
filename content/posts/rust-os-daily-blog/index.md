+++
title="rust-os-daily-blog"
date=2022-07-05

[taxonomies]
categories = ["Blog"]
tags = ["os", "rust", "blog"]

[extra]
toc = true
comments = true
+++

> rust 好好好!

这里是我学习[rust-based-os-comp][rust-based-os-comp]的一个日常记录

<!-- more -->

我的个人实验环境配置:

![sf](screenfetch.png)

# Blog

由于我看到训练营的通知较晚，导致我在最后一天才了解这个项目，又因为这几天还在学校实习，所以可能最近几天进度比较慢.

## 2022-07-05

#### task / progress

- 配置本地rust环境(之前已经配好)
- 尝试 `gitclassroom`, 使用 `codespace` 进行 `rustlings` 的训练
- `rustlings`:
  - `variables`
  - `functions`
  - `move_semantics`

## 2022-07-06

#### task / progress

- 第零章 实验环境配置
- 第一章 应用程序与基本执行环境(lab0-0)
- `rustlings`:
  - `primitive_types`
  - `enums`
  - `structs`

#### 实验环境配置

[第零章：实验环境配置][lab0-guide]

由于我之前学习过mit的 [6.S081][mit-6.S081], qemu已经装好([mit 6.S081的安装指引](https://pdos.csail.mit.edu/6.S081/2021/tools.html))
> 通过命令:`qemu-riscv64 -version`, 可以看出`qemu`的版本
> 此外, 我用的是`manjaro`(一个基于`arch linux`的linux发行版),所以qemu版本较新,符合实验要求.

根据文档,clone仓库, 运行

```bash
cd os1
LOG=DEBUG make run
```

成功获得输出:

![test_run](lab0_test_run.png)

#### QA / Thinking / Reading

1. 为什么 rust 的 两个宏: `print`/`pringln` 不能被写进`core`而需要写进`std`

  > By default, all Rust crates link the standard library, which depends on the operating system for features such as threads, files, or networking. It also depends on the C standard library libc, which closely interacts with OS services. Since our plan is to write an operating system, we can not use any OS-dependent libraries. So we have to disable the automatic inclusion of the standard library through the no_std attribute.

  为了打印到标准输出, 需要与内核进行交互, 因此必然与所在平台有关

2. 为什么rust的`core` libarary能做到 platform-agnostic.

3. [Why does Rust have a "Never" primitive type?](https://stackoverflow.com/questions/51832396/why-does-rust-have-a-never-primitive-type)

4. [What is a real world example of using a unit struct?](https://stackoverflow.com/questions/67689613/what-is-a-real-world-example-of-using-a-unit-struct)
  
## 2022-07-07

#### task / progress

- 第二章 批处理系统: 看到最后一节
- `rustlings`:
  - `collections`
  - `error_handling`
  - `generics`
  - `modules`
  - `option`
  - `standard_library_types`
  - `strings`
  - `tests`
  - `threads`
  - `traits`

#### QA / Thinking / Reading

1. [rfc of associated items](https://github.com/rust-lang/rfcs/blob/master/text/0195-associated-items.md#summary)
2. [git conventional commits](https://www.conventionalcommits.org)

[rust-based-os-comp]: <https://github.com/LearningOS/rust-based-os-comp2022>
[mit-6.S081]: <https://pdos.csail.mit.edu/6.S081/2021/index.html>
[lab0-guide]: <https://learningos.github.io/rust-based-os-comp2022/0setup-devel-env.html>
