# Canon EOS R8 · VisionLOG 与照片调色配置

为 **Canon EOS R8 静态 RAW 照片**制作的三份非官方 DCP 配置，适用于支持 R8 RAW 与 DCP 的 Adobe Camera Raw / Lightroom 工作流。主版本 **5D4 Match** 以 5D Mark IV VisionLOG 的调色起点为参考，另提供 NaturalFlat、LinearBase 两个照片基础配置。

**当前发布：v0.1.0 预览版（2026-10-09）。** 文件结构及数值检查已完成；尚未完成完整的 RAW 渲染验收、色卡校准或同场景 5D4 / R8 实拍匹配。名称中的 “Match” 表示设计目标，不表示已测得两机颜色一致。

## 下载

**[下载全部配置与中文说明](https://github.com/FIONN191/canon-r8-visionlog-profiles/releases/download/v0.1.0/Fionn-R8-Profiles-v0.1.0.zip)** · [发布页面](https://github.com/FIONN191/canon-r8-visionlog-profiles/releases/tag/v0.1.0)

| 配置 | 设计与用途 | 单独下载 |
| --- | --- | --- |
| **Fionn R8 VisionLOG 5D4 Match v1** | 希望沿用 5D4 VisionLOG 调色方法时先试这一份。保留参考的曲线、HueSatMap 和 Look Table，近似适配 R8 输入颜色。 | [DCP](profiles/5d4-match/Fionn%20R8%20VisionLOG%205D4%20Match%20v1.dcp) |
| **Fionn R8 NaturalFlat v1** | 以 R8 Camera Neutral 为颜色基础；曲线为 80% 原曲线 + 20% 恒等曲线。适合希望温和降低预置反差的照片工作流。 | [DCP](profiles/photo-base/Fionn%20R8%20NaturalFlat%20v1.dcp) |
| **Fionn R8 LinearBase v1** | 同一 Camera Neutral 颜色基础，DCP 曲线改为恒等直线，供自行建立明暗关系或比较使用。 | [DCP](profiles/photo-base/Fionn%20R8%20LinearBase%20v1.dcp) |

单独下载时，在 GitHub 文件页面使用 **Download raw file** 下载原始文件。首次使用推荐下载 ZIP。

## 安装与开始使用

1. 解压下载包，在 Camera Raw 的配置文件浏览器菜单中导入所需的 `.dcp` 文件；也可按[安装说明](docs/installation.zh-CN.md)复制到用户配置目录。
2. 保存正在编辑的工作，关闭并重新打开 Camera Raw；必要时重新启动 Photoshop / Bridge / Lightroom。
3. 打开 **Canon EOS R8 的原始 `.CR3`**，在配置文件浏览器中选择上表对应名称。
4. 用快照或 RAW 副本比较。先重新确定白平衡和曝光，再调整曲线、黑白点与颜色。

5D4 Match 保留了参考的灰片曲线，仍需要还原和调色。NaturalFlat 与 LinearBase 是另两种起点，不是 5D4 Match 的前置或后置步骤；每次选择一份配置即可。

## 适用范围与验证

- 这些文件是 RAW 相机配置，**不是 `.cube` 3D LUT，也不是 Canon C-Log3 / S-Log3 / LogC 编码**。不能默认套用对应视频 Log 的还原 LUT。
- DCP 曲线变平不会增加传感器动态范围；LinearBase 也不代表 Camera Raw 的完整处理流程或导出文件为场景线性。
- 5D4 Match 使用矩阵近似迁移。数值模型通过不代表肤色、高饱和服装、混合 LED 光源下的实拍颜色准确。
- 原参考的抬黑、压白曲线端点被保留；其端点不符合严格的 DNG SDR 端点要求，详见[技术说明](docs/technical-notes.zh-CN.md)。
- [校验记录](validation/)与 [SHA-256](SHA256SUMS)用于复核生成数据与文件完整性；不等同于相机实拍认证。

## 数据来源与项目关系

这是个人制作的非官方改编项目，未获 Canon、Adobe 或 VisionColor 背书。5D4 Match 使用 VisionLOG 参考风格数据及 Adobe 相机标定数据；NaturalFlat / LinearBase 基于 Adobe R8 Camera Neutral。相关版权元数据保留，详见 [第三方来源说明](THIRD_PARTY_NOTICES.md)。本仓库未给第三方配置数据重新授予 MIT 等开源许可。

欢迎通过 [Issues](https://github.com/FIONN191/canon-r8-visionlog-profiles/issues)反馈相机型号、应用版本、所选配置和光线条件下的使用表现。
