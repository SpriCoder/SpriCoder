# SpriCoder GitHub 主页设计调研与建议

> 调研日期：2026-10-11
> 目标仓库：`SpriCoder/SpriCoder`（GitHub 个人主页仓库）
> 范围：GitHub 官方能力、Apache IoTDB/TsFile 一手项目资料、成熟开源维护者 Profile README、动态组件与可访问性。
> 说明：本文是设计调研，不修改 `README.md`；“现状”指当前工作区可见内容，“建议”是待确认的设计方案。

## 1. 先确定主页要完成什么

主页的首要任务不是展示尽可能多的徽章，而是让访客在首屏回答三个问题：

1. 你是谁，当前承担什么开源职责？
2. 你长期解决哪类技术问题？
3. 访客下一步应阅读哪个项目、文章或联系方式？

GitHub 官方把 Profile README 定义为个人简介、值得展示的贡献和社区帮助入口；个人主页还包括个人资料、贡献活动、置顶项目、状态和成就等独立区域。因此 README 应负责“叙事和导航”，项目数量、贡献热图和置顶仓库应由 GitHub 主页原生区域承接。[GitHub：About your profile](https://docs.github.com/en/account-and-profile/concepts/personal-profile)

官方的简历指南建议 README 包含简介、技能、经历、精选项目和成就，并建议置顶 3–5 个最能代表目标方向的仓库；项目仓库自身还要有清楚的 README、运行/演示和测试信息。[GitHub：Using your GitHub profile to enhance your resume](https://docs.github.com/en/account-and-profile/tutorials/using-your-github-profile-to-enhance-your-resume)

## 2. 与 SpriCoder 最匹配的定位

### 已有事实（来自当前 README 与一手项目页面）

- 当前 README 已声明 **Apache IoTDB PMC Member**、**Apache TsFile Committer**，并链接到两个 Apache GitHub 仓库。
- 当前 README 提到 Apache IoTDB、Apache TsFile、IoT Benchmark、个人博客，并包含 Trophy、GitHub Stats、Profile Views、Activity Graph 四类动态图片。
- Apache IoTDB 官方网站将 IoTDB 定义为面向工业物联网的时序数据库，强调边缘–云协同、采集/存储/管理/分析一体化、多协议、读写吞吐和生态集成。[Apache IoTDB](https://iotdb.apache.org/)
- Apache TsFile 官方网站将 TsFile 定义为面向工业时序数据的高性能列式存储文件格式，强调多语言接口、压缩、读写吞吐、随机访问和与 IoTDB、Spark、Flink 的集成。[Apache TsFile](https://tsfile.apache.org/)
- IoT Benchmark 官方仓库将其定义为面向工业物联网时序数据库的基准测试工具，支持跨平台、多种工作负载、正确性验证和结果可视化；因此主页可以把它作为“评测工具”单独展示，而不是泛化成“性能结果”。[IoT Benchmark](https://github.com/thulab/iot-benchmark)
- IoTDB 社区页面把 PMC Member 描述为因对项目演进有贡献而当选的角色，并列出项目决策、开发支持、社区建设和方向引导等职责。[IoTDB：About the Community](https://iotdb.apache.org/Community/About-the-Community.html)
- ASF 的 PMC 治理说明指出，PMC 对项目治理和正式发布负责，PMC 成员以项目社区利益为出发点参与决策。[ASF：PMC Governance](https://www.apache.org/foundation/governance/pmcs.html)

### 建议的核心定位

建议把主页定位为：

> **Open-source database engineer and Apache community maintainer working on distributed time-series systems, columnar storage, and benchmarking.**

中文版本可以放在英文定位后：

> 开源数据库工程师，参与 Apache IoTDB 与 Apache TsFile 社区治理和开发，关注分布式时序系统、列式存储与基准测试。

这里把角色、技术方向和项目领域放在同一句中；具体项目链接再在后文展开。不要把研究假设、规划中的实验或尚未发布的性能数字写成“已完成贡献”。

## 3. 参考到的成熟 Profile README 模式

这些页面是 GitHub 上的公开一手页面，适合借鉴信息架构，不应照搬其个性化文案。

| 示例 | 页面中可观察到的模式 | 对 SpriCoder 的启发 |
|---|---|---|
| [Addy Osmani](https://github.com/addyosmani) | 一句话说明当前工作方向；列出希望合作/讨论的主题和联系方式；把详细项目放在置顶仓库 | 首屏给出当前角色与合作入口，项目细节交给“精选项目” |
| [Julia Evans](https://github.com/jvns) | 先说明主要项目，再列出博客、社交账号和学习资源；不依赖大量统计卡片 | “主要项目 + 写作/社区入口”比连续堆叠动态图片更易读 |
| [Sindre Sorhus](https://github.com/sindresorhus) | 极简首屏、外部作品入口、置顶仓库承担项目导航 | 保留个人风格，但把最重要的 3–5 个项目交给 GitHub 原生置顶区 |
| [TJ](https://github.com/tj) | README 与 Sponsor/开源项目关系紧密，置顶仓库是主要导航 | 如果未来开放赞助或维护多个工具，可增加单独的支持/协作入口 |

共同模式是：**一句话定位 → 少量可信链接 → 代表性项目 → 外部写作/联系入口**。动态统计并不是这些页面传达身份的必要条件。

## 4. 推荐的信息架构

建议将 README 控制在首屏可读、全文约 100–180 行，使用以下顺序：

### A. Hero：身份与方向

- `# Hongyin Zhang · SpriCoder`
- 一句英文定位 + 一句中文定位。
- 角色徽章或文字：Apache IoTDB PMC Member、Apache TsFile Committer。
- 徽章只链接到 [Apache IoTDB](https://github.com/apache/iotdb) 和 [Apache TsFile](https://github.com/apache/tsfile) 项目页面；按当前要求不加入 Apache 官方名册链接。
- 2–4 个联系/阅读入口：个人博客、GitHub、（如有且愿意公开）邮件或其他社交账号。

### B. What I work on：三条技术主线

用文字和链接代替泛化的技能墙：

1. **Distributed time-series databases** — Apache IoTDB：时序数据采集、存储、查询、分析与分布式系统。
2. **Columnar time-series storage** — Apache TsFile：文件格式、编码压缩、索引、随机访问与多语言接口。
3. **Benchmarking and systems evaluation** — IoT Benchmark 及相关实验/工具：明确区分已发布工具、正在维护的工作和研究中的假设。

IoTDB 官方资料同时强调 IoTDB 与 TsFile 的关系，因此可以在这一区域用一条短句说明“数据库层 ↔ 存储格式层”的关系，而不写未经验证的性能结论。[Apache IoTDB GitHub README](https://github.com/apache/iotdb)

### C. Featured work：精选项目卡片

建议 3–5 个项目，每张卡片只保留：

- 项目名和一手链接；
- 一句“它解决什么问题”；
- 你的角色（PMC、Committer、Maintainer、Contributor，按事实填写）；
- 当前状态（维护中、已发布、研究中；不要把计划写成结果）。

优先顺序可以是：

1. Apache IoTDB
2. Apache TsFile
3. IoT Benchmark
4. 个人维护的高质量工具或教程仓库
5. 有稳定公开产出的研究/写作项目

GitHub 官方建议置顶 3–5 个最相关的仓库，并指出自有项目与参与贡献的开源项目可以组合展示；主页 README 不必重复仓库的安装文档。[GitHub：Using your GitHub profile to enhance your resume](https://docs.github.com/en/account-and-profile/tutorials/using-your-github-profile-to-enhance-your-resume)

### D. Selected contributions：可核验贡献

可以列出 3–6 条稳定链接，例如：

- 已合并的 Apache IoTDB/TsFile PR；
- 参与的 release、设计文档、issue 讨论；
- 已发表的文章、演讲或教程。

每条使用描述性链接文本，例如“TsFile remote random-access design discussion”，不要使用“点击这里”。贡献数字、PR 数量和性能数字只有在来源、时间范围和统计口径同时明确时才适合写入。

### E. Writing and research：写作与研究入口

分成两个状态：

- **Published / maintained**：博客、教程、已发布论文或公开项目文档。
- **Ongoing / exploring**：正在研究的方向、实验记录或待验证假设。

后者要明确标注“研究中/待验证”，避免把计划、目录或草稿当作已验证结果。

### F. Connect：联系与社区

用描述性链接列出博客、邮件、社交账号或 Apache 项目社区入口。GitHub 官方支持个人资料中的社交链接、ORCID 等字段；这些稳定信息可以放在 Profile 设置中，README 只保留最有用的入口。[GitHub：Personalize your profile](https://docs.github.com/en/account-and-profile/tutorials/personalize-your-profile)

## 5. 动态组件的取舍

当前 README 的四类动态图片可以保留一部分，但建议采用“静态内容优先，动态图片可选”的策略。

### GitHub Readme Stats

上游文档明确警告：

- Top Languages 只表示代码统计，不代表语言熟练度；
- 默认只统计自己的非 fork 公有仓库，不包含对他人/组织仓库的贡献；
- 统计受 GitHub API 及仓库数量限制，公共实例可能触发限流。[github-readme-stats](https://github.com/anuraghazra/github-readme-stats)

因此，如果保留，最多保留一张 compact 卡片，并在邻近文字中避免把它解释为“技能排名”。更稳妥的方案是使用上游提供的 GitHub Action 定期生成 SVG 并提交到个人仓库，保留一个可读的静态 fallback；这会增加维护工作，但降低外部服务实时故障对主页的影响。[github-readme-stats：GitHub Action 示例](https://github.com/anuraghazra/github-readme-stats#all-demos)

### Activity Graph

Activity Graph 项目已经说明，Heroku 和 Cyclic 部署不可用，当前 canonical deployment 是 Vercel。[github-readme-activity-graph](https://github.com/Ashutosh00710/github-readme-activity-graph)

如果保留，应：

- 使用当前 canonical Vercel URL；
- 给图片提供有意义的 alt；
- 把它放到页面底部；
- 外部服务失效时，正文仍能完整表达身份和项目。

### Profile Trophy

Profile Trophy 项目拥有公开的自托管/CI 生成选项，但维护者也提示公共服务可能因成本和流量而停止。[github-profile-trophy](https://github.com/ryo-ma/github-profile-trophy)

它更像装饰，不是证明 PMC/Committer 身份的证据。推荐第一阶段移除，或只在静态主体完成后作为可选底部组件。

### Profile Views

访问计数对理解技术方向帮助很小，而且依赖第三方服务。建议删除，除非个人确实需要长期观察该指标；即使保留也不要把它放在首屏。

## 6. 可访问性与 Markdown 规则

GitHub 官方建议检查链接语境、图片 alt、标题层级、易读语言、列表标记和 emoji 使用。[GitHub Blog：5 tips for making your GitHub profile page accessible](https://github.blog/developer-skills/github/5-tips-for-making-your-github-profile-page-accessible/)

具体落实：

- 所有图片写描述性 alt；统计卡片应写“GitHub public activity summary for SpriCoder”，而不是只写“stats”。
- 使用一个 `#` 页面标题，按 `##`、`###` 递进，不跳级。
- 使用真正的 Markdown 列表，不用 emoji 模拟列表符号。
- 链接文本直接说明目的，例如“个人博客”“Apache IoTDB repository”，避免“here”“click here”。
- Emoji 只作少量视觉提示，不把关键信息放在 emoji 中。
- 主题色要同时检查浅色/深色模式的对比度。
- 需要折叠次要内容时，可用 GitHub 支持的 `<details><summary>`；不要把核心身份藏在折叠区。
- 需要深浅色图片时，可使用 GitHub 官方示例支持的 `<picture>` 与 `prefers-color-scheme`。[GitHub Quickstart：Writing on GitHub](https://docs.github.com/en/get-started/writing-on-github/getting-started-with-writing-and-formatting-on-github/quickstart-for-writing-on-github)

## 7. 视觉建议

建议采用 **Apache red + slate + neutral** 的克制配色：

- Apache 红只用于角色徽章、分隔线或小面积强调；
- 正文使用 GitHub 默认文字色，避免大块红色背景；
- 动态卡片统一浅色/深色主题，减少不同服务的视觉噪声；
- 首屏最多一个 banner 或一个头像辅助图，不要同时放 banner、trophy、stats 和 activity graph；
- 通过短段落、表格或项目卡片控制宽度，移动端优先；
- 纯装饰图片不应挤占项目链接和可读文本。

## 8. 建议的首版线框

以下是内容线框，不是最终文案：

```markdown
# Hongyin Zhang · SpriCoder

Open-source database engineer working on distributed time-series systems,
columnar storage, and benchmarking.

Apache IoTDB PMC Member · Apache TsFile Committer

[Apache IoTDB] · [Apache TsFile] · [IoT Benchmark] · [Blog]

## What I work on

- Distributed time-series databases
- Columnar storage formats for time-series data
- Benchmarking, observability, and reproducible systems evaluation

## Featured work

| Project | Role | What it is |
| --- | --- | --- |
| Apache IoTDB | PMC Member | Industrial time-series database |
| Apache TsFile | Committer | Columnar time-series storage format |
| IoT Benchmark | Maintainer | Benchmarking and workload tooling |

## Selected contributions

- [Verified contribution or design discussion]
- [Verified article, talk, or release note]

## Writing and research

- Published / maintained
- Ongoing / exploring (clearly marked as unverified)

## Connect

[Blog] · [GitHub] · [Other public contact]
```

## 9. 分阶段实施

### 第一阶段：稳定主体

- 重写 Hero、技术主线、精选项目、写作与联系区域。
- 保留角色事实和项目一手链接。
- 移除 Trophy、Profile Views；先不引入新的外部动态服务。
- 为现有图片补充描述性 alt，并统一标题层级。

### 第二阶段：核验与展示

- 逐条核验项目、博客、文章和 PR 链接。
- 选择 3–5 个 GitHub 置顶仓库，与 README 的精选项目保持一致。
- 只加入已有公开证据的贡献；研究中的内容标成“进行中/待验证”。

### 第三阶段：可选动态层

- 如确实需要，保留一张 stats 或 activity graph。
- 优先使用 GitHub Action 生成并提交静态 SVG，或自托管服务。
- 设定失效检查：每次 README 改动检查外链 HTTP 状态、图片加载、浅色/深色主题和 alt 文本。

## 10. 验收清单

- 首屏 10 秒内能看到姓名、Apache 角色和技术领域。
- Apache IoTDB、Apache TsFile、IoT Benchmark 和博客均有可点击的一手链接。
- 角色、项目、贡献和研究状态没有混用。
- 任何数字都有统计口径或被删除。
- 所有图片有有效 alt；标题不跳级；链接文本有目的。
- 关闭第三方动态图片后，正文仍然完整。
- GitHub 渲染、移动端、浅色模式和深色模式均可读。
- 只修改 `SpriCoder/README.md` 和本调研文件，不扫描或重写其他文章。

## 来源索引

- [GitHub：About your profile](https://docs.github.com/en/account-and-profile/concepts/personal-profile)
- [GitHub：Managing your profile README](https://docs.github.com/en/account-and-profile/how-tos/profile-customization/managing-your-profile-readme)
- [GitHub：Using your GitHub profile to enhance your resume](https://docs.github.com/en/account-and-profile/tutorials/using-your-github-profile-to-enhance-your-resume)
- [GitHub：Personalize your profile](https://docs.github.com/en/account-and-profile/tutorials/personalize-your-profile)
- [GitHub：Quickstart for writing on GitHub](https://docs.github.com/en/get-started/writing-on-github/getting-started-with-writing-and-formatting-on-github/quickstart-for-writing-on-github)
- [GitHub Blog：5 tips for making your GitHub profile page accessible](https://github.blog/developer-skills/github/5-tips-for-making-your-github-profile-page-accessible/)
- [Apache IoTDB](https://iotdb.apache.org/)
- [Apache IoTDB：About the Community](https://iotdb.apache.org/Community/About-the-Community.html)
- [Apache TsFile](https://tsfile.apache.org/)
- [ASF：PMC Governance](https://www.apache.org/foundation/governance/pmcs.html)
- [apache/iotdb](https://github.com/apache/iotdb)
- [apache/tsfile](https://github.com/apache/tsfile)
- [thulab/iot-benchmark](https://github.com/thulab/iot-benchmark)
- [anuraghazra/github-readme-stats](https://github.com/anuraghazra/github-readme-stats)
- [Ashutosh00710/github-readme-activity-graph](https://github.com/Ashutosh00710/github-readme-activity-graph)
- [ryo-ma/github-profile-trophy](https://github.com/ryo-ma/github-profile-trophy)
- [Addy Osmani profile](https://github.com/addyosmani)
- [Julia Evans profile](https://github.com/jvns)
- [Sindre Sorhus profile](https://github.com/sindresorhus)
- [TJ profile](https://github.com/tj)
