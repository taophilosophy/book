# FreeBSD 常见问题解答

- 原文：[Frequently Asked Questions for FreeBSD](https://docs.freebsd.org/en/books/faq/)

## 摘要

这是 FreeBSD 的常见问题解答（FAQ）。我们尽力使这个 FAQ 尽可能具有信息性。

## 1. 介绍

欢迎来到 FreeBSD 的世界！在本节中，我们将全面介绍 FreeBSD 的概念、起源、目标、使用场景以及背后的社区。

了解其名称的由来，学习如何为这个项目做贡献，并在开源操作系统的背景下探索 FreeBSD 丰富的生态系统。

### 1.1. 什么是 FreeBSD？

FreeBSD 是一款多功能的开源类 UNIX® 操作系统，以其卓越的稳定性、安全性和性能著称。它由一群热心的志愿者社区开发，基于伯克利软件发行版（BSD）UNIX 操作系统。

FreeBSD 提供了一个强大且可定制的环境，适用于从服务器和嵌入式系统到桌面和网络设备的广泛应用。它对开源原则的承诺确保了透明和协作的开发过程，使 FreeBSD 成为那些寻求可靠且高度适应性操作系统的用户的可信选择。

### 1.2. 为什么叫 FreeBSD？

“FreeBSD”这个名字来源于伯克利软件发行版（BSD）UNIX 操作系统，它以对开源软件世界的贡献而闻名。FreeBSD 中的“Free”表示它对自由和开源软件原则的承诺，赋予用户研究、修改和分发代码的自由。

值得指出的是，“free”在这里有两种含义：一种是“免费”，另一种是“随心所欲”。

### 1.3. FreeBSD 项目的目标是什么？

FreeBSD 项目的目标明确且坚定：提供一个高质量、开源的类 UNIX 操作系统，具有出色的性能、安全性和稳定性。

它旨在提供一个多用途平台，适用于从服务器和工作站到嵌入式系统等广泛的计算需求。FreeBSD 以强烈的开源原则为基础，营造了一个协作的环境，全球的开发者社区为操作系统的完善和改进做出了贡献。这种对质量、自由和可靠性的承诺，使 FreeBSD 在作为开源项目的持续成功中脱颖而出。

### 1.4. FreeBSD 适用于哪些使用场景？

FreeBSD 是一个多功能的操作系统，擅长于各种使用场景。它特别适用于服务器环境，在这些环境中，它的稳定性和性能使其成为 Web 主机、数据库和网络应用的流行选择。FreeBSD 强大的安全功能也使其成为防火墙和安全设备部署的强有力候选者。除了服务器，FreeBSD 还可以根据需求定制，以适应嵌入式系统和游戏控制台设备等专用环境。其适应性、可靠性和开源性质使 FreeBSD 成为各种计算需求的有力选择。

### 1.5. 谁负责 FreeBSD？

FreeBSD 是项社区驱动的开源项目，具有去中心化的结构。其开发和维护由全球的志愿者、开发者和组织共同进行，他们合作以增强和扩展操作系统。

FreeBSD 项目的关键决策，如项目的整体方向或谁有权将代码添加到源代码树，都是由一个由九人组成的选举核心团队做出的。

这种协作和社区驱动的方式是 FreeBSD 成功和长期稳定发展的基础。

### 1.6. 如何为 FreeBSD 做贡献？我能做些什么？

我们接受各种形式的贡献：文档、代码甚至艺术作品。有关如何做出贡献的具体建议，请参见 [贡献 FreeBSD 文章](https://docs.freebsd.org/en/articles/contributing/)。

感谢你的关注！

### 1.7. FreeBSD 许可证有任何限制吗？

FreeBSD 是根据 [BSD 许可证](https://www.freebsd.org/copyright/freebsd-license/) 分发的，这是一种宽松的许可证。

该许可证对你如何使用 FreeBSD 设置了非常少的限制：

* 不得声称是你编写的代码。
* 如果它崩溃，不得起诉我们。
* 不得移除或修改许可证。

该许可证意味着你可以自由修改、分发甚至出售 FreeBSD，而 **无需将你的修改作为开源发布**。然而，仍然有一些最低限度的条件，比如在分发 FreeBSD 时保留原始版权声明和免责声明。总体而言，BSD 许可证提供了高度的自由和灵活性，使 FreeBSD 成为各种应用和项目的有吸引力选择。

我们源代码树中的部分代码是根据 [GNU 通用公共许可证（GPL）](https://www.freebsd.org/copyright/COPYING) 或 [GNU 库通用公共许可证（LGPL）](https://www.freebsd.org/copyright/COPYING.LIB) 发布的，虽然它们有一些附加的条款，但通常是强调对访问的要求，而不是通常的相反要求。

### 1.8. FreeBSD 能替代我当前的操作系统吗？

对于许多用户和管理员来说，答案是肯定的。但这个问题并不是那么简单。

FreeBSD 是一个功能强大且多用途的操作系统，能够替代或与许多其他操作系统共存，具体取决于用户和管理员的需求。然而，FreeBSD 是否能替代你当前的操作系统，取决于你的硬件、软件需求以及对 FreeBSD 的熟悉程度。

尽管它提供了一个强大且功能丰富的替代方案，但在做出切换决定之前，评估你的特定使用案例和兼容性要求非常重要。

如果某个应用程序仅在某个操作系统上可用，那么该操作系统不能仅仅被替代。

从其他类 UNIX 环境迁移到 FreeBSD 的用户会发现 FreeBSD 相似。而非 UNIX 用户，如 Windows® 用户，应预期需要一些额外的时间来学习 UNIX 的工作方式。

### 1.9. FreeBSD 能运行流行的开源软件吗？

是的，FreeBSD 非常适合运行流行的开源软件。它与各种应用程序和库的兼容性使其成为那些希望部署和使用开源软件包的用户的理想选择。FreeBSD 提供了一个强大而稳定的环境，支持多种编程语言、数据库、Web 服务器和其他开源社区中常用的软件。其 Ports 和包系统简化了软件的安装和管理，确保用户可以轻松访问并运行他们喜欢的开源工具和应用程序，几乎无需麻烦。

### 1.10. 如何在 FreeBSD 中安装软件？

FreeBSD 提供了多种软件安装方法。最常见的一种方法是使用内置的 [pkg(8)](https://man.freebsd.org/cgi/man.cgi?query=pkg&sektion=8&format=html) 包管理器，通过该工具简化安装过程，直接获取并安装预构建的二进制包。另一种方法是通过 [Ports(7)](https://man.freebsd.org/cgi/man.cgi?query=ports&sektion=7&format=html) 集合从源代码编译并安装软件，这提供了一个灵活且可定制的安装方式。

FreeBSD 的文档提供了详细的指南，确保用户能够轻松地为系统安装所需的软件。

### 1.11. FreeBSD、NetBSD、OpenBSD 和其他开源 BSD 操作系统之间有什么区别？

FreeBSD、NetBSD、OpenBSD 和 DragonFly BSD 都是开源 BSD 家族的一部分，具有共同的类 UNIX 基础，但每个操作系统都有自己独特的重点和优先级。这些差异反映了每个项目的独特目标，虽然它们有相似之处，但它们的特定优势和重点满足了 BSD 生态系统中不同的使用场景和偏好。

### 1.12. FreeBSD 是 Linux® 发行版吗？

不是，FreeBSD **不是** Linux 发行版。

虽然 FreeBSD 和 Linux 都是类 UNIX 操作系统，并且有许多相似之处，但它们有各自不同的内核。Linux 使用 Linux 内核，而 FreeBSD 使用基于伯克利软件发行版（BSD）UNIX 操作系统的 FreeBSD 内核。

FreeBSD 和 Linux 各自有独立的开发社区、发布周期和系统架构，使它们成为独立的操作系统。

FreeBSD 提供了一些优势，包括不同的许可证模型、系统设计和用户空间工具，相比于 Linux 发行版有所不同。

### 1.13. 是否可以在 FreeBSD 上运行 Linux 程序？

是的，FreeBSD 提供了一个名为 *linuxulator* 的兼容层（[linux(4)](https://man.freebsd.org/cgi/man.cgi?query=linux&sektion=4&format=html)），使许多 Linux 程序能够在 FreeBSD 上运行。该功能使得无需专门的 Linux 环境，就能执行广泛的 Linux 二进制文件。

然而，需要注意的是，许多广泛使用的开源软件 **在 FreeBSD 上已经有本地版本**，可以通过 Ports 和包系统使用。

## 2. 安装 FreeBSD

安装 FreeBSD 是利用这一强大开源操作系统的第一步。本节提供了关于如何获取 FreeBSD 的基本信息，详细的安装说明，以及 FreeBSD-CURRENT 和 FreeBSD-STABLE 等概念的说明，还探讨了发布和快照计划、安装后配置工具、包搜索方法，并解答了有关包更新的常见问题。

### 2.1. 我在哪里可以获取 FreeBSD？

可以从 [官方 FreeBSD 网站](https://www.freebsd.org/where/) 免费下载 FreeBSD。

此外，FreeBSD 还可能通过各种镜像站点提供，确保全球用户都能轻松访问。 [官方网站](https://www.freebsd.org/where/) 是获取最新 FreeBSD 版本和更新的主要且最可靠来源，是开始 FreeBSD 之旅的理想起点。

### 2.2. 安装 FreeBSD 的说明在哪里？

可以在 [《FreeBSD 安装手册》](https://docs.freebsd.org/en/books/handbook/bsdinstall/) 中找到安装说明。

### 2.3. 什么是 FreeBSD-CURRENT？

FreeBSD-CURRENT 代表 FreeBSD 操作系统的开发分支。它是 FreeBSD 中最前沿的版本，包含活跃的开发和实验性更改。

虽然它集成了最新的功能、改进和实验性更改，但它可能不像 FreeBSD-STABLE 或发布版本那样稳定。

FreeBSD-CURRENT 是开发人员和爱好者贡献 FreeBSD 未来版本的一个平台，即使它偶尔会经历重大的变化，且 **不建议用于生产系统**。

### 2.4. 什么是 FreeBSD-STABLE？

FreeBSD-STABLE 分支相比 CURRENT 更稳定。它包含正在进一步测试和完善的代码，这些代码最终会被合并到 RELEASE 分支。STABLE 是那些希望跟踪 FreeBSD 开发，但又希望比 CURRENT 更稳定环境的用户的理想选择。

### 2.5. FreeBSD 发布由哪些内容组成？

FreeBSD 发布工程团队 \[[re@FreeBSD.org](mailto:re@FreeBSD.org)] 每隔大约 18 个月发布一个新的主要版本，每隔大约 8 个月发布一个新的次要版本。发布日期会提前公布，以便系统开发人员知道他们的项目需要在何时完成并进行测试。每次发布之前都会进行一个测试期，以确保新增功能不会影响发布的稳定性。

### 2.6. FreeBSD 快照是什么时候制作的？

FreeBSD 快照通常会在所有活跃开发的分支中按规律生成。这些快照捕捉了 FreeBSD 源代码和相关二进制包的某个时间点。快照的生成频率可能有所不同，但通常是每周或每两周一次。这些快照为用户提供了获取最新开发成果和更改的机会，帮助他们紧跟 FreeBSD 项目的进展。

### 2.7. 是否有工具执行安装后的配置任务？

是的，[bsdconfig(8)](https://man.freebsd.org/cgi/man.cgi?query=bsdconfig&sektion=8&format=html) 提供了一个界面来配置 FreeBSD 的安装后设置。

### 2.8. 如何在 FreeBSD 中搜索安装软件？

通过内置的 [pkg(8)](https://man.freebsd.org/cgi/man.cgi?query=pkg&sektion=8&format=html) 包管理器和 `pkg search` 命令，可以轻松搜索要安装的软件。

用户可以使用此命令通过关键字、包名或描述搜索可用的软件包。这个功能帮助用户在广泛的 FreeBSD Ports 和包集合中快速定位所需的软件，简化了在 FreeBSD 系统上添加新应用和工具的过程。

### 2.9. 为什么我的 FreeBSD 系统中没有最新的软件包？

在 FreeBSD 中，获取最新软件包的可用性可能受到多种因素的影响，包括包仓库更新的频率和使用的 FreeBSD 版本。

还应注意，FreeBSD Ports 有两个分支。更新频率较高的分支叫做 `latest`，而更新较稳定的分支叫做 `quarterly`。要使用最新的软件包，必须配置 `latest` 分支。如何配置分支的信息可以在 [Ports 手册章节](https://docs.freebsd.org/en/books/handbook/ports/) 中找到。

## 3. 硬件

硬件部分探讨了 FreeBSD 与各种硬件配置的兼容性。内容包括支持的架构、最大 RAM 容量、处理器可扩展性、显卡兼容性、Wi-Fi 卡支持以及 10 千兆以太网网卡的支持。无论是计划在服务器、工作站还是专用硬件上部署 FreeBSD，本节提供了有关 FreeBSD 的能力和限制的信息，为硬件选择和配置提供了洞察。

### 3.1. FreeBSD 支持哪些架构？

FreeBSD 支持多种架构，使其成为各种硬件环境的灵活选择。支持的架构包括 `amd64`、`arm64`、`riscv` 等。

可以在 [平台页面](https://www.freebsd.org/platforms/) 上找到完整的支持架构列表。

### 3.2. FreeBSD 支持多少 RAM？

作为一个操作系统，FreeBSD 支持的物理内存（RAM）量通常取决于其运行的平台。不同平台的内存限制不同。

例如，`amd64` 平台支持最大 4TB 的物理内存。

### 3.3. FreeBSD 支持多少个处理器？

FreeBSD 的处理器支持在不同架构之间有所不同。在 `amd64` 和 `arm64` 系统上，FreeBSD 可以有效利用最多 1024 个处理器。对于基于 `powerpc` 的系统，FreeBSD 支持最多 256 个处理器，而在 `risc-v` 系统上，它可以有效使用最多 16 个处理器。

### 3.4. FreeBSD 支持哪些显卡？

FreeBSD 对流行的显卡厂商如 Intel®、AMD® 或 NVIDIA® 提供了良好的支持。

可以在 FreeBSD Wiki 上找到来自 [Intel](https://wiki.freebsd.org/Graphics/Intel-GPU-Matrix) 和 [AMD](https://wiki.freebsd.org/Graphics/AMD-GPU-Matrix) 的显卡支持列表。

### 3.5. FreeBSD 支持哪些无线网卡？

了解 FreeBSD 与各种无线网卡的兼容性，使你可以轻松地将系统连接到无线网络。

以下是已知在 FreeBSD 上运行良好的 USB 无线网卡设备列表：

* RT5370 USB 加密狗（支持 hostap 模式）
* TP-Link TL-WDN3200（RT5592，[if\_run(4)](https://man.freebsd.org/cgi/man.cgi?query=if_run&sektion=4&format=html)）
* TP-Link TL-WN725N v2（RTL8188EU，[rtwn(4)](https://man.freebsd.org/cgi/man.cgi?query=rtwn&sektion=4&format=html)）
* TP-Link Archer T4U（RTL8812AU，[rtwn(4)](https://man.freebsd.org/cgi/man.cgi?query=rtwn&sektion=4&format=html)）
* D-Link DWA-131（RTL8192CU，[rtwn(4)](https://man.freebsd.org/cgi/man.cgi?query=rtwn&sektion=4&format=html)）
* D-Link DWA-171 rev A1（RTL8821AU，[rtwn(4)](https://man.freebsd.org/cgi/man.cgi?query=rtwn&sektion=4&format=html)）
* ASUS USB-N10 NANO（RTL8188CUS，[rtwn(4)](https://man.freebsd.org/cgi/man.cgi?query=rtwn&sektion=4&format=html)）

以下是已知在 FreeBSD 上运行良好的 Mini PCIe 无线网卡设备列表：

* Realtek RTL8188CE Mini PCIe

### 3.6. FreeBSD 是否支持 10 G 以太网网卡？

FreeBSD 为 10 G 以太网网卡提供了强大的支持，使其成为高速网络环境中的一个可行选择。FreeBSD 内核包含来自多个厂商的各种 10 G 以太网适配器的驱动程序，确保无缝集成并优化网络性能。

更多信息可以在 [FreeBSD Wiki](https://wiki.freebsd.org/Networking/10GbE) 上获取。

## 4. 文档与支持

本节提供了对那些希望深入了解 FreeBSD 的用户有价值的资源。内容涵盖了学习 FreeBSD 的推荐书籍、商业培训和支持渠道、了解 FreeBSD 内部结构的见解，以及在 FreeBSD 社区中寻求帮助的途径。

### 4.1. 有哪些关于 FreeBSD 的好书？

FreeBSD 爱好者和学习者可以探索许多关于操作系统的有价值的书籍。这些书籍涵盖了从 FreeBSD 基础到高级系统管理和开发的各个方面。

一些值得注意的书籍包括 Michael W. Lucas 所著的《Absolute FreeBSD: The Complete Guide To FreeBSD》和他的《FreeBSD Mastery》系列等。这些资源为不同层次的用户提供了宝贵的见解和知识，帮助他们掌握 FreeBSD 并最大化其潜力。

除了这些书籍，FreeBSD 项目还制作了广泛的文档，可以在 [文档门户](https://docs.freebsd.org/) 中在线访问。

### 4.2. 我在哪里可以获得商业的 FreeBSD 培训和支持？

对于那些寻求专业 FreeBSD 培训和支持的人，有多家商业提供商提供定制服务。FreeBSD 项目维护了一个 [公司列表](https://www.freebsd.org/commercial/)，你可以从这些公司中获取支持。

### 4.3. 如何深入了解 FreeBSD 的内部结构？

要深入了解 FreeBSD 的内部工作机制，有兴趣的人可以阅读《The Design And Implementation Of The FreeBSD Operating System》。另一个有价值的资源是 [FreeBSD 架构手册](https://docs.freebsd.org/en/books/arch-handbook/)，该手册提供了关于 FreeBSD 架构、系统组织和设计原则的详细信息。

此外，查看通过 FreeBSD 源代码仓库提供的 FreeBSD 源代码，也能为了解操作系统的核心组件提供宝贵的见解。

### 4.4. 如何在 FreeBSD 系统中寻求帮助？

在 FreeBSD 系统中获取帮助非常简单。FreeBSD 提供了丰富的内置文档，可以通过 [man(1)](https://man.freebsd.org/cgi/man.cgi?query=man&sektion=1&format=html) 命令访问，这些文档包含有关各种命令和系统组件的全面信息。

此外，[FreeBSD 手册](https://docs.freebsd.org/en/books/handbook/) 也可供在线和本地访问，是深入指导的宝贵资源。

如果遇到具体问题，可以通过 FreeBSD 社区的邮件列表、论坛或 IRC 寻求帮助，经验丰富的 FreeBSD 用户和开发人员可以提供及时的解决方案和见解。

## 5. 社区问题

本节介绍了与 FreeBSD 社区互动的方式。

关注 FreeBSD IRC 频道，以便进行实时讨论，关注基于 Web 的论坛，分享见解，并获取 FreeBSD 邮件列表和新闻组的信息，用于深入讨论和新闻更新。

### 5.1. 是否有 FreeBSD IRC（互联网中继聊天）频道？

是的，大多数主要的 IRC 网络都有 FreeBSD 聊天频道，FreeBSD wiki 上列出了一个最新的 [IRC 频道列表](https://wiki.freebsd.org/IRC/Channels)。

这些频道各自独立，没有相互连接。由于它们的聊天风格不同，可以尝试每个频道，找到最适合你聊天风格的一个。

### 5.2. 是否有任何基于 Web 的论坛可以讨论 FreeBSD？

官方的 FreeBSD 论坛位于 [FreeBSD 论坛首页](https://forums.freebsd.org/)。

### 5.3. 我在哪里可以找到 FreeBSD 邮件列表的信息？

公共邮件列表可以在 [FreeBSD 邮件列表](https://lists.freebsd.org/) 中找到。

## 6. 其他问题

探索一系列有关 FreeBSD 的有趣且实用的问题，涵盖从 Shell 选择到系统怪癖，甚至 FreeBSD 宠物的名字等话题。

### 6.1. 为什么 `/bin/sh` 如此简洁？为什么 FreeBSD 不使用 bash 或其他 shell？

许多人需要编写可以在多个系统之间移植的 Shell 脚本。这就是为什么 POSIX® 详细规定了 shell 和工具命令。大多数脚本都是用 Bourne shell（[sh(1)](https://man.freebsd.org/cgi/man.cgi?query=sh&sektion=1&format=html)）编写的，因为多个重要的编程接口规定使用 Bourne shell 来解释命令。由于 Bourne shell 被如此广泛和频繁地使用，确保其启动迅速、行为可预测且内存占用小就显得尤为重要。

现有的实现是我们尽最大努力在满足这些要求的同时，保持 `/bin/sh` 尺寸小巧。为了保持 `/bin/sh` 简洁，我们没有提供其他 shell 所有的便利功能。

这也是为什么像 `bash`、`scsh`、[tcsh(1)](https://man.freebsd.org/cgi/man.cgi?query=tcsh&sektion=1&format=html) 和 `zsh` 等功能更丰富的 shell 可供选择的原因。

### 6.2. 如何在 sh 和 csh 中使用删除键？

对于 Bourne Shell，请将以下内容添加到 **\~/.shrc** 文件：

```
bind ^[[3~ ed-delete-next-char # 对于 xterm
```

对于 C Shell，请将以下内容添加到 **\~/.cshrc** 文件：

```
bindkey ^[[3~ delete-char # 对于 xterm
```

### 6.3. 我忘记了 root 密码！该怎么办？

不要慌张！重启系统，在 `Boot:` 提示符下输入 `boot -s` 进入单用户模式。当系统询问选择使用的 shell 时，按 Enter 键，会显示一个 # 提示符。输入 `mount -urw /` 来重新挂载根文件系统为读写模式，然后运行 `mount -a` 来重新挂载所有文件系统。运行 `passwd root` 来更改 `root` 密码，然后运行 [exit(1)](https://man.freebsd.org/cgi/man.cgi?query=exit&sektion=1&format=html) 继续启动系统。

>**技巧**
>
> 如果在进入单用户模式时仍然被要求提供 `root` 密码，这意味着控制台在 **/etc/ttys** 中被标记为 `insecure`。在这种情况下，你需要从 FreeBSD 安装盘启动，选择安装过程开始时的 **Live CD** 或 **Shell**，然后执行上述命令。此时需要挂载特定的分区，然后进行 chroot。例如，对于系统在 *ada0p1* 上，替换 `mount -urw /` 为 `mount /dev/ada0p1 /mnt; chroot /mnt`。 

>**技巧**
>
> 如果根分区无法在单用户模式下挂载，则可能是分区已加密，没有访问密钥就无法挂载它们。有关加密磁盘的更多信息，请参阅 FreeBSD [手册](https://docs.freebsd.org/en/books/handbook/disks/#disks-encrypting) 中关于加密磁盘的部分。

### 6.4. 我在 rc.conf 或其他启动文件中犯了错误，现在因为文件系统是只读的，我无法编辑它。我该怎么办？

重启系统，在加载器提示符下输入 `boot -s` 进入单用户模式。当系统询问选择 shell 路径时，按 Enter 键，运行 `mount -urw /` 以重新挂载根文件系统为读写模式。你还需要运行 `mount -a -t ufs` 来挂载包含你常用编辑器的文件系统。如果编辑器在网络文件系统上，你可以手动配置网络，或者使用本地文件系统上的编辑器，比如 [ed(1)](https://man.freebsd.org/cgi/man.cgi?query=ed&sektion=1&format=html)。

为了使用全屏编辑器如 [vi(1)](https://man.freebsd.org/cgi/man.cgi?query=vi&sektion=1&format=html) 或 [emacs(1)](https://man.freebsd.org/cgi/man.cgi?query=emacs&sektion=1&format=html)，运行 `export TERM=xterm` 以便这些编辑器能够从 [termcap(5)](https://man.freebsd.org/cgi/man.cgi?query=termcap&sektion=5&format=html) 数据库中加载正确的数据。

执行这些步骤后，编辑 **/etc/rc.conf** 以修正语法错误。系统在内核启动信息之后显示的错误信息应指明文件中有问题的行号。

### 6.5. 系统中有多少可用的内存？

有几种“空闲内存”的定义。最常见的是立即可用的内存量，这部分内存不需要回收已使用的内存。它是空闲页面队列的大小加上一些其他保留页面。此值可以通过 `vm.stats.vm.v_free_count` [sysctl(8)](https://man.freebsd.org/cgi/man.cgi?query=sysctl&sektion=8&format=html) 获取，并可以通过 [top(1)](https://man.freebsd.org/cgi/man.cgi?query=top&sekction=1&format=html) 显示。另一种“空闲内存”是用户空间进程可以使用的虚拟内存总量，这取决于交换空间和可用内存的总和。还有其他不同类型的“空闲内存”描述，但这些定义并不特别有用。更重要的是保持低的分页率，并避免耗尽交换空间。

### 6.6. 我的时间不对，我该如何更改时区？

使用 [tzsetup(8)](https://man.freebsd.org/cgi/man.cgi?query=tzsetup&sektion=8&format=html)。

### 6.7. 即使计算机有空闲内存，FreeBSD 仍然使用大量的交换空间，为什么？

FreeBSD 会主动将完全空闲、未使用的内存页面移到交换空间中，以便让更多的主内存可供活动使用。这种对交换空间的重度使用是通过使用额外的空闲内存来缓存数据来平衡的。

需要注意的是，尽管 FreeBSD 在这方面是主动的，它并不会在系统真正空闲时随意决定交换页面。因此，系统不会在将其放置一夜之后完全被交换出去。

### 6.8. 为什么即使我运行的程序很少，`top` 显示的空闲内存很少？

简单的答案是，空闲内存是浪费的内存。

任何程序没有主动分配的内存都会被 FreeBSD 内核用作磁盘缓存。通过 [top(1)](https://man.freebsd.org/cgi/man.cgi?query=top&sektion=1&format=html) 显示的 `Inact` 和 `Laundry` 值是不同老化级别的缓存数据。这些缓存数据意味着系统不必再次访问慢速磁盘来获取它最近访问过的数据，从而提高了整体性能。通常，在 [top(1)](https://man.freebsd.org/cgi/man.cgi?query=top&sektion=1&format=html) 中显示的 `Free` 内存较低是好事，只要它不是 *非常* 低。

### 6.9. 那个可爱的小红色家伙叫什么名字？

他没有名字，只叫 "BSD 守护神"。如果你非要给他起个名字，可以叫他 "beastie"。需要注意的是，“beastie” 发音为 "BSD"。

更多关于 BSD 守护神的信息可以查看他的 [主页](http://www.mckusick.com/beastie/index.html)。

### 6.10. 我可以使用 BSD 守护神的图像吗？

也许可以。BSD 守护神的版权归 Marshall Kirk McKusick 所有。请查看他的 [BSD 守护神图像使用声明](http://www.mckusick.com/beastie/mainpage/copyright.html) 了解详细的使用条款。

总之，图像可以以合适的方式用于个人用途，只要给出适当的归属。在商业上使用该标志之前，请联系 Kirk McKusick \[[mckusick@FreeBSD.org](mailto:mckusick@FreeBSD.org)]\(%[5Bmckusick@FreeBSD.org](mailto:5Bmckusick@FreeBSD.org)%5D(mailto\:mckusick\@FreeBSD.org)) 获得许可。可以在 [BSD 守护神主页](http://www.mckusick.com/beastie/index.html) 上找到更多细节。

### 6.11. 为什么我需要关心自行车棚的颜色？

简短的回答是，你不需要关心。稍长的回答是，仅仅因为你能够建造一个自行车棚，并不意味着你应该因为不喜欢别人想涂的颜色而阻止他们建造。这是一个隐喻，意味着即使你知道足够多的东西，也不应该为每个小问题争论。有人评论过，改变所引发的噪音量与变化的复杂度成反比。

更长且完整的答案是，在经历了一场关于 [sleep(1)](https://man.freebsd.org/cgi/man.cgi?query=sleep&sektion=1&format=html) 是否应该接受分数秒参数的漫长辩论后，Poul-Henning Kamp [phk@FreeBSD.org](mailto:phk@FreeBSD.org) 发布了一篇名为 [A bike shed (any color will do) on greener grass…](http://www.bikeshed.com/) 的长文。

## 7. FreeBSD 趣闻

从技术细节中休息一下，来享受 FreeBSD 的幽默一面。

### 7.1. FreeBSD 多酷？

1. *有没有人在运行 FreeBSD 时做过温度测试？*
   没有，但我们曾在盲测志愿者身上进行过多次味觉测试，志愿者们在测试之前服用了 250 微克 LSD-25。35%的志愿者表示 FreeBSD 有点像橙色的味道，而 GNU/Linux® 则像紫色迷雾。没有一组提到温度上有任何显著差异。

说真的，FreeBSD 使用了 ACPI（高级配置与电源接口），因此 FreeBSD 可以将 CPU 置于低功耗模式。

### 7.2. 写入 **/dev/null** 的数据去哪了？

它进入了 CPU 中的一个特殊数据汇聚点，在那里它被转化为热量并通过散热器/风扇组件排出。这就是为什么 CPU 冷却变得越来越重要的原因；随着人们习惯了更快的处理器，他们开始对数据变得漫不经心，越来越多的数据最终进入 **/dev/null**，导致 CPU 过热。

如果删除 **/dev/null**（实际上是禁用了 CPU 数据汇聚点），你的 CPU 可能会变得更冷，但系统会因为积压的过多数据而变得不稳定，开始表现出异常行为。

如果你有一个快速的网络连接，你可以通过读取 **/dev/random** 中的数据并将其发送到某个地方来帮助冷却 CPU；但是你可能会使网络连接过热，并且 **/** 目录也有可能过热，或者激怒你的 ISP，因为大多数数据将被他们的设备转化为热量，但他们通常有很好的散热，如果不过度使用，你应该没问题。

### 7.3. 我的同事坐在电脑前太久了，我该如何捉弄他们？

安装 [games/sl](https://cgit.freebsd.org/ports/tree/games/sl/) 并等待他们把 `sl` 错打成 `ls`。

## 8. 致谢

这份常见问题解答（FAQ）在过去几十年中经历了无数次修订和改进，得到了来自不同贡献者的帮助。
