### ISTQB:s testing related vocabulary

1st term: An **anti-pattern** is like a bad habit that seems helpful at first but actually makes things worse. It's similar to always taking a shortcut through a neighborhood that has lots of stop signs - you think it's faster, but it actually takes longer than the main road. In software testing, this might be skipping documentation to "save time" but then causing confusion later when nobody remembers how the tests work.

2nd term:**Bebugging** is deliberately adding mistakes to your software to see if your testing can find them. It's like asking a friend to hide Easter eggs in your yard, and then seeing how many you can find - this helps you estimate how many eggs (or bugs) might still be hidden. For example, a team might intentionally add five calculation errors to their accounting software and then see if their testing process catches all five.

3rd term:**Beta testing** is when real users try your software before it's officially released. It's like a restaurant's "soft opening" where they invite people to dine before the grand opening to get feedback. For instance, when a game company lets selected players try a new game before its official launch to find problems and get suggestions for improvements.

4th term:A **smoke test** quickly checks if the basic functions of software work before doing detailed testing. This is like turning on a new TV just to make sure it powers up and shows a picture before adjusting all the settings and connecting all your devices. For example, checking that a banking app lets you log in and view your balance (the most critical functions) before testing more complex features like setting up automatic payments.

### V-model and testing pyramid

**Understanding the V-Model** helps clarify the relationship between development and testing activities, verification and validation processes, and ensures appropriate test planning at each stage of development.

While the V-Model is typically associated with waterfall methodologies, the **Testing Pyramid** is more common in agile approaches. The Testing Pyramid addresses efficiency by distributing test quantities across levels - numerous unit tests at the base, fewer integration tests in the middle, and minimal UI/system tests at the top.

**SUT (System Under Test)** 是指正在被测试的系统。在软件测试中,SUT 是你要检查和验证的目标软件、应用程序或系统组件。例如,如果你正在测试一个银行应用程序,那么这个银行应用程序就是 SUT。测试人员会对 SUT 执行各种测试用例,以确保它按预期工作并找出可能存在的错误或问题。

### test cases and test case design

**Pair coverage testing** (也称为 pairwise testing 或 all-pairs testing) 是一种测试技术,用于测试具有多个输入参数的系统。它的核心思想是:不需要测试所有参数的所有可能组合,只需要确保任意两个参数的所有可能组合都至少被测试一次。

例如,假设一个登录系统有三个参数:

- 浏览器类型:Chrome、Firefox、Safari(3种选择)
- 操作系统:Windows、Mac、Linux(3种选择)
- 语言:英语、中文、日语(3种选择)

如果要测试所有可能的组合,需要 3 × 3 × 3 = 27 个测试用例。但使用 pair coverage testing,只需要大约 9 个测试用例就可以确保任意两个参数的所有组合都被覆盖到。

**为什么大约只需要 9 个测试用例?**

这是因为 pair coverage testing 使用了数学优化算法来生成最小的测试用例集。让我们用上面的例子来说明:

**参数:**

- 浏览器:Chrome (C)、Firefox (F)、Safari (S)
- 操作系统:Windows (W)、Mac (M)、Linux (L)
- 语言:英语 (E)、中文 (Z)、日语 (J)

**可能的 9 个测试用例示例:**

1. C + W + E
2. C + M + Z
3. C + L + J
4. F + W + Z
5. F + M + J
6. F + L + E
7. S + W + J
8. S + M + E
9. S + L + Z

通过这 9 个测试用例,我们确保了:

- 浏览器和操作系统的所有组合都被测试到(如 C+W、C+M、C+L、F+W 等)
- 浏览器和语言的所有组合都被测试到(如 C+E、C+Z、C+J、F+E 等)
- 操作系统和语言的所有组合都被测试到(如 W+E、W+Z、W+J、M+E 等)

这种方法利用了**正交数组(Orthogonal Arrays)**或类似的组合数学技术,确保用最少的测试用例覆盖所有的两两参数组合。实际需要的测试用例数量可能在 9-12 个之间,具体取决于使用的算法和工具。

**优点:**

- 大幅减少测试用例数量,节省时间和资源
- 研究表明,大多数软件缺陷是由单个参数或两个参数的交互引起的,因此这种方法能发现大部分问题
- 比完全随机测试更系统和全面

**局限性:**

- 无法检测需要三个或更多参数同时交互才会出现的缺陷
- 对于参数间有复杂依赖关系的系统可能不够充分

### equivalent classes

### exploratory testing

### dynamic testing

### risk analysis

### MoSCoW 优先级方法

**MoSCoW** 是一种用于软件开发和项目管理的优先级排序方法,帮助团队决定哪些功能或需求最重要。这个名称来自四个优先级类别的首字母:

