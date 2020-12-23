# proj8-RVM
系统级虚拟化技术已经广泛应用于云计算中的数据中心等领域，是操作系统的重要组成部分，但目前高校中对系统级虚拟化的OS教学还比较少。RVM (Rcore Virtual Machine) 是一个用 Rust 语言编写的轻量级 hypervisor (虚拟机管理器，也叫 Virtual Machine Monitor、VMM) 模块，可用于构建各类虚拟机应用程序，实现在一台计算机上同时运行多个操作系统；由于其轻量性也可用于 hypervisor 的教学。

### 所属赛道

2021全国大学生操作系统比赛的“OS功能设计”赛道

### 参赛要求
- 以小组为单位参赛，最多三人一个小组，且小组成员是来自同一所高校的本科生（2021年春季学期或之后本科毕业的大一~大四的学生）
- 如学生参加了多个项目，参赛学生选择一个自己参加的项目参与评奖
- 请遵循“2021全国大学生操作系统比赛”的章程和技术方案要求

### 项目导师

贾越凯
- github https://github.com/equation314
- email jyk19@mails.tsinghua.edu.cn

### 难度

中等

### 特征

- 支持X86的硬件虚拟化
- 支持加载rCore kernel in Guest Mode
- 以Linux Kernel Module的形式运行

### 文档

- [中文设计文档](https://github.com/rcore-os/RVM/wiki)

### License

- Apache 2.0 license

## 预期目标

### 注意：下面的内容是建议内容，不要求必须全部完成。选择本项目的同学也可与导师联系，提出自己的新想法，如导师认可，可加入预期目标

在现有RVM的基础上，进一步完成如下目标：

### 第一题：分阶段重新实现RVM

- 与导师协商，形成一系列的小步骤，参考目前的代码，重新按小步骤实现一个简单的Hypervisor
- 在每个步骤完成后，能够有测试用例，并尽量与OS课程中涉及的内容相关
- 撰写实验设计与分析文档


### 第二题：支持其他硬件

- 支持ARM的系统级硬件虚拟化
- 支持RISC-V的系统级硬件虚拟化

