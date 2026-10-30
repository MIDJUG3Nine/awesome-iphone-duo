# Awesome iPhone Duo [![Awesome](https://awesome.re/badge.svg)](https://awesome.re)

[English](README.md) | 简体中文

为 iPhone Duo（Apple 第一款折叠屏 iPhone）开发 App 的资源精选。

iPhone Duo 像护照一样对折：合上时用 5.4 英寸的外屏，打开后是 7.6 英寸的内屏，从 iOS 27.1 起 App 可以读取铰链的状态和角度。Apple 在 2026 年 9 月发布了它，2026-10-23 正式开售。这份清单收集了此后开发者为它做出来的东西：库、示例 App、跨平台插件和文章，另外附一张新 API 速查表。

欢迎补充。提交前请先看[贡献指南](CONTRIBUTING.md)（英文）。

## 目录

- [官方资料](#官方资料)
- [API 一览](#api-一览)
- [Swift 库](#swift-库)
- [示例 App 和演示](#示例-app-和演示)
- [跨平台](#跨平台)
- [文章](#文章)
- [给 AI 编程助手用的工具](#给-ai-编程助手用的工具)

## 官方资料

- [Apple Newsroom: Apple unveils iPhone Duo](https://www.apple.com/newsroom/2026/09/apple-unveils-iphone-duo/) - 发布公告，包括屏幕尺寸、铰链设计和 iOS 27 里与折叠相关的功能。
- [Apple Developer Forums: observing fold posture in SwiftUI](https://developer.apple.com/forums/thread/847888) - Apple 推荐的读取折痕等保留区域的方法。

## API 一览

以下 API 都是 iOS 27.1 新增的。

| 你要做的事 | SwiftUI | UIKit |
| --- | --- | --- |
| 铰链状态和角度 | `onHingeChange(isEnabled:_:)`、`DeviceHinge`（`status`、`angle`） | `UIHingeInteraction`、`UIHinge`（`status`、以弧度表示的 `angle`） |
| 折痕和摄像头遮挡区域 | `GeometryProxy.reservedRegions(kind:)`，配合 `.division` / `.occlusion` | `UIView.reservedRegions(kind:)` |
| 两个视图并排或叠放 | `ArrangementView`，样式 `.split` / `.overlay` | `UIArrangementViewController`，配合 `UISplitArrangement` / `UIOverlayArrangement` |
| 竖向侧边工具栏 | `toolbarVerticalEdge`、`toolbarVerticalBehavior(_:)` | `UITraitCollection.verticalBarEdge` |

Xcode Device Hub 里的 iPhone Duo 模拟器在机身下方有 Closed、Partially Open 和 Open 三个按钮；按住 Option 拖动那里的滑块，可以折到任意角度。下面的一些工具还能在 Xcode 预览和其他模拟器里提供折叠控制。

## Swift 库

- [HingeKit](https://github.com/MIDJUG3Nine/HingeKit) - 把铰链变成 SwiftUI 事件：打开、合上，以及「快速半合再打开」的翻页手势；附带铰链模拟面板，可在预览和任意模拟器中使用。
- [DuoKit](https://github.com/arjunkshah12345-hash/duokit) - 面向 SwiftUI 和 Web 的折叠感知分栏布局，还复刻了展开动画。
- [iphone-duo-simulator](https://github.com/acc-ai-tech/iphone-duo-simulator) - 在 iPad 模拟器里预览 iPhone Duo 的屏幕尺寸、折叠和半开姿态。

## 示例 App 和演示

- [iPhone-Duo-by-Examples](https://github.com/artemnovichkov/iPhone-Duo-by-Examples) - 每个新 API 一个可运行的 SwiftUI 示例，还链接了作者用铰链驱动的几个小玩具 App。
- [duo-demo](https://github.com/pvinis/duo-demo) - 很小的 SwiftUI 演示：识别内外屏、读取铰链和折痕，以及两个窗口之间互相通信。
- [Answer Book](https://github.com/MIDJUG3Nine/AnswerBook_iDUO) - 合上手机是一本书，打开就随机翻到写着答案的一页。基于 HingeKit。
- [DuoAngle](https://github.com/hutianchi123/DuoAngle) - 铰链角度计，可设目标角度并用触感提醒，App Store 上也能下载。
- [iPhoneDuoDemo](https://github.com/jboylabo/iPhoneDuoDemo) - 小型铰链状态演示，附有关于 Device Hub 铰链滑块的说明（日文）。
- [anytime: iPhone Duo layout support](https://github.com/hewigovens/anytime/pull/10) - 一个现有 App 适配 iPhone Duo 的真实 PR，带截图。

## 跨平台

- [Expo Hinge](https://docs.expo.dev/versions/latest/sdk/hinge/) - 为用 Expo 构建的 React Native App 提供铰链角度和状态，支持 iPhone Duo 和安卓折叠屏。
- [foldable](https://pub.dev/packages/foldable) - Flutter 插件，读取 iPhone Duo 的铰链角度、折叠姿态以及折痕和摄像头区域。
- [duo_kit](https://pub.dev/packages/duo_kit) - 用于 iPhone Duo 布局的 Flutter 包。
- [nitro_fold_duo](https://pub.dev/packages/nitro_fold_duo) - 基于 Nitro FFI 的 Flutter 插件，支持 iPhone Duo 铰链、保留区域和竖向工具栏。

## 文章

- [What can the APIs added in iOS 27.1 for iPhone Duo do?](https://dev.classmethod.jp/en/articles/ios27-1-iphone-duo-new-apis/) - 逐个讲解 `ArrangementView`、`onHingeChange`、`reservedRegions` 和竖向工具栏修饰符。
- [Apple Unfolds the iPhone Duo](https://tidbits.com/2026/09/11/apple-unfolds-the-iphone-duo/) - TidBITS 对硬件的概览，以及对 App 有哪些影响。
- [Get your in-app messages ready for iPhone Duo](https://www.pushwoosh.com/blog/iphone-duo-in-app-messages/) - 应用内消息、富媒体和推送通知的兼容性检查清单。

## 给 AI 编程助手用的工具

- [iphone-duo-skills](https://github.com/mirzaaghazadeh/iphone-duo-skills) - 一组 agent skill，涵盖 iPhone Duo 上的自适应布局、竖向工具栏、铰链与场景、相机以及设计审查。

## Star 趋势

<a href="https://www.star-history.com/#MIDJUG3Nine/awesome-iphone-duo&Date">
  <picture>
    <source media="(prefers-color-scheme: dark)" srcset="https://api.star-history.com/svg?repos=midjug3nine%2fawesome-iphone-duo&type=Date&theme=dark" />
    <source media="(prefers-color-scheme: light)" srcset="https://api.star-history.com/svg?repos=midjug3nine%2fawesome-iphone-duo&type=Date" />
    <img alt="Star History Chart" src="https://api.star-history.com/svg?repos=midjug3nine%2fawesome-iphone-duo&type=Date" />
  </picture>
</a>

## 许可

[![CC0](https://licensebuttons.net/p/zero/1.0/88x31.png)](https://creativecommons.org/publicdomain/zero/1.0/)

在法律允许的范围内，贡献者已放弃本作品的全部版权及相关权利。

iPhone 是 Apple Inc. 的商标。本清单与 Apple 无关。

链接最后检查日期：2026-10-30。