- **M - Must have (必须有)**:这些是项目成功的关键需求,没有它们项目就无法交付。例如,一个银行应用必须能够让用户登录和查看账户余额。
- **S - Should have (应该有)**:这些需求很重要,但不是绝对必需的。如果时间不够,可以推迟到下一个版本。例如,银行应用应该有交易历史筛选功能,但没有它也能基本使用。
- **C - Could have (可以有)**:这些是"锦上添花"的功能,有了更好,但优先级最低。例如,自定义主题颜色或个性化界面。
- **W - Won't have (暂不需要)**:这些是团队明确决定在当前版本中不实现的功能,可能会在未来考虑。

**在测试中的应用:**

MoSCoW 方法帮助测试团队确定测试优先级。测试人员应该首先专注于测试 "Must have" 功能,确保核心功能正常工作。然后再测试 "Should have" 和 "Could have" 功能。这样即使时间有限,也能确保最重要的功能得到充分测试。

**优点:**

- 帮助团队在资源有限时做出明智的决策
- 确保关键功能得到优先关注
- 促进团队和利益相关者之间的清晰沟通

**示例场景:**

假设你正在开发一个在线购物网站,使用 MoSCoW 方法可能会这样分类:

- **Must have**:用户注册、登录、浏览商品、添加到购物车、结账支付
- **Should have**:商品评价系统、愿望清单、订单追踪
- **Could have**:商品推荐、社交媒体分享、虚拟试穿
- **Won't have** (本版本):虚拟助手聊天功能、AR 产品预览

### four metres

1. **Amount of passing test cases**
    - **Useful info**: Shows how much of the system coders have tested and how stable it is.
    - **Bad behaviour**: Testers might write super easy tests just to get more passes.
2. **Defect fixing time**
    - **Useful info**: Shows how quickly coders fix bugs and how good they are at it.
    - **Bad behaviour**: Coders might rush fixes without proper testing, or testers might only report "easy-to-fix" bugs.
3. **Requirements coverage**
    - **Useful info**: Shows how much of what the customer wanted is actually tested.
    - **Bad behaviour**: Coders may only focus on things they can measure, ignoring stuff like "is it easy to use?" or "is it fast enough?"
4. **Test case efficiency**
    - **Useful info**: Tells if testers are writing tests that actually catch real problems.
    - **Bad behaviour**: Testers may skip old tests (that rarely find new bugs) and just write tests they know will find bugs to keep their numbers looking good.

### Test automation jeopardy

在测试自动化的背景下,**jeopardy**(危险、风险)指的是测试自动化可能带来的负面影响或风险。

虽然测试自动化有很多好处,但如果使用不当,也可能会带来一些问题,比如:

- 维护自动化测试脚本需要额外的时间和成本
- 过度依赖自动化可能会忽略探索性测试
- 自动化测试可能产生误报(false positives),浪费调查时间
- 初期投入大,如果项目变化频繁,自动化测试可能需要经常更新

因此在决定是否使用测试自动化时,需要权衡其带来的好处和潜在的风险。

不会改变被测软件时序或其他特性（timing/characteristics）的测试，通常更适合做自动化。

例子：API 回归、确定性的业务规则校验、数据库约束检查、接口返回码/字段校验。

结果更容易由人判断（比如视觉效果、可用性体验），或者很少运行的测试，通常更适合人工测试（自动化性价比低）。

例子：UI 外观是否“看起来对”、文案是否自然、交互是否顺畅、探索性测试、一次性验证。

### test automation tool

**Postman** is a tool for testing APIs. It helps automate **integration and system-level** testing of RESTful APIs by allowing HTTP requests to be sent and responses to be checked. API tests can be grouped together and run sequentially, which is ideal for verifying that backend services return the correct data and response codes.

Postman offers several ways to automate testing. With **record and play**, API requests can be manually recorded and replayed later. For more advanced testing, JavaScript test **scripts** can be written to check specific conditions. Postman also supports **data-driven** testing through the Collection Runner, which allows the same tests to be run with different sets of data to test various scenarios and edge cases.

### artificial intelligence in testing terms or abbreviations

- **False positive** is incorrect reporting: the code works well, but the test reports a bug.
- **Fitness function** is a measurement: it evaluates the test case performance by giving a numeric score. It can measure anything relevant like coverages, execution time, etc.
- **TCS (Test Case Selection)**: Selecting a subset of tests that finds the same or nearly the same number of errors as the entire test set.
- **TCP (Test Case Prioritization)**: Order test cases by likelihood of finding errors, so the most valuable tests are run first. The method does not reduce the number of tests, but running of tests can be interrupted, and still get reasonably good results.

