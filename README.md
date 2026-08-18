# 星海音乐源（xinghai-music-source.js）

> LX Music 自定义音源插件 | 仅供个人学习与交流使用

## 简介

星海音乐源是一款 LX Music 自定义音源插件，聚合 GDAPI、ChKSz API 等公开接口，支持网易云、QQ、酷我、酷狗、咪咕五大平台的音乐获取。

酷我平台返回的加密音频（`.mflac` / `.mgg`）可配合 [kuwo-music-relay](https://github.com/cdyUuu/kuwo-music-relay) 中转解密服务器实现实时解密播放，无需下载后手动处理。

## 支持平台与音质

| 平台 | 音质选项 |
|------|----------|
| 网易云音乐 | 128k / 192k / 320kbps / FLAC / FLAC 24bit / Hi-Res / 臻品音质 / 沉浸声 / 臻品母带 |
| QQ音乐 | 128k / 192k / 320kbps / FLAC / Hi-Res / 杜比全景声 / 杜比全景声+ / 母带 |
| 酷我音乐 | 128k / 320kbps / FLAC / Hi-Res / 杜比全景声 / 母带 |
| 酷狗音乐 | 128k / 320kbps / FLAC / Hi-Res / 杜比全景声 / 母带 |
| 咪咕音乐 | 128k / 320kbps / FLAC |

## 安装步骤

1. 打开 LX Music，进入「我的」→「设置」
2. 找到「自定义音源」，点击「添加音源」
3. 访问 [https://zrcdy.dpdns.org/lx/vers.php](https://zrcdy.dpdns.org/lx/vers.php)，选择需要的版本，复制链接或下载文件
4. 在 LX Music 中粘贴链接或选择文件，点击导入

## 酷我加密音频解密

酷我平台的高音质音频通常以 `.mflac`（加密 FLAC）或 `.mgg`（加密 OGG）格式返回，附带 `ekey` 解密密钥。

**注意：插件默认不会返回加密歌曲，需要自行部署解密服务并配置后才会启用。**

配置步骤：

1. 自行部署 [kuwo-music-relay](https://github.com/cdyUuu/kuwo-music-relay) 中转解密服务器（PHP 单文件，支持 Docker）
2. 打开插件 JS 文件，在第 14 行附近的 `KW_DECRYPT_PROXY` 配置区域填入你的服务器地址
3. 将 `allowEncryptedLossless` 设为 `true`
4. 配置完成后，插件会将加密音频链接和 ekey 发送到你的解密服务器，解密后返回明文音频流

未配置解密服务时，酷我平台仅返回 128k / 320k / FLAC 等非加密格式。

## 免责声明

- 本脚本**仅用于个人学习与交流**，所有音乐资源均来自公开网络 API
- 请遵守相关法律法规，支持正版音乐，**禁止用于商业用途**
- 音源可用性依赖第三方 API 稳定性，若出现失效可等待脚本更新

## 资源来源

- 音源数据来自公开接口：`GDAPI` | `聚合` | `ChKSz API`
- 作者整理封装为 LX Music 格式

## 关联项目

- [kuwo-music-relay](https://github.com/cdyUuu/kuwo-music-relay) — 酷我音乐中转解密服务器（PHP 单文件实现）

## 反馈与支持

反馈链接：[https://zrcdy.dpdns.org/send_news.php](https://zrcdy.dpdns.org/send_news.php)
欢迎通过 Issue 反馈问题，或直接联系作者。

## 关于赞赏

如果觉得本音源好用，欢迎扫码赞赏支持（纯自愿）：
<img src="https://zrcdy.dpdns.org/lx/1.png" alt="赞赏码" width="200">

如果觉得有用，请给个 Star 支持一下～
