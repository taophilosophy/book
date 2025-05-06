# FreeBSD 项目模型

- 原文：[A project model for the FreeBSD Project](https://docs.freebsd.org/en/books/dev-model/)

## 前言

到目前为止，FreeBSD 项目已经发布了许多不同部分的工作技巧。然而，随着项目成员数量的增加，需要一种总结项目结构的模型。^\[[1](https://docs.freebsd.org/en/books/dev-model/#_footnotedef_1 "查看脚注")]^ 本文将提供这样的项目模型，并捐赠给 FreeBSD 文档项目，以便它能与项目一起发展，随时反映项目的工作方式。它基于 \[[Saers](https://docs.freebsd.org/en/books/dev-model/#thesis)]。

我想感谢以下人士，他们花时间解释了我不清楚的内容，并对本文进行了校对：

* Andrey A. Chernov [ache@freebsd.org](mailto:ache@freebsd.org)
* Bruce A. Mah [bmah@freebsd.org](mailto:bmah@freebsd.org)
* Dag-Erling Smørgrav [des@freebsd.org](mailto:des@freebsd.org)
* Giorgos Keramidas [keramida@freebsd.org](mailto:keramida@freebsd.org)
* Ingvil Hovig [ingvil.hovig@skatteetaten.no](mailto:ingvil.hovig@skatteetaten.no)
* Jesper Holck [jeh.inf@cbs.dk](mailto:jeh.inf@cbs.dk)
* John Baldwin [jhb@freebsd.org](mailto:jhb@freebsd.org)
* John Polstra [jdp@freebsd.org](mailto:jdp@freebsd.org)
* Kirk McKusick [mckusick@freebsd.org](mailto:mckusick@freebsd.org)
* Mark Linimon [linimon@freebsd.org](mailto:linimon@freebsd.org)
* Marleen Devos
* Niels Jørgenssen [nielsj@ruc.dk](mailto:nielsj@ruc.dk)
* Nik Clayton [nik@freebsd.org](mailto:nik@freebsd.org)
* Poul-Henning Kamp [phk@freebsd.org](mailto:phk@freebsd.org)
* Simon L. Nielsen [simon@freebsd.org](mailto:simon@freebsd.org)

## 1. 概述

项目模型是一种减少项目中沟通开销的手段。正如 \[[Brooks](https://docs.freebsd.org/en/books/dev-model/#brooks)] 所示，项目参与者数量的增加会使得沟通在项目中呈指数增长。近年来，FreeBSD 的活跃用户和提交者数量都在增加，项目中的沟通也相应增加。这个项目模型将通过提供项目的最新描述来减少这种开销。

在 2002 年的核心团队选举期间，Mark Murray 说：“我反对制定一个冗长的规则书，因为这会迎合律师的倾向，并且与项目所急需的技术中心思想相悖。” \[[FreeBSD](https://docs.freebsd.org/en/books/dev-model/#bsd-election2002)]。这个项目模型不是用来为开发者施加限制的工具，而是一个促进协调的工具。它旨在作为项目的描述，概述不同过程的执行方式。它是对 FreeBSD 项目工作原理的介绍。

FreeBSD 项目模型的描述基于 2004 年 7 月 1 日的版本，依托于 Niels Jørgensen 的论文 \[[Jørgensen](https://docs.freebsd.org/en/books/dev-model/#jorgensen2001)]，FreeBSD 的官方文档，FreeBSD 邮件列表中的讨论以及与开发者的访谈。

本文将首先定义所使用的术语，接着概述组织结构（包括角色描述和沟通路线），讨论方法模型，并在展示了用于过程控制的工具后，介绍已定义的过程。最后，将概述 FreeBSD 项目的主要子项目。

\[[FreeBSD](https://docs.freebsd.org/en/books/dev-model/#freebsd-developer-handbook)] 第 1.2 和 1.3 节给出了项目的愿景和架构指南。愿景是：“生产尽可能最好的类 UNIX 操作系统包，充分尊重原始软件工具的理念，以及可用性、性能和稳定性。” 架构指南有助于确定某个问题是否在项目的范围内。

## 2. 定义

### 2.1. 活动

“活动”是指在项目过程中执行的工作元素 \[[PMI](https://docs.freebsd.org/en/books/dev-model/#ref-pmbok)]。它有一个输出，并朝向一个结果推进。这样的输出可以是另一个活动的输入，也可以是过程交付的一部分。

### 2.2. 过程

“过程”是一系列朝向特定结果推进的活动。一个过程可以包含一个或多个子过程。例如，软件设计就是一个过程。

### 2.3. 角色

“角色”与“帽子”是同义词。角色在一个过程中的职责和过程结果的责任是明确的。角色执行活动。项目成员和项目外部人员都知道应该就什么问题联系这个角色。

### 2.4. 结果

“结果”是过程的最终输出。这与交付物同义，交付物被定义为“任何可衡量、具体、可验证的结果、结果或项目，必须通过它来完成一个项目或项目的一部分。通常更狭义地指代外部交付物，即必须经过项目赞助人或客户批准的交付物”\[[PMI](https://docs.freebsd.org/en/books/dev-model/#ref-pmbok)]。结果的例子包括一段软件，一个决策或一份报告。

### 2.5. FreeBSD

当我们说“FreeBSD”时，指的是类 UNIX 操作系统 FreeBSD；而当我们说“FreeBSD 项目”时，指的是项目组织。

## 3. 组织结构

尽管没有人真正“拥有”FreeBSD，但 FreeBSD 组织分为核心成员、提交者和贡献者，并且是围绕它生活的 FreeBSD 社区的一部分。

FreeBSD 项目的结构（按权限从高到低排序）

| 组别   | 人数     |
| ---- | ------ |
| 核心成员 | 9      |
| 提交者  | 318    |
| 贡献者  | \~3000 |

提交者的数量是通过检查 2004 年 1 月 1 日至 2004 年 12 月 31 日的 CVS 日志来确定的，贡献者数量则是通过查看贡献列表和问题报告来确定的。

FreeBSD 社区的主要资源是它的开发者：提交者和贡献者。正是通过他们的贡献，项目得以前进。普通开发者被称为贡献者。截至 2003 年 1 月 1 日，估计项目上有约 5500 名贡献者。

提交者是有权限提交更改的开发者。通常，提交者是最活跃的开发者，他们愿意花时间不仅整合自己的代码，还整合其他没有此权限的开发者提交的代码。提交者也是选举核心团队的开发者，并且可以访问闭门讨论。

项目可以分为四个明显的部分，大多数开发者将专注于 FreeBSD 的某一部分。这四部分是内核开发、用户空间开发、Ports 和文档。当提到基础系统时，既指内核，也指用户空间。

这一区分使得我们的表格变成了这样：

FreeBSD 项目的结构（按提交者分类）

| 组别   | 类别   | 人数     |
| ---- | ---- | ------ |
| 核心成员 |      | 9      |
| 提交者  | 基本系统 | 164    |
|      | 文档   | 45     |
|      | Ports   | 166    |
|      | 总计   | 374    |
| 贡献者  |      | \~3000 |

每个领域的提交者数量是通过检查 2004 年 1 月 1 日至 2004 年 12 月 31 日的 CVS 日志来确定的。请注意，许多提交者在多个领域工作，因此总数高于实际的提交者人数。2022 年 6 月，活跃的独立提交者总数为 317。

提交者分为三类：仅关注项目某一领域的提交者（例如文件系统），仅参与某个子项目的提交者，以及提交代码至不同部分（包括子项目）的提交者。由于一些提交者在不同部分工作，表格中提交者总数比上表中的数字要高。

内核是 FreeBSD 的主要构建模块。虽然用户空间应用程序可以防止其他用户空间应用程序中的错误，但整个系统对内核中的错误是脆弱的。结合内核中庞大的依赖关系以及很难预见内核变更的所有后果，这要求开发者对内核有相对全面的理解。内核中的多个开发工作也需要比用户空间应用程序更紧密的协调。

核心工具（即用户空间）提供了标识 FreeBSD 的接口，包括用户界面、共享库以及与连接客户端的外部接口。目前，162 人参与了用户空间的开发和维护，其中许多人是自己负责代码部分的维护者。维护者的角色将在[维护者](https://docs.freebsd.org/en/books/dev-model/#role-maintainer)部分中讨论。

文档工作由 [FreeBSD 文档项目](https://docs.freebsd.org/en/books/dev-model/#sub-project-documentation)负责，涵盖了与 FreeBSD 项目相关的所有文档，包括网页内容。在 2004 年，有 101 人参与了 FreeBSD 文档项目的提交工作。

Ports 是构建正确的软件包所需的元数据集合。在 FreeBSD 上构建软件包时，ports 包含有关如何获取源代码、应用补丁及如何在系统上安装软件包的信息。这允许自动化工具获取、构建并安装该软件包。至目前为止，已提供 12600 余个 Port ^\[[2](https://docs.freebsd.org/en/books/dev-model/#_footnotedef_2 "查看脚注")]^，范围涵盖从 Web 服务器到游戏、编程语言以及现代计算机中使用的大多数应用类型。Ports 子项目将在[Ports 子项目](https://docs.freebsd.org/en/books/dev-model/#sub-project-ports)部分中进一步讨论。


## 4. 方法论模型

### 4.1. 开发模型

FreeBSD 并没有定义明确的代码编写模型。然而，Niels Jørgenssen 提出了一个模型，描述了如何将编写的代码集成到项目中。

Jørgenssen 的变更集成模型

| 阶段    | 成功后继续到 | 失败后继续到 |
| ----- | ------ | ------ |
| 代码    | 审查     |        |
| 审查    | 提交前测试  | 代码     |
| 提交前测试 | 开发版发布  | 代码     |
| 开发版发布 | 并行调试   | 代码     |
| 并行调试  | 生产版发布  | 代码     |
| 生产版发布 |        | 代码     |

“开发版发布”指的是 FreeBSD-CURRENT（“-CURRENT”）分支，而“生产版发布”指的是 FreeBSD-STABLE（“-STABLE”）分支 \[[Jørgensen](https://docs.freebsd.org/en/books/dev-model/#jorgensen2001)]。

这是针对一次变更的模型，显示了在编码之后，开发者会寻求社区的审查，并尝试将其与他们自己的系统集成。在将变更集成到开发版（即 FreeBSD-CURRENT）之后，它会经过 FreeBSD 社区中的众多用户和开发者的测试。当它经过足够的测试后，它会合并到生产版（即 FreeBSD-STABLE）中。除非每个阶段都顺利完成，否则开发者需要回到代码并进行修改，然后重新启动过程。将变更集成到 -CURRENT 或 -STABLE 中被称为进行提交。

Jørgenssen 发现，大多数 FreeBSD 开发者是独立工作的，这意味着这个模型会在多个开发者的不同开发工作中并行使用。一个开发者也可能在处理多个变更，因此，在等待审查或其他人测试其变更的同时，他们可能会编写另一个变更。

由于每个提交代表着一个增量，因此这是一个大规模增量的模型。实际上，提交的频率非常高，在一年内 ^\[[3](https://docs.freebsd.org/en/books/dev-model/#_footnotedef_3 "查看脚注")]^，共进行了 85427 次提交，平均每天有 233 次提交。

在 Jørgenssen 模型中的“代码”阶段，每个程序员都有自己的工作风格，并遵循自己的开发模型。这个阶段完全可以被称为“开发”，因为它包括需求收集与分析、系统与详细设计、实现和验证。然而，这些阶段的唯一输出是源代码或系统文档。

从逐步模型的角度来看（例如瀑布模型），其他阶段可以视为进一步的验证和系统集成。这种系统集成也很重要，用于查看变更是否被社区接受。在代码提交之前，开发者可以自由决定是否与项目其他成员进行沟通。为了使 -CURRENT 能作为缓冲区（以便那些有些未被发现的缺点的创新想法可以被撤销），一个提交在 -CURRENT 中的最低时间应该是 3 天，之后才可以合并到 -STABLE 中。这样的合并称为 MFC（从 CURRENT 合并）。

需要注意的是，“变更”这个词。大多数提交并不包含激进的新特性，而是维护性更新。

此模型的唯一例外是安全修复和 -CURRENT 分支中已弃用特性的更改。在这些情况下，可以直接提交到 -STABLE 分支。

除了许多人参与这个项目外，FreeBSD 项目还有许多相关项目。这些项目或是开发全新特性、子项目，或是其成果被整合到 FreeBSD 中 ^\[[4](https://docs.freebsd.org/en/books/dev-model/#_footnotedef_4 "查看脚注")]^。这些项目与 FreeBSD 项目一样，作为常规开发工作的一部分进行：它们生产的代码会被集成到 FreeBSD 项目中。然而，其中一些（如 Ports 和文档）有特权，可以适用于两个分支，或直接提交到 -CURRENT 和 -STABLE。

关于设计并没有标准，也没有集中式的设计仓库。主要的设计是 4.4BSD 的设计 ^\[[5](https://docs.freebsd.org/en/books/dev-model/#_footnotedef_5 "查看脚注")]^。由于设计是 Jørgenssen 模型中“代码”阶段的一部分，具体如何进行设计由每个开发者或子项目决定。即使设计应当存储在集中式仓库中，由于不同方法论的差异，设计阶段的输出也将受到很大限制，可能会使其相互不兼容或难以互操作。对于整个项目的设计，项目依赖于子项目之间协商接口，而不是强制规定接口。

### 4.2. 发布分支

FreeBSD 的发布最适合通过一棵有许多分支的树来展示，其中每个主要分支代表一个主要版本。次要版本则通过主要分支的子分支来表示。

在以下发布树中，依次相互连接的箭头代表一个分支。实线框和菱形框代表官方发布，虚线框代表当时的开发分支。安全分支用椭圆表示。菱形框与方框的不同之处在于它们代表一个分叉点，意味着一个分支分裂成两个分支，其中一个分支变成了子分支。例如，在 4.0-RELEASE 时，4.0-CURRENT 分支分裂成了 4-STABLE 和 5.0-CURRENT。在 4.5-RELEASE 时，该分支又分叉出了一个名为 RELENG\_4\_5 的安全分支。

![请参见下面的表格以获取屏幕阅读器友好的版本。](https://docs.freebsd.org/images/books/dev-model/branches.png)

**图 1. FreeBSD 发布树**

| 主要发布版本            | 分叉自         | 后续次要版本                                                                                                                                              |
| ----------------- | ----------- | --------------------------------------------------------------------------------------------------------------------------------------------------- |
| …                 |             |                                                                                                                                                     |
| 3.0 Current（开发分支） |             | Releng 3 分支：3.0 Release 到 3.5 Release，随后是 3.5.1 Release 和后续的 3 Stable 分支                                                                            |
| 4.0 Current（开发分支） | 3.1 Release | Releng 4 分支：4.1 Release 到 4.6 Release（以及 4.6.2 Release），然后是 4.7 Release 到 4.11 Release（所有从 4.3 Release 开始也都指向一个 Releng\_4\_n 分支），以及后续的 4 Release 分支 |
| 5.0 Current（开发分支） | 4.0 Release | Releng 5 分支：5.0 Release 到 5.4 Release（除了 5.0 和 5.3 之外，其他也会指向一个 Releng\_5\_n 分支），以及后续的 5 Release 分支                                                  |
| 6.0 Current（开发分支） | 5.3 Release |                                                                                                                                                     |
| …                 |             |                                                                                                                                                     |

最新的 -CURRENT 版本始终被称为 -CURRENT，而最新的 -STABLE 发布版本始终被称为 -STABLE。在这个图中，-STABLE 指的是 4-STABLE，而 -CURRENT 则指的是 5.0-CURRENT，跟随 5.0-RELEASE。\[[FreeBSD](https://docs.freebsd.org/en/books/dev-model/#freebsd-releng)]

"主要发布" 总是从 -CURRENT 分支中制作。然而，-CURRENT 分支在这一时间点不一定需要分叉，而可以集中精力进行稳定化。例如，在 3.0-RELEASE 之后，3.1-RELEASE 也是 -CURRENT 分支的延续，并且 -CURRENT 直到此版本发布并且 3-STABLE 分支分叉后才成为真正的开发分支。当 -CURRENT 再次成为开发分支时，它只能跟随一个主要版本发布。预计 5-STABLE 会在 5.0-CURRENT 的大约 5.3-RELEASE 时分叉。只有 5-STABLE 被分叉之后，开发分支才会被标记为 6.0-CURRENT。

"次要发布" 是从主要版本发布后，或从 -STABLE 分支中制作的。

从 4.3-RELEASE 开始^\[[6](https://docs.freebsd.org/en/books/dev-model/#_footnotedef_6 "查看脚注")]^，每当次要发布完成后，它将变成一个“安全分支”。这专为那些不想跟随 -STABLE 分支及其潜在的新功能或更改的组织设计，而是需要一个绝对稳定的环境，只进行安全更新。^\[[7](https://docs.freebsd.org/en/books/dev-model/#_footnotedef_7 "查看脚注")]^

每次更新安全分支时，都会增加一个“补丁级别”。每次进行安全增强时，补丁级别的数字都会增加，方便跟踪该分支的人员查看已实施的安全增强。如果存在特别严重的安全漏洞，可能会从安全分支制作一个全新的发布版本。例如，4.6.2-RELEASE 就是一个来自安全分支的全新发布版本。

### 4.3. 模型总结

总结来说，FreeBSD 的开发模型可以看作是以下树状结构：

![请参见下面的段落获取屏幕阅读器友好的版本。](https://docs.freebsd.org/images/books/dev-model/freebsd-code-model.png)

**图 2. 整体开发模型**

FreeBSD 的开发树展示了持续的开发工作和持续集成。

该树象征着发布版本，其中主要版本产生新的主分支，而次要版本则是主分支的版本。最上面的分支是 -CURRENT 分支，所有新开发的代码都集成在这个分支中，紧随其下的是 -STABLE 分支。在 -STABLE 分支下面是旧的、不再支持的版本。

开发努力像云雾一样笼罩着项目，开发者根据自己的需求选择合适的开发模型。开发工作的成果随后被集成到 -CURRENT 分支，在那里进行并行调试，并最终从 -CURRENT 合并到 -STABLE 分支。安全修复则从 -STABLE 合并到安全分支。

许多提交者有着特定的责任领域，这些责任被称为"帽子"。这些帽子可以是项目角色，例如公关官员，或是某个代码区域的维护者。由于这是一个由人们自愿奉献业余时间的项目，因此拥有帽子的人员并不总是可以用，他们需要指派代理人来代替其缺席时履行角色，另一种选择是由一个小组来承担该角色。

许多帽子并没有正式化。正式化的帽子有一份章程，明确帽子的具体目的以及它的特权和责任。编写这些章程是项目的一个新部分，因此尚未完成所有帽子的正式化。这些帽子描述并非正式化，而是对角色的总结，并提供了相关的章程链接以及联系方式。

## 5. 帽子

### 5.1. 一般帽子

#### 5.1.1. 贡献者

贡献者通过作为开发者、作者、提交问题报告或以其他方式为项目的进展做出贡献。贡献者在 FreeBSD 项目中没有特殊权限。\[[FreeBSD](https://docs.freebsd.org/en/books/dev-model/#freebsd-contributors)]

#### 5.1.2. 提交者

提交者是指拥有将代码或文档添加到版本库的权限的人。提交者必须在过去的 12 个月内进行过一次提交。\[[FreeBSD](https://docs.freebsd.org/en/books/dev-model/#freebsd-developer-handbook)] 一个活跃的提交者是指在过去 12 个月内平均每月进行至少一次提交的人。

值得注意的是，没有技术上的障碍阻止某人获得主项目或子项目的提交权限后，去修改该项目源代码中没有明确许可修改的部分。然而，当提交者想要修改自己之前未涉及过的部分时，他们应该查看日志，了解该区域之前发生过什么，并且查阅 MAINTAINERS 文件，看看该部分的维护者是否对代码修改有任何特殊要求。

#### 5.1.3. 核心团队

核心团队由提交者从提交者池中选举产生，并作为 FreeBSD 项目的董事会。它促进活跃贡献者晋升为提交者，分配人员到明确定义的帽子角色，并且是决定项目未来发展方向的最终裁决者。截至 2004 年 7 月 1 日，核心团队由 9 名成员组成。选举每两年举行一次。

#### 5.1.4. 维护者角色

维护者角色意味着某个人对某一代码区域的贡献负责，并在代码发生争议时拥有最终决定权。这包括主动工作，旨在促进贡献，以及在审查提交时进行的反应性工作。

FreeBSD 源代码中包含了 MAINTAINERS 文件，其中包含每个维护者希望如何进行贡献的一行总结。通过这一通知和联系信息，开发者可以将精力集中在开发工作上，而不是在维护者不可用时陷入缓慢的通信中。

如果维护者长时间无法联系，并且其他人做了大量工作，维护者角色可以在没有维护者批准的情况下转交给其他人。这是基于“维护者角色应该通过行动证明，而不是仅仅通过声明”这一立场。

特定代码的维护者角色不是由小组持有的，而是由个人持有的。

### 5.2. 官方帽子

FreeBSD 项目中的官方帽子是那些在一定程度上正式化的帽子，主要是行政性角色。它们对自己的领域拥有权限和责任。以下列表展示了各个职责线，并给出了每个帽子的描述，包括由谁担任。

#### 5.2.1. 文档项目经理

[FreeBSD 文档项目](https://docs.freebsd.org/en/books/dev-model/#sub-project-documentation) 负责人负责定义和跟踪文档目标，监督文档项目中的提交者。

该帽子由：DocEng 团队 [doceng@FreeBSD.org](mailto:doceng@FreeBSD.org) 持有。[DocEng 章程](https://www.freebsd.org/internal/doceng/)。

#### 5.2.2. 邮件管理员

邮件管理员负责确保邮件正确送达提交者的电子邮件地址。他们还负责确保邮件列表的正常运作，并应采取措施防止邮件受到干扰，如设置防止恶搞、垃圾邮件和病毒的过滤器。

该帽子目前由：邮件管理员团队 [postmaster@FreeBSD.org](mailto:postmaster@FreeBSD.org) 持有。

#### 5.2.3. 发布协调

发布工程团队的职责包括：

* 设置、发布和跟踪官方发布的发布时间表
* 编写并正式化发布工程程序
* 创建和维护代码分支
* 与 Ports 和文档团队协调，确保随着新发布一同发布更新的包和文档
* 与安全团队协调，确保待发布的版本不受新披露的漏洞影响。

有关开发过程的更多信息，请参见 [发布工程](https://docs.freebsd.org/en/books/dev-model/#process-release-engineering) 部分。

该帽子由：发布工程团队 [re@FreeBSD.org](mailto:re@FreeBSD.org) 持有。[发布工程章程](https://www.freebsd.org/releng/charter/)。

#### 5.2.4. 公共关系与企业联络

公共关系与企业联络的职责包括：

* 在 FreeBSD 项目发生重要事件时发布新闻声明。
* 作为与 FreeBSD 项目密切合作的公司的官方联系人。
* 在开源社区和企业界推广 FreeBSD。
* 处理“freebsd-advocacy”邮件列表。

该帽子目前没有被占用。

#### 5.2.5. 安全官

安全官的主要职责是协调与安全社区和 FreeBSD 项目中的其他成员的信息交换。安全官还负责在报告安全问题时采取行动，并在安全方面促进积极的开发行为。

由于担心在补丁可用之前，关于漏洞的信息可能会泄露给怀有恶意意图的人，只有安全官（包括一名官员、一名副官和两名 [Core Team](https://docs.freebsd.org/en/books/dev-model/#role-core) 成员）可以接收关于安全问题的敏感信息。然而，为了创建或实施补丁，安全官可以借助安全官团队 [security-team@FreeBSD.org](mailto:security-team@FreeBSD.org) 来完成工作。

#### 5.2.6. 源代码仓库管理员

源代码仓库管理员是唯一允许直接修改仓库而不使用 [Git](https://docs.freebsd.org/en/books/dev-model/#tool-git) 工具的人。他们负责确保仓库中出现的技术问题能够迅速解决。源代码仓库管理员有权在必要时撤销提交，以解决 Git 技术问题。

该帽子由：源代码仓库管理员 [clusteradm@FreeBSD.org](mailto:clusteradm@FreeBSD.org) 持有。

#### 5.2.7. 选举管理员

选举管理员负责 [Core 选举](https://docs.freebsd.org/en/books/dev-model/#process-core-election) 过程。管理员负责运行和维护选举系统，并且在选举过程中发生小范围的不可预见事件时是最终裁定者。对于重大不可预见事件，必须与 [Core Team](https://docs.freebsd.org/en/books/dev-model/#role-core) 讨论。

该帽子仅在选举期间由人担任。

#### 5.2.8. 网站管理

网站管理帽子的责任是协调全球各地镜像站点的网页更新，并负责主网站的整体结构及其运行的系统。管理人员需要与 [FreeBSD 文档项目](https://docs.freebsd.org/en/books/dev-model/#sub-project-documentation) 协调内容，并担任 "www" 树的维护者。

该帽子由：FreeBSD 网站管理员团队 [www@FreeBSD.org](mailto:www@FreeBSD.org) 持有。

#### 5.2.9. Port 管理员

Port 管理员充当 [Port 子项目](https://docs.freebsd.org/en/books/dev-model/#sub-project-ports) 与核心项目之间的联络人，所有来自该项目的请求应提交给 Port 管理员。

该帽子由：Port 管理团队 [portmgr@FreeBSD.org](mailto:portmgr@FreeBSD.org) 持有。[Portmgr 章程](https://www.freebsd.org/portmgr/charter/)。

#### 5.2.10. 标准

标准帽子的责任是确保 FreeBSD 遵守其承诺遵守的标准，跟进这些标准的发展，并通知 FreeBSD 开发者有关重大变化，从而让他们采取积极的角色，减少标准更新与 FreeBSD 遵从之间的时间差。

该帽子目前由：Garrett Wollman [wollman@FreeBSD.org](mailto:wollman@FreeBSD.org) 持有。

#### 5.2.11. 核心秘书

核心秘书的主要职责是起草并发布最终的核心报告。秘书还负责维护核心议程，确保没有未解决的事项。

该帽子目前由：René Ladan [rene@FreeBSD.org](mailto:rene@FreeBSD.org) 持有。

#### 5.2.12. Bugmeister

Bugmeister 负责确保维护数据库正常运行，条目正确分类并且没有无效条目。他们还负责监督 bugbusters。

该帽子目前由：Bugmeister 团队 [bugmeister@FreeBSD.org](mailto:bugmeister@FreeBSD.org) 持有。

#### 5.2.13. 捐赠联络官

捐赠联络官的任务是将需要开发者的开发需求与愿意捐赠的人或组织匹配起来。

该帽子由：捐赠联络办公室 [donations@FreeBSD.org](mailto:donations@FreeBSD.org) 持有。[捐赠联络章程](https://www.freebsd.org/donations/)。

#### 5.2.14. 管理员

（也称为 "FreeBSD 集群管理员"）

管理员团队由负责管理项目依赖的计算机的人员组成，这些计算机用于协调项目的分布式工作和通信。该团队主要由那些拥有服务器物理访问权限的人员组成。

该帽子由：管理员团队 [admin@FreeBSD.org](mailto:admin@FreeBSD.org) 持有。

### 5.3. 依赖于流程的帽子

#### 5.3.1. 报告发起人

最初负责提交问题报告的人。

#### 5.3.2. Bugbuster

Bugbuster 是一个人，负责找到合适的人解决问题，或关闭重复的或无关紧要的问题报告（PR）。

#### 5.3.3. 导师

导师是一个承诺帮助新提交者熟悉项目的开发者，确保新提交者的设置是有效的，知道在工作中需要的工具，并了解对行为的期望。

#### 5.3.4. 供应商

提供外部代码并接收补丁的人或组织。

#### 5.3.5. 审核者

在提交审核请求的邮件列表中的人员。

以下部分将描述已定义的项目流程。那些不受这些流程管理的问题通常基于类似情况下的惯例进行处理。

## 6. 流程

### 6.1. 添加新提交者和移除旧提交者

Core 团队负责授予和撤销贡献者的提交权限。这只能通过在核心邮件列表上的投票来完成。Port 和文档子项目可以授予从事这些项目的人员提交权限，但至今未曾撤销此类权限。

通常，一名提交者会推荐一个贡献者给 Core。通常，贡献者或外部人员主动联系 Core 请求成为提交者的做法是不被推崇的，并且通常会被拒绝。

如果开发者的特定兴趣领域可能与其他提交者的维护领域重叠，便会征求这些维护者的意见。然而，通常是由该提交者推荐该开发者。

当贡献者被授予提交者身份时，会为其分配一名导师。一般情况下，推荐新提交者的提交者会担任新提交者的导师。

当贡献者获得提交权限后，会从 [Core Secretary](https://docs.freebsd.org/en/books/dev-model/#role-core-secretary)、[Ports Manager](https://docs.freebsd.org/en/books/dev-model/#role-ports-manager) 或 [nik@freebsd.org](mailto:nik@freebsd.org) 发送一封 PGP 签名邮件，邮件内容确认新帐户的批准，并发送给 [admins@freebsd.org](mailto:admins@freebsd.org)、指定的导师、新提交者和 Core。导师随后会从新提交者那里收集密码行、[Secure Shell](https://docs.freebsd.org/en/books/dev-model/#tool-ssh2) 公钥和 PGP 密钥，并将其发送给管理员。创建新帐户后，导师将激活提交权限，并指导新提交者完成剩余的初始设置。

![请参阅下文的屏幕阅读器友好版本](https://docs.freebsd.org/images/books/dev-model/proc-add-committer.png)

**图 3. 过程总结：添加新提交者**

当贡献者提交一段代码时，接收的提交者可能会建议该贡献者获得提交权限。如果他们将此建议提交给 Core，Core 将就此建议进行投票。如果投票通过，则为新提交者分配导师，并要求新提交者通过邮件向管理员提供详细信息以创建帐户。此后，新提交者即可进行第一次提交，按照惯例通常是将自己的名字添加到提交者列表中。

回想一下，提交者被视为在过去 12 个月内曾提交过代码的人。然而，直到 18 个月未进行任何提交后，提交权限才会被撤销。

然而，对于这种撤销权限，并没有自动的程序。有关未因时间触发的提交权限反应，请参见 [第1.5.8节](https://docs.freebsd.org/en/books/dev-model/#process-reactions)。

![请参阅下文的屏幕阅读器友好版本](https://docs.freebsd.org/images/books/dev-model/proc-rm-committer.png)

**图4. 过程总结：移除提交者**

当核心团队决定清理提交者列表时，他们会检查哪些提交者在过去 18 个月内没有进行提交。没有提交的提交者将被撤销提交权限，并由管理员删除帐户。

提交者也可以请求撤回其提交权限，如果由于某些原因他们不再积极参与项目的提交工作。在这种情况下，提交权限可以在稍后的时间恢复，前提是提交者请求恢复。

此过程中的角色：

1. [核心团队](https://docs.freebsd.org/en/books/dev-model/#role-core)
2. [贡献者](https://docs.freebsd.org/en/books/dev-model/#role-contributor)
3. [提交者](https://docs.freebsd.org/en/books/dev-model/#role-committer)
4. [维护者](https://docs.freebsd.org/en/books/dev-model/#role-maintainer)
5. [导师](https://docs.freebsd.org/en/books/dev-model/#role-mentor)

### 提交代码

在 FreeBSD 项目中，提交新代码或修改代码是最常见的过程之一，通常每天都会发生多次。代码的提交只能由“提交者”（committer）进行。提交者可以提交自己编写的代码、提交给他们的代码，或通过 [问题报告](https://docs.freebsd.org/en/books/dev-model/#model-pr) 提交的代码。

当开发者编写的代码较为复杂时，他们应当寻求社区的代码审查。这通常通过向相关邮件列表发送邮件请求审查来完成。在提交代码进行审查之前，开发者应确保代码能够正确编译并且所有相关测试都能通过，这叫做“提交前测试”（pre-commit test）。当收到贡献的代码时，提交者也应以相同的方式进行审查和测试。

当提交的代码涉及到外部 [供应商](https://docs.freebsd.org/en/books/dev-model/#role-vendor) 提供的部分时，维护者应确保将补丁反馈给供应商。这符合开源哲学，并且有助于保持与外部项目的同步，因为每次新版本发布时，补丁不需要重新应用。

在代码已通过审查且不再需要进一步修改后，代码将提交到开发分支 -CURRENT。如果该更改还适用于 -STABLE 分支或其他分支，提交者将设置一个“从当前合并”（“MFC”）倒计时。倒计时结束后，系统将自动发送电子邮件提醒提交者将该更改提交到 -STABLE 分支（并可能提交到安全分支）。只有安全关键的更改应合并到安全分支。

延迟提交到 -STABLE 和其他分支允许进行“并行调试”，即在广泛的配置上测试已提交的代码。这使得 -STABLE 分支的更改包含更少的错误，从而得名。

![参见下文的屏幕阅读友好版本。](https://docs.freebsd.org/images/books/dev-model/proc-commit.png)

**图 5. 流程总结：提交者提交代码**

当提交者编写了代码并准备提交时，他们首先需要确定代码是否足够简单，可以直接提交而无需审查，或者是否需要先由开发者社区进行审查。如果代码很简单或已经经过审查，且提交者不是维护者，他们应该在继续之前咨询维护者。如果代码是由外部供应商提供的，维护者应创建一个补丁并发送回供应商。然后代码被提交并由用户部署。如果用户发现代码有问题，将报告给提交者，提交者可以回去修复补丁。如果涉及到供应商，供应商可以选择实施或忽略该补丁。

![参见上文和下文的屏幕阅读友好版本。](https://docs.freebsd.org/images/books/dev-model/proc-contrib.png)

**图 6. 流程总结：贡献者提交代码**

当贡献者做出代码贡献时，与提交者的不同之处在于他们通过 Bugzilla 界面提交代码。这个报告将由维护者接收，维护者审核代码并提交。

此过程中涉及的角色有：

1. [提交者](https://docs.freebsd.org/en/books/dev-model/#role-committer)
2. [贡献者](https://docs.freebsd.org/en/books/dev-model/#role-contributor)
3. [供应商](https://docs.freebsd.org/en/books/dev-model/#role-vendor)
4. [审阅者](https://docs.freebsd.org/en/books/dev-model/#role-reviewer)

### 核心团队选举

核心团队选举至少每两年举行一次。^\[[8](https://docs.freebsd.org/en/books/dev-model/#_footnotedef_8 "查看脚注。")]^ 选举九名核心成员。如果核心成员人数低于七人，则会举行新选举。如果至少 1/3 的活跃提交者要求，也可以举行新选举。

当选举即将举行时，核心团队会提前至少 6 周宣布此事，并任命选举经理来负责选举工作。

只有提交者才能被选为核心团队成员。候选人必须在选举开始前至少一周提交其候选声明，但可以在投票开始前继续修改声明。候选人会在 [候选人名单](http://election.uk.freebsd.org/candidates.html) 中列出。在撰写选举声明时，候选人必须回答选举经理提出的几个标准问题。

在选举期间，必须严格遵守提交者过去 12 个月内有提交代码的规则。只有这些提交者有资格投票。

在投票时，提交者可以支持最多九名候选人。投票期为四周，在此期间，开发者邮件列表会向所有提交者发送投票提醒。

选举结果会在选举结束后一周公布，新选举的核心团队团队将在结果发布后一周正式上任。

如果投票结果出现平局，由新当选的核心团队成员解决此问题。

选票和候选人声明将被存档，但存档内容不会公开。

![参见下文的屏幕阅读友好版本。](https://docs.freebsd.org/images/books/dev-model/proc-elections.png)

**图 7. 流程总结：核心团队选举**

核心团队公布选举并选择选举经理准备选举工作，候选人可以提交候选声明。提交者随后投票。投票结束后，公布选举结果，新的核心团队接管工作。

核心团队选举涉及的角色有：

* [核心团队](https://docs.freebsd.org/en/books/dev-model/#role-core)
* [提交者](https://docs.freebsd.org/en/books/dev-model/#role-committer)
* [选举经理](https://docs.freebsd.org/en/books/dev-model/#role-election-manager)

### 新特性开发

在 FreeBSD 项目中，有一些子项目负责开发新特性。这些项目通常由一个人负责 \[[Jørgensen](https://docs.freebsd.org/en/books/dev-model/#jorgensen2001)]。每个子项目可以根据自己的需要自由组织开发。然而，当项目合并到 -CURRENT 分支时，它必须遵循项目的相关指导方针。当代码在 -CURRENT 分支中经过充分测试并被认为稳定且与 -STABLE 分支相关时，它会被合并到 -STABLE 分支。

项目的需求来源于开发者的愿望、社区的直接请求（如通过邮件、问题报告），商业资金支持特性开发，或来自科学界的贡献。那些属于某个开发者职责范围内的愿望会被分配给该开发者，并由其在请求和个人愿望之间进行时间优先级的调整。常见的做法是维护一个由项目团队管理的待办事项列表（TODO-list）。那些不属于某个开发者职责范围的请求会被汇总到待办事项列表中，除非有人自愿承担责任。所有的请求、分配和跟进工作都通过 [Bugzilla](https://docs.freebsd.org/en/books/dev-model/#tool-bugzilla) 工具来处理。

需求分析有两种方式进行。收到的请求会在邮件列表中讨论，讨论的范围包括主项目和相关子项目，或者是由这些请求衍生出的子项目。此外，子项目中的个别开发者会评估请求的可行性，并在其中进行优先级排序。除去已进行讨论的邮件存档外，这一阶段不会产生任何结果，亦不会合并到主项目中。

由于请求的优先级是由个别开发者基于他们认为有趣、必要或者有资金支持的工作来决定的，因此没有针对哪些请求应该作为需求以及如何正确实现这些请求的整体策略或优先级。不过，大多数开发者对哪些问题更重要有一些共同的看法，他们可以向发布工程团队请求指导。

项目的验证阶段分为两部分。在将代码提交到当前分支之前，开发者会请求同行对其代码进行审查。审查大多通过功能测试进行，但代码审查也是非常重要的。当代码提交到分支后，会进行更广泛的功能测试，如果代码表现不符合预期，可能会触发进一步的代码审查和调试。这第二种验证形式可以视为结构性验证。尽管子项目本身可能编写正式的测试，如单元测试，但这些测试通常不会被主项目收集，并且在代码提交到当前分支之前通常会被移除。^\[[9](https://docs.freebsd.org/en/books/dev-model/#_footnotedef_9 "查看脚注。")]^


### 6.2. 维护

对于项目来说，每个源代码区域至少有一个对该区域非常了解的人是非常有利的。某些代码部分有指定的维护者，其他部分有事实上的维护者，还有一些系统部分没有维护者。维护者通常是子项目中编写并集成该代码的人员，或者是将代码从原本平台移植过来的人员。^\[[10](https://docs.freebsd.org/en/books/dev-model/#_footnotedef_10 "查看脚注。")]^ 维护者的工作是确保代码与其所来自的项目保持同步（如果是外部贡献的代码），并应用社区提交的补丁或修复发现的问题。

FreeBSD 项目的大部分工作是维护工作。\[[Jørgensen](https://docs.freebsd.org/en/books/dev-model/#jorgensen2001)] 提出了一个展示变更生命周期的图示。

Jørgenssen 的变更集成模型

| 阶段    | 成功时进入 | 失败时进入 |
| ----- | ----- | ----- |
| 代码    | 审查    |       |
| 审查    | 提交前测试 | 代码    |
| 提交前测试 | 开发版发布 | 代码    |
| 开发版发布 | 并行调试  | 代码    |
| 并行调试  | 生产版发布 | 代码    |
| 生产版发布 |       | 代码    |

在这里，“开发版发布”指的是 -CURRENT 分支，而“生产版发布”指的是 -STABLE 分支。 “提交前测试”是指同伴开发者在被要求时进行的功能测试，或者是尝试代码以确定子项目的状态。“并行调试”是指当代码包含到 -CURRENT 分支后进行的功能测试，这可能会触发更多的审查和调试。

截至本文写作时，项目中有 269 位提交者。当他们将变更提交到某个分支时，这就构成了一个新的版本。社区中的用户非常常见地会跟踪特定的分支。新版本的即时存在使得变更能够立即广泛可用，并允许社区快速反馈。这也使得社区能够在他们关心的问题上获得预期的响应时间。这使得社区更为积极参与，从而提供更多且更好的反馈，进一步促进了更多的维护工作，并最终有助于创造更好的产品。

在对树中那些提交者不熟悉的历史部分进行代码更改之前，提交者需要阅读提交日志，以了解某些特性为何以当前的方式实现，以避免犯下之前已经思考过或解决过的错误。

### 6.3. 问题报告

在 FreeBSD 10 之前，FreeBSD 包含了一个名为 `send-pr` 的问题报告工具。问题包括 bug 报告、功能请求、功能增强以及通知项目中包含的新版本外部软件。尽管 `send-pr` 可用，但用户和开发者被鼓励使用我们的 [问题报告表单](https://bugs.freebsd.org/submit/) 提交问题。

问题报告被发送到一个电子邮件地址，然后插入到问题报告维护数据库中。一个 [Bugbuster](https://docs.freebsd.org/en/books/dev-model/#role-bugbuster) 会对问题进行分类，并将其发送到项目中的正确小组或维护者。在有人接手该报告后，报告会进入分析阶段。此分析包括验证问题并思考解决方案。通常需要报告发起人或甚至 FreeBSD 社区的反馈。一旦问题的补丁创建完成，发起人可能会被要求进行测试。最后，经过验证的补丁将被集成到项目中，并在适用的情况下进行文档记录。此后，它将按照 [维护](https://docs.freebsd.org/en/books/dev-model/#model-maintenance) 部分中描述的常规维护周期进行处理。问题报告可以处于以下几种状态：开放、分析、反馈、已修复、挂起和关闭。挂起状态是指由于缺乏信息，或任务需要的工作量过大，目前没有人处理的情况。

![参见下方段落获取屏幕阅读器友好的版本。](https://docs.freebsd.org/images/books/dev-model/proc-pr.png)

**图 8. 过程总结：问题报告**

问题由报告发起人报告。然后，Bugbuster 会对问题进行分类，并交给正确的维护者。维护者验证问题并与发起人讨论，直到获得足够的信息来创建有效的补丁。补丁完成后，将被提交并关闭问题报告。

这一过程中的角色有：

1. [报告发起人](https://docs.freebsd.org/en/books/dev-model/#role-problem-originator)
2. [维护者](https://docs.freebsd.org/en/books/dev-model/#role-maintainer)
3. [Bugbuster](https://docs.freebsd.org/en/books/dev-model/#role-bugbuster)

[[FreeBSD](https://docs.freebsd.org/en/books/dev-model/#freebsd-handle-pr)].

### 应对不当行为

[[FreeBSD](https://docs.freebsd.org/en/books/dev-model/#freebsd-committer)] 规定了提交者应遵守的一些规则。然而，偶尔会有这些规则被打破。为应对不当行为，以下规则明确了哪些行为会导致提交者的提交权限被暂停，以及暂停的时长：

* 在代码冻结期间提交，且未获得发布工程团队批准 - 暂停 2 天
* 向安全分支提交，且未获得批准 - 暂停 2 天
* 提交战争 - 参与各方暂停 5 天
* 不礼貌或不当行为 - 暂停 5 天

为了使暂停有效，任何一位核心成员都可以在未在 `core` 邮件列表上讨论的情况下执行暂停。反复违规者可以由核心团队 2/3 投票，接受更严厉的惩罚，包括永久撤销提交权限（然而，由于其固有的争议性，这通常是作为最后手段）。所有的暂停都会公布在 `developers` 邮件列表上，这个列表仅供提交者使用。

需要注意的是，技术错误不会导致暂停。所有惩罚均来自违反社交礼仪的行为。

参与这一过程的角色有：

* [核心团队](https://docs.freebsd.org/en/books/dev-model/#role-core)
* [提交者](https://docs.freebsd.org/en/books/dev-model/#role-committer)

### 6.4. 发布工程

FreeBSD 项目有一个发布工程团队，由一名首席发布工程师负责创建可以通过网络发布给用户社区或在零售商店销售的 FreeBSD 版本。由于 FreeBSD 支持多平台，并且不同架构的版本同时发布，团队中每个架构都有一个负责人。此外，团队中还设有负责协调质量保证、构建软件包集以及更新文档集的角色。当提到发布工程师时，通常是指发布工程团队的代表。

当发布临近时，FreeBSD 项目的形态会发生一些变化。发布计划会制定出来，其中包括功能冻结、代码冻结、过渡版发布和最终发布。功能冻结意味着未经发布工程师明确同意，不允许在分支中提交新功能。代码冻结则意味着未经发布工程师明确同意，不允许对代码（如修复 bug）进行更改。功能冻结和代码冻结被称为“稳定化”过程。在发布过程中，发布工程师拥有完全的权力回退到旧版本的代码，从而“撤销”变更，若他们发现这些变更不适合纳入发布。

有三种不同类型的发布：

1. .0 版本是主要版本的首次发布。这些版本从 -CURRENT 分支中分支出来，由于 -CURRENT 分支的不稳定性质，发布工程周期明显较长。
2. .X 版本是 -STABLE 分支的发布。它们计划每 4 个月发布一次。
3. .X.Y 版本是安全版本，跟随 .X 分支发布。这些版本仅在自上次发布以来合并了足够的安全修复时才会发布。新功能很少包含，安全团队在这些版本中的参与程度远高于常规发布。

对于 -STABLE 分支的发布，发布过程从预定发布日期前 45 天开始。在第一阶段，即前 15 天，开发者将其在 -CURRENT 中的变更合并到发布分支中。如果这段时间结束，代码将进入为期 15 天的代码冻结期，仅允许修复 bug、更新文档、安全修复和少量设备驱动更改。这些变更必须事先获得发布工程师的批准。在最后 15 天的周期开始时，将创建一个供广泛测试的发布候选版本。在此期间，除非是重要的 bug 修复和安全更新，否则不太可能允许其他更新。在这最后的阶段，所有发布版本都被视为发布候选版本。发布过程结束时，将创建一个新的版本号发布，其中包括网站上的二进制分发和 CD-ROM 镜像的创建。然而，在发布公告发送到 freebsd-announce 邮件列表之前，该版本不会被视为“真正发布”。任何被标记为“发布”的版本在此之前都可能仍在进行中，且在 PGP 签名的公告发送之前可能会有所更改。^\[[11](https://docs.freebsd.org/en/books/dev-model/#_footnotedef_11 "查看脚注")]^。

-STABLE 分支的发布过程与 -CURRENT 分支相似，但时间框架是其两倍。发布过程在发布 8 周前开始，并公布发布时间表。在发布过程开始两周后，功能冻结开始，性能调整应尽量减少。发布前四周，将提供一个正式的 beta 版本。发布前两周，代码将正式分支成新版本，并获得发布候选状态。与 -STABLE 分支的发布工程一样，发布候选的代码冻结期会被加固。然而，主开发分支上的开发可以继续进行。除了这些差异外，发布工程过程是类似的。

\*.0 版本会进入自己的分支，主要面向早期采用者。该分支会经历稳定化过程，直到 [发布工程团队](https://docs.freebsd.org/en/books/dev-model/#role-releng) 确定稳定性需求得到满足时，该分支才会变成 -STABLE，而 -CURRENT 将针对下一个主要版本进行开发。尽管大多数情况下是通过 \*.1 版本完成这一过程，但这并不是强制要求。

大多数版本的发布是在预定时间到来时进行的，该时间间隔被认为是自上次发布以来的足够长时间。目标是每 18 个月发布一次重大版本，每 4 个月发布一次次要版本。用户社区明确表示，安全性和稳定性不能因自设的最后期限和目标发布日期而受到牺牲。为了避免时间延误过长，特别是在安全性和稳定性问题方面，在提交更改到 -STABLE 时需要额外的纪律性。

1. 制定发布计划
2. 功能冻结
3. 代码冻结
4. 创建分支
5. 发布候选版本
6. 稳定发布（如有必要，循环回到上一阶段；当发布被认为稳定时，继续下一阶段）
7. 构建软件包
8. 提醒镜像站点
9. 发布版本

\[[FreeBSD](https://docs.freebsd.org/en/books/dev-model/#freebsd-releng)]

## 7. 工具

支持开发过程的主要工具有 Bugzilla、Mailman 和 OpenSSH。这些是外部开发的工具，在开源世界中广泛使用。

### 7.1. Git

Git 是一个用于处理文本文件的多个版本并跟踪谁提交了哪些更改以及为何更改的系统。一个项目存在于一个“代码库”中，不同的版本被视为不同的“分支”。

### 7.2. Bugzilla

Bugzilla 是一个维护数据库，包含一套工具，用于在中央站点跟踪 bug。它支持发送和处理 bug 的跟踪过程，并能够查询和更新数据库、编辑 bug 报告。该项目使用其 web 界面向项目的中央 Bugzilla 服务器发送“问题报告”。提交者还可以使用 web 和命令行客户端。

### 7.3. Mailman

Mailman 是一个自动化管理邮件列表的程序。FreeBSD 项目使用它运行 16 个公共列表、60 个技术列表、4 个限制性列表和 5 个包含 Git 提交日志的列表。它还被用于其他人和项目在 FreeBSD 社区中设置和使用的多个邮件列表。公共列表是面向公众的列表，技术列表主要用于特定领域的开发，封闭列表则用于不面向公众的内部沟通。项目中的大多数沟通都是通过这 85 个列表进行的 \[[FreeBSD](https://docs.freebsd.org/en/books/dev-model/#ref-bsd-handbook)，附录 C]。

### 7.4. Pretty Good Privacy

Pretty Good Privacy，简称 PGP，是一个使用公钥体系的加密系统，允许人们对信息进行数字签名和/或加密，以确保双方之间的安全通信。发送信息给多个接收者时会使用签名，这样他们就可以验证信息在传输过程中是否被篡改。在 FreeBSD 项目中，这是确保信息确实由声称编写它的人写成，并且在传输过程中未被修改的主要方式。

### 7.5. Secure Shell

Secure Shell 是一种标准，用于安全地登录远程系统并执行远程系统上的命令。它允许在两个系统之间建立并保护其他连接，称为隧道。此标准有两个主要版本，而 FreeBSD 项目只使用第二个版本。该标准最常见的实现是 OpenSSH，它是项目主发行版的一部分。由于其源代码更新频率高于 FreeBSD 发布，最新版本也可以在 Ports 树中找到。

## 8. 子项目

子项目的形成是为了减少协调开发人员群体所需的沟通量。当一个问题区域足够孤立时，大部分沟通将局限于专注于该问题的团队内部，减少了与其他团队的沟通需求。

### 8.1. Ports 子项目

“Port” 是一组元数据和补丁，用于正确地获取、编译和安装外部软件到 FreeBSD 系统中。Port 的数量增长速度惊人，以下图表展示了这一变化。

![请参阅下面的段落以获取适合屏幕阅读器的版本。](https://docs.freebsd.org/images/books/dev-model/portsstatus.svg)

**图 9. 1995 年至 2022 年期间添加的 Port 数量**

[image::portsstatus.svg](https://docs.freebsd.org/en/books/dev-model/#fig-ports) 显示了 1995 年至 2022 年期间 FreeBSD 上可用的 Port 数量。图表显示，Port 数量最初呈指数增长，从 2001 年中期到 2007 年中期以每年约 2000 个 Port 的线性速度增长，然后增长率开始放缓。

由于 Port 所描述的外部软件通常在持续开发中，维护 Port 所需的工作量已经非常庞大，且还在增加。这导致 FreeBSD 项目中的 Ports 部分拥有了更强大的结构，越来越多地成为 FreeBSD 项目的一个子项目。

Ports 拥有自己的核心团队，由 [Ports 经理](https://docs.freebsd.org/en/books/dev-model/#role-ports-manager) 领导，该团队可以在不需要 FreeBSD Core 批准的情况下任命提交者。与 FreeBSD 项目不同，后者的许多维护工作经常会得到提交权限，Ports 子项目包含了许多活跃的维护者，但他们并不是提交者。

与主项目不同，Ports 树没有分支。每个 FreeBSD 发布都遵循当前的 Ports 集合，因此可以获取更新的信息，了解在哪里找到程序以及如何构建它们。然而，这意味着一个依赖系统的 Port 可能需要根据运行的 FreeBSD 版本进行调整。

由于 Ports 仓库没有分支，因此无法保证任何 Port 能在除 -CURRENT 和 -STABLE 之外的版本上运行，特别是较旧的次要版本。缺乏必要的基础设施和志愿者时间来保证这一点。

为了提高沟通效率，依赖于 Ports 的团队，如发布工程团队，拥有各自的 Ports 联络人。

### 8.2. FreeBSD 文档项目

FreeBSD 文档项目始于 1995 年 1 月。从最初的一个项目负责人、四个团队负责人和 16 名成员，现已发展为 44 名提交者。文档邮件列表的成员接近 300 人，表明围绕它形成了一个相当大的社区。

文档项目的目标是提供 FreeBSD 项目的良好且有用的文档，从而让新用户更容易熟悉系统，并为用户详细介绍高级功能。

文档项目的主要任务是处理“FreeBSD 文档集”中的当前项目，并将文档翻译成其他语言。

与 FreeBSD 项目类似，文档分为相同的分支。这是为了确保每个版本的文档始终保持更新。仅在安全分支中修正文档错误。

与 Ports 子项目类似，文档项目可以在不需要 FreeBSD Core 批准的情况下任命文档提交者 \[[FreeBSD](https://docs.freebsd.org/en/books/dev-model/#freebsd-doceng-charter)]。

文档项目拥有 [入门指南](https://docs.freebsd.org/en/books/fdp-primer/)，该指南用于向新成员介绍标准工具和语法，同时也是在项目中工作的参考资料。

## 参考文献

\[Brooks, 1995] Frederick P. Brooks. Copyright © 1975, 1995 Pearson Education Limited. 0201835959. Addison-Wesley Pub Co. *The Mythical Man-Month. Essays on Software Engineering, Anniversary Edition (2nd Edition)*.

\[Saers, 2003] Niklas Saers. Copyright © 2003. *A project model for the FreeBSD Project*. Candidatus Scientiarum thesis. [http://niklas.saers.com/thesis](http://niklas.saers.com/thesis).

\[Jørgensen, 2001] Niels Jørgensen. Copyright © 2001. *Putting it All in the Trunk. Incremental Software Development in the FreeBSD Open Source Project*. [http://www.dat.ruc.dk/\~nielsj/research/papers/freebsd.pdf](http://www.dat.ruc.dk/~nielsj/research/papers/freebsd.pdf).

\[PMI, 2000] Project Management Institute. Copyright © 1996, 2000 Project Management Institute. 1-880410-23-0. Project Management Institute. Newtown Square Pennsylvania USA. *PMBOK Guide. A Guide to the Project Management Body of Knowledge, 2000 Edition*.

\[FreeBSD, 2000A] Copyright © 2002 The FreeBSD Project. *Core Bylaws*. [https://www.freebsd.org/internal/bylaws/](https://www.freebsd.org/internal/bylaws/).

\[FreeBSD, 2002A] Copyright © 2002 The FreeBSD Documentation Project. *FreeBSD Developer’s Handbook*. [Developers Handbook](https://docs.freebsd.org/en/books/developers-handbook/).

\[FreeBSD, 2002B] Copyright © 2002 The FreeBSD Project. *Core team election 2002*. [http://election.uk.freebsd.org/candidates.html](http://election.uk.freebsd.org/candidates.html).

\[FreeBSD, 2002C] Dag-Erling Smørgrav and Hiten Pandya. Copyright © 2002 The FreeBSD Documentation Project. *The FreeBSD Documentation Project. Problem Report Handling Guidelines*. [Problem Report Handling Guidelines](https://docs.freebsd.org/en/articles/pr-guidelines/).

\[FreeBSD, 2002D] Dag-Erling Smørgrav. Copyright © 2002 The FreeBSD Documentation Project. *The FreeBSD Documentation Project. Writing FreeBSD Problem Reports*. [Writing FreeBSD Problem Reports](https://docs.freebsd.org/en/articles/problem-reports/).

\[FreeBSD, 2001] Copyright © 2001 The FreeBSD Documentation Project. *The FreeBSD Documentation Project. Committers Guide*. [Committer’s Guide](https://docs.freebsd.org/en/articles/committers-guide/).

\[FreeBSD, 2002E] Murray Stokely. Copyright © 2002 The FreeBSD Documentation Project. *The FreeBSD Documentation Project. FreeBSD Release Engineering*. [FreeBSD Release Engineering](https://docs.freebsd.org/en/articles/releng/).

\[FreeBSD, 2003A] The FreeBSD Documentation Project. *FreeBSD Handbook*. [FreeBSD Handbook](https://docs.freebsd.org/en/books/handbook/).

\[FreeBSD, 2002F] Copyright © 2002 The FreeBSD Documentation Project. *The FreeBSD Documentation Project. Contributors to FreeBSD*. [Contributors to FreeBSD](https://docs.freebsd.org/en/articles/contributors/).

\[FreeBSD, 2002G] Copyright © 2002 The FreeBSD Project. *The FreeBSD Project. Core team elections 2002*. [http://election.uk.freebsd.org](http://election.uk.freebsd.org/).

\[FreeBSD, 2002H] Copyright © 2002 The FreeBSD Project. *The FreeBSD Project. Commit Bit Expiration Policy*. 2002/04/06 15:35:30. [https://www.freebsd.org/internal/expire-bits/](https://www.freebsd.org/internal/expire-bits/).

\[FreeBSD, 2002I] Copyright © 2002 The FreeBSD Project. *The FreeBSD Project. New Account Creation Procedure*. 2002/08/19 17:11:27. [https://www.freebsd.org/internal/new-account/](https://www.freebsd.org/internal/new-account/).

\[FreeBSD, 2003B] Copyright © 2002 The FreeBSD Documentation Project. *The FreeBSD Documentation Project. FreeBSD DocEng Team Charter*. 2003/03/16 12:17. [https://www.freebsd.org/internal/doceng/](https://www.freebsd.org/internal/doceng/).

\[Lehey, 2002] Greg Lehey. Copyright © 2002 Greg Lehey. *Two years in the trenches. The evolution of a software project*. [http://www.lemis.com/grog/In-the-trenches.pdf](http://www.lemis.com/grog/In-the-trenches.pdf).

---

[1](https://docs.freebsd.org/en/books/dev-model/#_footnoteref_1). 这与 Brooks 定律密切相关，后者认为在一个项目已经很晚的时候增加一个人，反而会使项目进展更加迟缓，因为这会增加沟通的需求。项目模型是用来减少沟通需求的工具。

[2](https://docs.freebsd.org/en/books/dev-model/#_footnoteref_2). 统计数据是通过计算 2005 年 4 月 1 日之前，由 portsdb 获取的文件中的条目数生成的。portsdb 是 port sysutils/portupgrade 的一部分。

[3](https://docs.freebsd.org/en/books/dev-model/#_footnoteref_3). 该数字是通过对 2004 年 1 月 1 日至 2004 年 12 月 31 日的期间进行检查得出的。

[4](https://docs.freebsd.org/en/books/dev-model/#_footnoteref_4). 例如，蓝牙栈的开发最初作为子项目进行，直到它被认为足够稳定，可以合并到 -CURRENT 分支中。现在它是 FreeBSD 核心系统的一部分。

[5](https://docs.freebsd.org/en/books/dev-model/#_footnoteref_5). 根据 Kirk McKusick 的说法，在开发 UNIX 操作系统 20 年后，接口大部分已经解决。因此，不需要太多的设计。然而，系统的新应用和新硬件导致某些实现比过去的优选实现更为有益。一个例子是引入网页浏览，它使得普通的 TCP/IP 连接变成了一个短时间的数据传输，而不是长时间的稳定数据流。

[6](https://docs.freebsd.org/en/books/dev-model/#_footnoteref_6). 这种情况首次出现在 4.5-RELEASE 版本中，但同时也为 4.3-RELEASE 和 4.4-RELEASE 创建了安全分支。

[7](https://docs.freebsd.org/en/books/dev-model/#_footnoteref_7). “稳定”一词的术语重叠，导致一些混淆。-STABLE 分支仍然是一个开发分支，其目标是对大多数人有用。如果系统永远不能接受未在部署时宣布的更改，那么该系统应该运行安全分支。

[8](https://docs.freebsd.org/en/books/dev-model/#_footnoteref_8). 首次进行 Core 选举是在 2000 年 9 月。

[9](https://docs.freebsd.org/en/books/dev-model/#_footnoteref_9). 然而，构建系统（make world）时执行的测试越来越多。然而，这些测试仍然是一个非常新的补充，目前尚未建立系统的框架。

[10](https://docs.freebsd.org/en/books/dev-model/#_footnoteref_10). sendmail 和 named 是已从其他平台合并的代码示例。

[11](https://docs.freebsd.org/en/books/dev-model/#_footnoteref_11). 许多商业供应商使用这些镜像来制作 CD-ROM，并在零售店销售。