**Broken authentication** means the system that checks your identity—like login pages, passwords, and “stay logged in” features—does not protect you properly. When these parts of a system are weak, attackers may be able to log in as someone else without knowing their password. This can happen if the system allows very simple passwords, doesn’t block repeated wrong attempts, has insecure password reset links, or lets old login sessions stay active for too long. In other words, the “lock on the door” exists, but it doesn’t actually keep the wrong people out. Because of these weaknesses, attackers might access personal accounts, read private information, or even take over someone’s profile completely. 

To check if a system might suffer from broken authentication, We can try things like using an extremely weak password, seeing whether the account locks after many failed attempts, checking if logout actually ends the session, or observing whether password reset links expire quickly. If these protections don’t work properly, the system may be vulnerable to attackers pretending to be legitimate users.

---

---

### 1. Definitions

**a) Acceptance testing**

Acceptance testing is a formal testing phase conducted to determine whether a system satisfies its acceptance criteria and to enable the customer or stakeholders to determine whether to accept the system. It is typically performed by end users or clients to validate that the software meets business requirements before deployment.

**b) Big Bang integration**

Big Bang integration is an integration testing approach where all components or modules are combined together at once and then tested as a whole. This method does not involve incremental integration and is typically used for small systems, though it makes defect localization difficult.

**c) Fuzz testing**

Fuzz testing (fuzzing) is a software testing technique that involves providing invalid, unexpected, or random data as inputs to a program to discover vulnerabilities, crashes, or bugs. It is particularly effective at finding security vulnerabilities and robustness issues.

**d) Glass box testing (white box testing)**

Glass box testing is a testing approach where the tester has full knowledge of the internal structure, design, and implementation of the system being tested. Test cases are designed based on code structure, logic paths, and internal workings to achieve structural coverage criteria.

**e) Negative testing**

Negative testing is a testing approach that focuses on verifying that the system handles invalid inputs, error conditions, and unexpected user behavior gracefully. It ensures the software does not crash or behave incorrectly when given invalid or unexpected data.

**f) Sowing/planting errors**

Sowing or planting errors is a technique where known defects are intentionally inserted into the software to evaluate the effectiveness of the testing process. The ratio of found planted errors to total planted errors can be used to estimate the number of real defects remaining in the system.

### 2. Coverage meters

**a) Statement coverage (1.5p)**

Statement coverage measures the percentage of executable statements that have been executed by the test suite. For 100% statement coverage, every line of code must be executed at least once.

**Minimum test case set:**

- Test 1: a=1, b=0, c=-1 (det=4, both sides of OR evaluated, r1=2, r2=-2, returns true)

**b) Decision/branch coverage (1.5p)**

Decision coverage measures the percentage of decision outcomes (true/false) that have been tested. Each if-statement must evaluate to both true and false.

**Minimum test case set:**

- Test 1: a=1, b=0, c=-1 (det=4 ≥ 0 and a≠0, returns true)
- Test 2: a=1, b=0, c=1 (det=-4 < 0, returns false)
- Test 3: a=0, b=1, c=1 (a==0, returns false)

**c) Condition coverage (1.5p)**

Condition coverage requires each boolean sub-expression (condition) to evaluate to both true and false independently.

**Minimum test case set:**

- Test 1: a=1, b=0, c=-1 (det=4 > 0 [T], a≠0 [T], returns true)
- Test 2: a=1, b=0, c=1 (det=-4 < 0 **[F]**, a≠0 [T], returns false)
- Test 3: a=0, b=1, c=1 (det=0 [F], a==0 **[F]**, returns false)

**d) Multiple condition coverage (1.5p)**

Multiple condition coverage (MCC) requires testing all possible combinations of boolean conditions in each decision.

**Minimum test case set:**

- Test 1: det < 0 [T], a == 0 [T] → a=0, b=1, c=1 (det=0 fails first, need det<0)
- Test 2: det < 0 [T], a == 0 [F] → a=1, b=0, c=1 (det=-4, a=1, returns false)
- Test 3: det < 0 [F], a == 0 [T] → a=0, b=0, c=0 (det=0, a=0, returns false)
- Test 4: det < 0 [F], a == 0 [F] → a=1, b=0, c=-1 (det=4, a=1, returns true)

---

### Regression testing（回归测试）

- **是什么**：在代码修改（修 bug、加功能、重构、升级依赖）之后，再跑一遍已有测试，确认**原来正常的功能没有被改坏**。
- **目的**：防止“改 A 坏 B”的副作用。
- **例子**：购物网站修复优惠券 bug 后，再测下单、支付、发票、库存扣减等原本功能。
- **常见对比**：回归测试不一定是“重新测试全部”，通常会做**回归测试集选择**（只跑最关键、最容易受影响的部分）。

### Reliability testing（可靠性测试）

