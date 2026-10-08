# 安装与使用

## 导入

在 Adobe Camera Raw 的配置文件浏览器菜单中使用导入配置文件入口，选择解压后的 `.dcp` 文件。界面名称可能因语言和版本不同而变化。

macOS 也可以手动安装：在 Finder 的“前往文件夹”中输入下面的用户目录，将需要的 DCP 放入自行新建的子文件夹：

```text
~/Library/Application Support/Adobe/CameraRaw/CameraProfiles/
```

保存当前工作并重新打开 Camera Raw；列表未刷新时，重新启动承载它的 Photoshop / Bridge 或 Lightroom。保留原有配置，方便随时比较。

## 选择配置

打开 Canon EOS R8 的 `.CR3`，在配置文件浏览器中按名称寻找：

- `Fionn R8 VisionLOG 5D4 Match v1`
- `Fionn R8 NaturalFlat v1`
- `Fionn R8 LinearBase v1`

分组名称可能随应用版本变化。普通 JPG / PNG 或 Photoshop 的 Camera Raw 滤镜不适合验证 R8 专用 DCP 是否正确安装。

## 调色建议

1. 先创建快照或使用 RAW 副本，保留已有编辑。
2. 选择一份配置后，检查此前为其他配置添加的大幅曲线、对比度、饱和度补偿，必要时重新建立基础调整。
3. 先定白平衡和曝光，再调整高光、阴影、黑白点，最后微调颜色。
4. 5D4 Match 可以从熟悉的 5D4 VisionLOG 调色步骤开始，但旧参数和旧 LUT 的兼容性仍需自行验证。
5. 打开到 Photoshop 时可使用 16 位，并保留正确的 ICC 色彩配置；使用第三方 LUT 时需匹配该 LUT 的输入颜色空间。

切换回 Adobe Color、Camera Neutral 等配置即可停止使用。若要卸载，先让使用这些配置的照片改用其他配置，再删除对应 DCP 并重新启动应用。

## 校验下载

macOS 终端进入解压后的包目录，运行：

```sh
shasum -a 256 -c SHA256SUMS
```

该检查只验证文件是否与发布包一致，不评估照片颜色准确度。
