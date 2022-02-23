# proj8-RVM
系统级虚拟化技术已经广泛应用于云计算中的数据中心等领域，是操作系统的重要组成部分，但目前高校中对系统级虚拟化的 OS 教学还比较少。RVM (Rcore Virtual Machine) 是一个用 Rust 语言编写的轻量级 hypervisor (虚拟机管理器，也叫 Virtual Machine Monitor、VMM) 模块，可用于构建各类虚拟机应用程序，实现在一台计算机上同时运行多个操作系统，提供更好的隔离性；由于其轻量性也可用于 hypervisor 的教学。目前该题目成为一个实时工业机器人科研项目的核心部分，未来将会用于实际工业机器人场景中。

当前项目实现源码：

* https://github.com/rcore-os/RVM
* https://github.com/rcore-os/RVM1.5

### 所属赛道

2022全国大学生操作系统比赛的“OS功能设计”赛道

### 参赛要求
- 以小组为单位参赛，最多三人一个小组，且小组成员是来自同一所高校的本科生（2022年春季学期或之后本科毕业的大一~大四的学生）
- 如学生参加了多个项目，参赛学生选择一个自己参加的项目参与评奖
- 请遵循“2022全国大学生操作系统比赛”的章程和技术方案要求

### 项目导师

贾越凯
- github https://github.com/equation314
- email jyk19@mails.tsinghua.edu.cn  equation618@gmail.com 

### 难度

中等

### 特征

- 支持 Intel VT-x 硬件虚拟化
- 用 Rust 语言实现
- 支持以多种方式构建虚拟化应用，运行其他 Guest OS：
    + Type-1：RVM 先启动，直接管理所有硬件，然后再启动其他 Guest OS。类似于 [Xen](https://en.wikipedia.org/wiki/Xen)；
    + Type-2：作为 Host OS 的子模块，先启动 Host OS，然后以进程的方式运行其他 Guest OS。类似于 [KVM](https://www.linux-kvm.org/page/Main_Page)；
    + Type-1.5：先启动 Linux，RVM 被一个 Linux Kernel Module 加载，然后将 Linux 自动降权为 Guest 模式运行；

### 文档

- [中文设计文档](https://github.com/rcore-os/RVM/wiki)

### License

- Apache 2.0 license

## 预期目标

### 注意：下面的内容是建议内容，不要求必须全部完成。选择本项目的同学也可与导师联系，提出自己的新想法，如导师认可，可加入预期目标

在现有RVM的基础上，进一步完成如下目标：

### 第一题：分阶段重新实现 RVM

- 与导师协商，形成一系列的小步骤，参考目前的代码，重新按小步骤实现一个简单的 Hypervisor，Type-1/2/1.5 均可
- 在每个步骤完成后，能够有测试用例，并尽量与 OS 课程中涉及的内容相关，适合作为教学实验
- 撰写实验设计与分析文档

### 第二题：扩展当前 RVM 的功能

- 在 Type-1/2 形式的 RVM 中，以设备直通或模拟的方式，支持运行复杂的 Guest OS ([rCore](https://github.com/rcore-os/aCore)/[zCore](https://github.com/rcore-os/zCore)/Linux)
- 在 Type-1/2 形式的 RVM 中，支持多核，能同时运行多个 Guest OS
- 在 Type-1.5 形式的 RVM 中，通过在 Guest Linux 中向 RVM 发送 Hypercall 的方式，运行其他 Guest OS
- 使用 Rust 语言重写启动 Type-1.5 RVM 所需的 Linux 内核可加载模块
- 更好的自动测试

### 第三题：支持其他硬件

- 支持 AMD SVM 的系统级硬件虚拟化
- 支持 ARMv8 的系统级硬件虚拟化
- 支持 RISC-V 的系统级硬件虚拟化