- **是什么**：评估系统在规定条件下、规定时间内**稳定运行、不出故障**的能力。
- **关注点**：崩溃率、错误率、长时间运行是否内存泄漏、服务是否能持续提供功能。
- **例子**：让服务器连续运行 72 小时压测，看是否出现崩溃或资源耗尽。
- **常见对比**：
    - **性能测试**更关注“快不快”，
    - **可靠性测试**更关注“稳不稳、久不久”。

### Requirement coverage（需求覆盖率 / 需求覆盖）

- **是什么**：衡量测试是否覆盖了需求。通常是“需求 ↔ 测试用例”的可追踪关系。
- **怎么用**：把每条需求（或用户故事、验收标准）映射到至少一个测试用例，统计覆盖情况。
- **目的**：避免只测“开发顺手测到的地方”，而漏掉客户真正关心的要求。
- **注意**：需求覆盖高 ≠ 缺陷少。它只说明“测到了”，不保证“测得好”。

### Unit testing（单元测试）

- **是什么**：对最小可测试单元（函数、方法、类）进行测试，通常由开发人员写，跑得快，隔离依赖（mock/stub）。
- **目的**：尽早发现逻辑错误，定位快。
- **例子**：测试 `calculateTotal(cart)` 在不同购物车输入下返回值是否正确。
- **特点**：粒度小、数量多、执行快。

### Integration testing（集成测试）

- **是什么**：测试多个组件组合在一起时，它们的**接口与交互**是否正确。
- **目的**：发现模块间契约（API/数据格式/调用顺序/错误处理）的问题。
- **例子**：订单服务调用库存服务、支付服务，测试在库存不足或支付失败时的整体行为。
- **常见对比**：单元测试不一定会暴露“模块之间连起来后”的问题。

### System integration（系统集成 / 系统集成测试，常见写法是 SIT）

- **是什么**：把“系统”与**外部系统/子系统**集成起来测试（例如第三方支付、身份认证、硬件设备、外部数据库、消息队列等）。
    - Integration testing 更偏“内部模块之间集成”，
    - System integration 更偏“系统与系统之间集成”（范围更大、环境更像真实）。
- **目的**：验证跨系统的端到端流程、协议、网络、权限、环境配置等。
- **例子**：你的系统与银行支付网关、物流接口、学校 SSO 登录集成后的全链路测试。

### Acceptance testing（验收测试）

- **是什么**：由客户、业务代表或最终用户（或代表）进行，判断系统是否满足**验收标准/业务目标**，决定是否接受交付。
- **目的**：验证“做的是不是客户要的”（偏验证/确认业务价值）。
- **例子**：客户按验收清单操作：注册、下单、退款、权限管理等都符合合同/需求。
- **常见类型**：UAT（用户验收测试）常被视为 acceptance testing 的一种实践形式。

### Confusion matrix（混淆矩阵：TP / FP / TN / FN）

用于**二分类**（或推广到多分类）的预测/判定结果统计表。先定义：

- **Positive / Negative**：例如“有缺陷”为正类，“无缺陷”为负类。
- **TP（True Positive）真阳性**：实际是正类，你也判成正类（判对了）。
- **FP（False Positive）假阳性**：实际是负类，你却判成正类（误报）。
- **TN（True Negative）真阴性**：实际是负类，你也判成负类（判对了）。
- **FN（False Negative）假阴性**：实际是正类，你却判成负类（漏报）。

在测试语境里：

- **FP**：系统其实没问题，你报了 bug（误报）。
- **FN**：系统有问题，你没测出来（漏报，通常更危险）。

### Compute metrics（由混淆矩阵计算指标：accuracy、precision、recall 等）

常用指标（以二分类为例）：

- **Accuracy（准确率）**：整体判对的比例
    - 公式：$(TP + TN) / (TP + FP + TN + FN)$
    - 适用：类别分布比较均衡时更有意义。
    - 陷阱：严重类别不平衡时会“看起来很高但没用”。
- **Precision（精确率 / 查准率）**：你判为正的里面，有多少是真的正
    - 公式：$TP / (TP + FP)$
    - 高 precision 表示：**误报少**。
- **Recall（召回率 / 查全率 / TPR）**：实际为正的里面，你找回了多少
    - 公式：$TP / (TP + FN)$
    - 高 recall 表示：**漏报少**。
- **F1-score**：precision 和 recall 的折中（调和平均）**（harmonic mean）**
    - 公式：$2PR/(P+R)$
    - 用于需要平衡误报和漏报的场景。
        - 如果 **P=1, R=0**：(F1 = 0)（一个为 0，整体就 0）
        - 如果 **P=0.9, R=0.1**：(F1 approx 0.18)（差的那个会强烈拖后腿）
        - 如果 **P=0.5, R=0.5**：(F1=0.5)
        
        所以它强调的是**平衡**，适合“误报（FP）和漏报（FN）都很重要”的场景。
