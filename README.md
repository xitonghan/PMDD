<!--
  仓库地址：https://github.com/xitonghan/PMDD （已按实际地址填入，无需再替换）

  待办：
  1. 截图 —— 把图片放进 docs/screenshots/ 后，取消「界面预览」一节的注释
  2. 二维码 —— 把分享海报生成的二维码存为 docs/qrcode.png 后，取消对应注释
  3. 内测分发链接 —— 补进「下载与安装 · 方式三」（百度网盘 / 公众号）
  4. LICENSE 文件 —— 还没建，README 里指向它的链接现在是 404
  5. 若改用 MIT 以外的许可证，同步改「许可证」一节
-->

# PMDD 情绪日记 · PMDD Mood Diary

[![Platform](https://img.shields.io/badge/Android-8.0%2B-3DDC84?logo=android&logoColor=white)](https://developer.android.com)
[![Kotlin](https://img.shields.io/badge/Kotlin-1.9.24-7F52FF?logo=kotlin&logoColor=white)](https://kotlinlang.org)
[![Jetpack Compose](https://img.shields.io/badge/Jetpack%20Compose-Material%203-4285F4?logo=jetpackcompose&logoColor=white)](https://developer.android.com/jetpack/compose)
[![Permissions](https://img.shields.io/badge/system%20permissions-none-2ea44f)](#隐私承诺)
[![License](https://img.shields.io/badge/license-MIT-blue)](LICENSE)

**完全离线、不申请任何系统权限、不上传任何数据的 PMDD（经前期烦躁障碍）情绪与周期记录应用。**

面向真实需要的女性用户而写的公益项目，免费使用，无广告、无内购、无账号。

> An offline-first Android diary for tracking PMDD symptoms and menstrual cycles.
> No network permission, no data collection, no ads. Free for public good.

[![下载最新版 APK](https://img.shields.io/badge/%E4%B8%8B%E8%BD%BD%E6%9C%80%E6%96%B0%E7%89%88%20APK-e8462f?style=for-the-badge&logo=android&logoColor=white)](https://github.com/xitonghan/PMDD/releases/latest)

[中文说明](#中文说明) ｜ [English](#english)

---
---

## 中文说明

### 这是什么

PMDD（Premenstrual Dysphoric Disorder，经前期烦躁障碍）不是"脾气不好"，而是一种在经前期反复出现、明显影响生活与关系的症状群。它的麻烦之处在于：**症状随周期起伏，靠记忆很难说清**，而就医时医生最需要的恰恰是连续的记录。

这个 App 只做一件事：**让记录变得足够简单，并且让数据只留在你自己手机里。**

| 项目 | 说明 |
| --- | --- |
| 应用名 | PMDD 情绪日记 |
| 包名 | `com.pmdd.record` |
| 系统要求 | Android 8.0（API 26）及以上 |
| 当前版本 | v0.3.0 |
| 费用 | 免费，公益项目 |
| 上架情况 | 不上架应用商店，APK 直装分发 |

### 下载与安装

**方式一**：点击上方红色按钮，下载最新版 APK。

**方式二**：手机扫码下载（二维码待补充）。

```
https://github.com/xitonghan/PMDD/releases/latest/download/PMDD.apk
```

> 这个链接**永久有效**，每次发新版都指向最新那一版，不用换二维码。

**方式三（国内推荐）**：百度网盘卡片 / 公众号文章 —— 链接待补充。

安装时安卓会提示"未知来源应用"，允许一次即可。

> ⚠️ **升级时请直接覆盖安装，不要先卸载旧版。**
> 安卓在卸载 App 时会连数据目录一起删掉，这是系统规定动作，任何 App 都救不回来。
> 覆盖安装则不会丢数据。如果已经卸载了，可以用 App 内的「从备份恢复」找回自动备份。

<!-- 界面预览：把截图放进 docs/screenshots/ 后取消注释
### 界面预览

| 日历 | 每日打卡 | 图表 |
| --- | --- | --- |
| ![日历](docs/screenshots/calendar.png) | ![打卡](docs/screenshots/entry.png) | ![图表](docs/screenshots/charts.png) |

| 自查评估 | 就医报告 | 分享海报 |
| --- | --- | --- |
| ![自查](docs/screenshots/assessment.png) | ![报告](docs/screenshots/report.png) | ![分享](docs/screenshots/share.png) |
-->

### 隐私承诺

这是本项目最认真对待的一件事，也是可以**被验证**的：

- **未申请任何系统权限** —— 没有 `INTERNET`、没有存储、没有定位、没有通讯录。你可以自己核对：

  ```bash
  aapt dump permissions app-release.apk
  ```

- **没有服务器** —— 数据存在本机 Room 数据库里，密码用随机盐 + SHA-256 哈希保存，不落明文。
- **没有埋点、没有广告、没有账号体系** —— 不需要手机号、不需要微信授权。
- **报告导出与分享海报都在本机生成**，图片存相册走系统 MediaStore，全程不联网。

备份文件是你主动导出到**自己的文件夹**里的，去向你完全可控。

### 主要功能

**记录**

- 日历视图，点任意日期即可标注**经期开始 / 结束**（参考大姨妈、美柚的手动标注方式）
- 经期粉色实心圆，黄体期黄色小圆点（系统自动推算），设计上尽量不引入误读压力
- 每日打卡：情绪打分、标签、日记、症状、睡眠、多条用药记录

**观察**

- 最近 30 天情绪曲线（自绘 Canvas，带经期/黄体期底色带）
- 睡眠趋势、症状频次排行
- 以 **2 个月（60 天）为一个评估周期**，本周期与上一周期对比

**就医**

- 一键导出 **PDF 报告**（曲线图 + 每日明细），面诊时可直接给医生看
- 内置 **PMDD 自查评估问卷**（参照 DSM-5），给出低 / 中 / 高风险判定，并逐条说明哪几条满足、哪几条没满足

**数据安全**

- 覆盖安装不丢数据（正式 Room 迁移脚本）
- 自动备份到自选文件夹，卸载重装也能恢复
- 手动导出/导入本地备份

### 常见问题

**Q：为什么微信里点下载链接打不开？**
微信会拦截外部 APK 下载。请用手机浏览器打开链接，或从网盘卡片下载。App 内的「分享」页会生成一张**图片海报**，图片在微信里传播不受限制，可以放心转发到群里。

**Q：升级会不会把我的记录清空？**
不会，只要**覆盖安装**。如果先卸载，数据会随卸载一起消失——这是安卓的机制，不是 App 的问题。

**Q：换了手机怎么办？**
在设置里选一个文件夹作为自动备份位置（授权一次）。之后所有改动都会静默备份进去。新手机装好后重新选同一个文件夹，用「从备份恢复」即可。

**Q：忘记密码了，数据会丢吗？**
不会。用密保问题答对后可以重设密码，记录全部保留。

**Q：自查结果说我高风险，是我确诊了吗？**
不是。自查问卷**不是诊断工具**，它只是提醒你"值得找专业医生聊一聊"。任何判断请以医生面诊为准。

**Q：会上架应用商店吗？**
目前不会，只做 APK 直装 + 微信群 / 公众号分发，因此也不需要隐私政策页与备案。

### 开发者与反馈

**软件开发志愿者：韩析同**
微信：`BD7JQD` ｜ 邮箱：`xitonghan@139.com`

这是一个公益项目，欢迎反馈 bug、建议，或者帮忙把界面文案改得更温柔一些。如果这个工具对你有帮助，也欢迎转给可能需要的姐妹。

### 免责声明

本 App 仅用于情绪与身体状态的记录与自我观察，**不提供医疗诊断**。自查评估结果不具备诊断效力。如有持续困扰，请及时就诊。

---

### 技术栈

| 项目 | 版本 |
| --- | --- |
| 语言 | Kotlin 1.9.24 |
| UI | Jetpack Compose（Material 3）+ Navigation Compose |
| 数据库 | Room 2.6.1 + KSP |
| 图表 | 自绘 Canvas（不依赖第三方图表库） |
| PDF | 原生 `PdfDocument` + 系统 CJK 字体探测 |
| 二维码 | zxing core |
| 构建 | Gradle 8.14.1 / AGP 8.13.2 |
| SDK | compileSdk 37 / minSdk 26 / targetSdk 34 |

### 环境要求（重要）

| 项目 | 要求 |
| --- | --- |
| Android Studio | 任意近期版本 |
| **Gradle JDK** | **JDK 17 ~ 24**（**不能用 JDK 25**） |
| Android SDK Platform | compileSdk 37 |
| Build Tools | 36.0.0 |

> ⚠️ **最容易踩的坑：Gradle JDK 不能用 JDK 25。**
> Android Studio 自带的 JBR 是 JDK 25，而 Gradle 8.14.1 的 Groovy 无法解析 JDK 25 的字节码，会直接报
> `BUG! exception in phase 'semantic analysis' ... Unsupported class file major version 69`。
>
> 解决办法：在 `Settings > Build, Execution, Deployment > Build Tools > Gradle > Gradle JDK` 里选 JDK 21。

### 命令行构建

```bash
export JAVA_HOME="/path/to/jdk21"
./gradlew assembleDebug        # 产出 APK
./gradlew testDebugUnitTest    # 周期推算 + 问卷判定 单元测试（39 条）
```

产物路径：`app/build/outputs/apk/debug/app-debug.apk`

> 如果 `services.gradle.org` 下载超时，可改用镜像
> `https://mirrors.cloud.tencent.com/gradle/` 手动铺进 wrapper 缓存目录。

### 项目结构

```
app/src/main/java/com/pmdd/record/
├── PmddApplication.kt          应用入口，初始化数据库与密码管理器
├── MainActivity.kt             唯一 Activity，承载 Compose 界面
├── AppInfo.kt                  版本号读取（统一走 PackageManager）
├── data/                       ★ 数据层
│   ├── Entities.kt             Room 实体：DailyRecord / CycleSetting / PeriodRecord / TagItem / Assessment
│   ├── Daos.kt                 五个 DAO
│   ├── AppDatabase.kt          数据库单例（version 3）+ 正式迁移脚本
│   ├── AppRepository.kt        数据仓库（写操作后触发自动备份）
│   └── Medication.kt           用药记录与标签的编解码
├── domain/                     ★ 业务层
│   ├── CycleCalculator.kt      周期阶段推算（经期读手动记录，黄体期自动推算）
│   ├── PeriodEditor.kt         经期区间手动编辑（标开始/结束/取消 + 合并）
│   ├── Questionnaire.kt        自查问卷定义与风险判定（纯数据，有单元测试）
│   └── Stats.kt                统计聚合
├── security/                   ★ 安全与备份
│   ├── LockManager.kt          本机密码 + 密保问题（盐 + SHA-256）
│   ├── AutoBackup.kt           SAF 文件夹自动备份（写后读回校验）
│   └── DataBackup.kt           备份 JSON 的导出与解析
├── share/AppShare.kt           下载二维码 + 分享海报生成
├── pdf/ReportExporter.kt       就医报告 PDF 生成（含中文字体探测）
└── ui/                         AppRoot.kt / theme / components / screen（十个页面）

tools/IconTool.java             图标生成工具：从设计稿裁图并输出各密度资源
```

### 周期标注规则

参考大姨妈 / 美柚的做法，**经期由用户手动标注，系统只推算黄体期**：

| 标记 | 由谁决定 | 视觉 |
| --- | --- | --- |
| **经期** | **用户手动标注开始日与结束日** | 粉色实心圆 |
| **黄体期** | 系统自动推算：下一次经期开始前 14 天 | 黄色小圆点 |
| 普通日 | — | 留白（仅数字） |
| 已打卡 | 当天有任意记录 | 浅豆沙底色 |

**操作方式**：日历里点任意日期 → 弹出操作面板 →「这天是经期开始」/「这天是经期结束」/「取消这天的经期标记」/「记录这天的状态」。

推算细节见 `domain/CycleCalculator.kt`：周期长度优先取两次真实经期开始日的间隔，没有下一条记录时用设置里的平均周期（默认 28，可调 21~40）；距上一次经期超过一个周期长度时不做猜测。

### 自查评估问卷

底部导航**正中间**的「自查」Tab。

| 部分 | 题号 | 说明 |
| --- | --- | --- |
| 第一部分 基础背景信息 | 1~13 | 必答；**不计入筛查分数**，仅用于统计调研 |
| 第二部分 PMDD 核心症状自评 | 14~24 | 11 项，0~3 分（参照 DSM-5） |
| 第三部分 症状周期与社会功能 | 25~27 | 单选 |

**判定规则**（`domain/Questionnaire.kt`）—— 同时满足以下 5 条 → **PMDD 高风险**；满足 2 条及以上 → **存在经前期不适**；否则 → **未达风险标准**：

1. 第 14~17 题（核心情绪症状）至少 1 项 ≥ 2 分
2. 第 14~24 题合计 5 项及以上 ≥ 2 分
3. 第 25 题 = B（与月经周期高度相关）
4. 第 26 题 = B（近 1 年连续 2 个以上周期反复出现）
5. 第 27 题 ≥ B（已经明显干扰到生活）

结果页会**逐条列出哪几条满足、哪几条没满足**，并列出达到中度及以上的症状名称，便于面诊时直接给医生看。提交前必须勾选同意隐私声明。最近 10 次评估可回看对比，也会一并写进备份文件。

### 数据不丢的三道保险

1. **覆盖安装不丢** —— 未使用 `fallbackToDestructiveMigration()`，而是正式 Room 迁移脚本（1→2 新增经期表并去掉 `lastPeriodStart` 列；2→3 新增评估表）。建表语句与 Room 生成的语句逐字比对一致，改实体字段后必须同步更新迁移脚本。
2. **卸载重装能救回来** —— 设置里选一个自己的文件夹作为备份位置（走 SAF，授权一次），之后每次修改记录都会**自动静默**写一份 `PMDD情绪日记_自动备份.json`；重装后重新选同一个文件夹，用「从备份恢复」即可。写盘后会**读回校验**，防止文件提供方不截断导致 JSON 损坏。
3. **手动兜底** —— 「导出本地备份」仍然保留。

### 分享与二维码

**为什么是图片而不是链接**：微信内点击链接无法下载 APK（会被拦截），但**图片在微信里传播不受限制**。所以「我的 → 分享给姐妹」会生成一张海报图片（图标 + 名称 + 功能点 + 二维码 + 扫码引导），可直接发到微信群 / 朋友圈。

海报与二维码都在本机生成，保存到相册走 MediaStore（Android 10+ 免权限），**全程不申请任何存储权限、不联网**。

### 功能实现清单

| 需求条目 | 状态 |
| --- | --- |
| 启动页（自动跳转 + 免责提示） | ✅ |
| 首次打开免责声明弹窗（勾选同意才进入） | ✅ |
| 解锁页（4 位数字密码，随机盐 + SHA-256） | ✅ |
| 忘记密码 → 密保问题重设，数据保留 | ✅ |
| 首页日历：经期粉色实心圆（手动标注） | ✅ |
| 首页日历：黄体期黄色小圆点（自动推算） | ✅ |
| 日历点击日期 → 标注经期开始 / 结束 / 取消 | ✅ |
| 每日打卡：情绪打分 / 标签 / 日记 / 症状 / 睡眠 / 用药 | ✅ |
| 数据图表：最近 30 天情绪曲线 | ✅ |
| 数据图表：睡眠趋势 + 症状频次统计 | ✅ |
| 数据图表：2 个月评估周期对比 | ✅ |
| 报告导出：生成 PDF（含曲线图与每日明细） | ✅ |
| 自查评估问卷 + 风险判定 + 历史记录 | ✅ |
| 数据不丢：Room 迁移 + 自动备份 + 手动备份 | ✅ |
| 分享海报 + 下载二维码 | ✅ |
| 开发者署名（关于项目页） | ✅ |
| 桌面图标（设计稿图形，工具见 `tools/IconTool.java`） | ✅ |
| 我的：周期设置 / 改密码 / 清除数据 | ✅ |
| UI 规范（豆沙红 + 驼色 + 浅米底、大字号） | ✅ |
| 全程无广告、无内购、不采集上传 | ✅ |
| PMDD 科普静态页 | ⚠️ 文案待项目方提供 |
| 手势密码 | ❌ 已确认首期只做 4 位数字 |
| 本地打卡提醒（通知） | ❌ 待确认 |
| 云备份 / 后端 | ❌ 需求明确首期不做 |

### 已知限制与待验证项

1. **尚未在真机 / 模拟器上运行验证。** 开发机无 AVD、无系统镜像，仅验证到「编译通过 + 产出 APK + 39 条单元测试全绿」。
2. **PDF 中文渲染未在真机验证。** 代码按优先级探测系统 CJK 字体；若目标机型都取不到，需把中文字体打包进 `assets/`，APK 体积会增加 3~5MB。
3. **迁移脚本未经真机跨版本升级验证。** 建表语句已与 Room 生成结果逐字核对一致，但「就地升级保留数据」这条路径建议用旧版在真机上实测一次。
4. **密码锁允许「暂不设置」**，仅便于试用，正式版建议强制设置。
5. **科普页为占位文案**，正式内容需项目方提供并经审核。
6. **release 签名**需项目方生成（建议由发起人保管，志愿者不持有）。

### 维护者须知

**每次发版前必须改的一处**：`app/src/main/java/com/pmdd/record/share/AppShare.kt` 里的 `DOWNLOAD_URL` 常量 —— 它是 App 内分享海报上二维码的内容。

```kotlin
const val DOWNLOAD_URL = "https://github.com/xitonghan/PMDD/releases/latest"
```

建议直接指向本仓库的 Release 页（或 `.../releases/latest/download/PMDD.apk` 直链），这样**一次设置长期有效**，以后发新版不用改代码、不用重印二维码。当前代码里是占位地址，App 内会检测到并给出醒目提示，不会漏改。

发布流程：改 `versionCode` / `versionName` → 构建 APK → 在 GitHub 新建 Release（tag 沿用 `PMDD_V0.3.0` 这种格式）→ **把 APK 附件命名为固定的纯 ASCII 名 `PMDD.apk`**（**不要**带版本号，否则 `latest/download/` 直链会失效）→ 勾选 *Set as the latest release*。

**重新生成下载二维码**（换了链接、或需要印刷版时）：工具在 `tools/QrTool.java`，只用 zxing core + JDK 自带 java.awt，输出前会自动回读解码校验。

```bash
cd PMDDApp/tools
mkdir -p _qrbuild
cp ~/.gradle/caches/modules-2/files-2.1/com.google.zxing/core/3.5.3/*/core-3.5.3.jar _qrbuild/zxing-core.jar
"C:/buildtools/jdk21/bin/javac.exe" -encoding UTF-8 -cp "_qrbuild/zxing-core.jar" -d _qrbuild QrTool.java
"C:/buildtools/jdk21/bin/java.exe" -cp "_qrbuild;_qrbuild/zxing-core.jar" QrTool ../output
```

产出三个文件：

| 文件 | 内容 | 适用场景 |
| --- | --- | --- |
| `二维码_APK直链.png` | `.../releases/latest/download/PMDD.apk` | 系统相机扫码直接下载、印刷、非微信渠道 |
| `二维码_Release页面.png` | `.../releases/latest` | 微信里打开（能看到版本与更新说明） |
| `分享卡_扫码下载.png` | 1080×1350 海报，内嵌直链二维码 | 发微信群 / 朋友圈 |

### 许可证

本项目以 **MIT 许可证**开源，详见 [LICENSE](LICENSE)。

---
---

<a id="english"></a>

## English

### About

PMDD (Premenstrual Dysphoric Disorder) is not "just moodiness" — it is a cluster of symptoms that recurs before menstruation and can seriously affect daily life and relationships. The hard part is that **symptoms rise and fall with the cycle**, making them nearly impossible to describe from memory. What a doctor needs is a continuous record.

This app does one thing: **makes that record effortless, and keeps the data on your own phone.**

- App name: PMDD Mood Diary（PMDD 情绪日记）
- Package: `com.pmdd.record`
- Requires: Android 8.0 (API 26) or above
- Version: v0.3.0
- Price: free, non-profit project
- Distribution: direct APK install (not on any app store)

### Download & install

[Download the latest APK](https://github.com/xitonghan/PMDD/releases/latest)

Direct link (permanent — always points to the newest release):

```
https://github.com/xitonghan/PMDD/releases/latest/download/PMDD.apk
```

Android will ask you to allow installation from an unknown source; grant it once.

> ⚠️ **When updating, install directly over the existing version — do not uninstall first.**
> Android deletes the app's data directory on uninstall; no app can prevent that. Installing over the top preserves everything. If you already uninstalled, use "Restore from backup" inside the app.

### Privacy

This is the part we take most seriously, and it is **verifiable**:

- **No system permissions at all** — no `INTERNET`, no storage, no location, no contacts. Check it yourself:
  ```bash
  aapt dump permissions app-release.apk
  ```
- **No server.** Data lives in a local Room database; the passcode is stored as a salted SHA-256 hash, never in plain text.
- **No analytics, no ads, no accounts** — no phone number, no login, no WeChat authorization.
- **PDF reports and share posters are generated on-device.** Saving to your gallery uses MediaStore (no permission needed on Android 10+). Nothing ever leaves the phone.

Backups are written to a folder **you** choose, so you stay in full control.

### Features

**Record**

- Calendar view — tap any date to mark the **start or end of a period** (manual marking, like most period trackers)
- Period days shown as filled pink dots; luteal phase as small yellow dots (auto-estimated)
- Daily check-in: mood score, tags, journal, symptoms, sleep, multiple medication entries

**Understand**

- 30-day mood curve (custom Canvas rendering, with period / luteal shading)
- Sleep trend and symptom frequency ranking
- **Two-month (60-day) assessment cycles**, comparing the current cycle with the previous one

**Share with a doctor**

- One-tap **PDF report** (curves + daily details) you can hand straight to a clinician
- Built-in **PMDD self-assessment questionnaire** (based on DSM-5) producing a low / medium / high risk result, with a line-by-line explanation of which criteria were met

**Keep your data**

- Updates never erase data (proper Room migrations)
- Automatic backup to a folder of your choice — survives uninstall and reinstall
- Manual export / import as a fallback

### FAQ

**Why can't I open the download link inside WeChat?**
WeChat blocks external APK downloads. Open the link in your phone browser, or download from the cloud-drive card. The in-app "Share" page generates an **image poster** instead — images travel freely in WeChat, so you can forward it to a group chat.

**Will updating wipe my records?**
No, as long as you **install over the existing version**. If you uninstall first, the data goes with it — that is Android's behaviour, not a bug in the app.

**I changed phones. What now?**
Pick a folder in Settings as your auto-backup location (one-time authorization). Everything is then backed up silently. On the new phone, choose the same folder and use "Restore from backup".

**I forgot my passcode — do I lose my data?**
No. Answer your security question and you can set a new passcode; all records are kept.

**The self-check says I'm high risk. Am I diagnosed?**
No. The questionnaire is **not a diagnostic tool** — it is only a prompt that it may be worth talking to a doctor. Any diagnosis must come from a clinician.

### Credits

**Volunteer developer: 韩析同 (Han Xitong)**
WeChat: `BD7JQD` · Email: `xitonghan@139.com`

This is a non-profit project. Bug reports, suggestions, and warmer wording for the UI are all welcome. If it helps you, please pass it on to someone who might need it.

### Disclaimer

This app is intended only for tracking and self-observation of mood and physical state. It does **not** provide medical diagnosis, and the self-assessment result carries no diagnostic weight. If symptoms persist, please see a doctor.

### Tech stack

| Item | Version |
| --- | --- |
| Language | Kotlin 1.9.24 |
| UI | Jetpack Compose (Material 3) + Navigation Compose |
| Database | Room 2.6.1 + KSP |
| Charts | Custom Canvas rendering (no third-party chart library) |
| PDF | Native `PdfDocument` + system CJK font detection |
| QR code | zxing core |
| Build | Gradle 8.14.1 / AGP 8.13.2 |
| SDK | compileSdk 37 / minSdk 26 / targetSdk 34 |

### Building

Requires **JDK 17–24**. JDK 25 will fail with `Unsupported class file major version 69` (Gradle 8.14.1 cannot parse JDK 25 bytecode). Point the Gradle JDK to 21 in `Settings > Build, Execution, Deployment > Build Tools > Gradle > Gradle JDK`.

```bash
export JAVA_HOME="/path/to/jdk21"
./gradlew assembleDebug        # build APK
./gradlew testDebugUnitTest    # 39 unit tests for cycle math & questionnaire logic
```

Output: `app/build/outputs/apk/debug/app-debug.apk`

A detailed architecture walkthrough, cycle-marking rules, questionnaire scoring logic, and known limitations are documented in the Chinese section above (`项目结构` / `周期标注规则` / `自查评估问卷` / `已知限制与待验证项`).

### License

Released under the **MIT License** — see [LICENSE](LICENSE).
