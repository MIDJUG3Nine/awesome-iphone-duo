# Awesome iPhone Duo [![Awesome](https://awesome.re/badge.svg)](https://awesome.re)

English | [简体中文](README.zh-CN.md)

A curated list of resources for building apps for the iPhone Duo, Apple's first foldable iPhone.

The iPhone Duo folds like a passport: a 5.4" outer display when closed and a 7.6" inner display when open, with a hinge that apps can read from iOS 27.1. Apple announced it in September 2026 and it went on sale on 2026-10-23. This list collects what developers have built for it since: libraries, example apps, cross-platform plugins and articles, plus a quick map of the new APIs.

Contributions are welcome. Please read the [contribution guidelines](CONTRIBUTING.md) first.

## Contents

- [Official](#official)
- [APIs at a glance](#apis-at-a-glance)
- [Swift libraries](#swift-libraries)
- [Example apps and demos](#example-apps-and-demos)
- [Cross-platform](#cross-platform)
- [Articles](#articles)
- [Tools for AI coding agents](#tools-for-ai-coding-agents)

## Official

- [Apple Newsroom: Apple unveils iPhone Duo](https://www.apple.com/newsroom/2026/09/apple-unveils-iphone-duo/) - The announcement, with display sizes, hinge design and the fold-aware features in iOS 27.
- [Apple Developer Forums: observing fold posture in SwiftUI](https://developer.apple.com/forums/thread/847888) - Apple's recommended way to read reserved regions such as the crease.

## APIs at a glance

All of these are new in iOS 27.1.

| What you need | SwiftUI | UIKit |
| --- | --- | --- |
| Hinge status and angle | `onHingeChange(isEnabled:_:)`, `DeviceHinge` (`status`, `angle`) | `UIHingeInteraction`, `UIHinge` (`status`, `angle` in radians) |
| Crease and camera cut-outs | `GeometryProxy.reservedRegions(kind:)` with `.division` / `.occlusion` | `UIView.reservedRegions(kind:)` |
| Two views side by side or layered | `ArrangementView` with `.split` / `.overlay` styles | `UIArrangementViewController` with `UISplitArrangement` / `UIOverlayArrangement` |
| Toolbars on the side | `toolbarVerticalEdge`, `toolbarVerticalBehavior(_:)` | `UITraitCollection.verticalBarEdge` |

The iPhone Duo simulator in Xcode's Device Hub has Closed, Partially Open and Open buttons below the bezel; hold Option and drag the slider there to fold to any angle. The tools below add fold controls to Previews and other simulators.

## Swift libraries

- [HingeKit](https://github.com/MIDJUG3Nine/HingeKit) - Turns the hinge into SwiftUI events: opened, closed and a flick-to-turn-page gesture, plus a hinge simulator panel for Previews and any simulator.
- [DuoKit](https://github.com/arjunkshah12345-hash/duokit) - Fold-aware split layouts for SwiftUI and the web, with a reconstruction of the unfold animation.
- [iphone-duo-simulator](https://github.com/acc-ai-tech/iphone-duo-simulator) - Previews iPhone Duo screen sizes, fold and half-open postures inside the iPad simulator.

## Example apps and demos

- [iPhone-Duo-by-Examples](https://github.com/artemnovichkov/iPhone-Duo-by-Examples) - One runnable SwiftUI example per new API, plus links to the author's hinge-driven toy apps.
- [duo-demo](https://github.com/pvinis/duo-demo) - Tiny SwiftUI demo of outer/inner display detection, hinge, crease and two windows talking to each other.
- [Answer Book](https://github.com/MIDJUG3Nine/AnswerBook_iDUO) - Close the phone and it is a book; open it on a random page with an answer. Built on HingeKit.
- [DuoAngle](https://github.com/hutianchi123/DuoAngle) - Hinge angle meter with target angles and haptic alerts, also on the App Store.
- [iPhoneDuoDemo](https://github.com/jboylabo/iPhoneDuoDemo) - Small hinge-status demo with notes (in Japanese) on the hinge slider in Device Hub.
- [anytime: iPhone Duo layout support](https://github.com/hewigovens/anytime/pull/10) - A real-world pull request adapting an existing app, with screenshots.

## Cross-platform

- [Expo Hinge](https://docs.expo.dev/versions/latest/sdk/hinge/) - Hinge angle and status for React Native apps built with Expo, on iPhone Duo and Android foldables.
- [foldable](https://pub.dev/packages/foldable) - Flutter plugin for the iPhone Duo hinge angle, fold posture and fold/camera regions.
- [duo_kit](https://pub.dev/packages/duo_kit) - Flutter package for iPhone Duo layouts.
- [nitro_fold_duo](https://pub.dev/packages/nitro_fold_duo) - Flutter plugin for the iPhone Duo hinge, reserved regions and vertical bars, over Nitro FFI.

## Articles

- [What can the APIs added in iOS 27.1 for iPhone Duo do?](https://dev.classmethod.jp/en/articles/ios27-1-iphone-duo-new-apis/) - Walkthrough of `ArrangementView`, `onHingeChange`, `reservedRegions` and the vertical toolbar modifiers.
- [Apple Unfolds the iPhone Duo](https://tidbits.com/2026/09/11/apple-unfolds-the-iphone-duo/) - TidBITS overview of the hardware and what changes for apps.
- [Get your in-app messages ready for iPhone Duo](https://www.pushwoosh.com/blog/iphone-duo-in-app-messages/) - A compatibility checklist for in-app messages, rich media and push notifications.

## Tools for AI coding agents

- [iphone-duo-skills](https://github.com/mirzaaghazadeh/iphone-duo-skills) - Agent skills for adaptive layout, vertical bars, hinge and scenes, camera and design review on iPhone Duo.

## Star History

<a href="https://www.star-history.com/#MIDJUG3Nine/awesome-iphone-duo&Date">
  <picture>
    <source media="(prefers-color-scheme: dark)" srcset="https://api.star-history.com/svg?repos=midjug3nine%2fawesome-iphone-duo&type=Date&theme=dark" />
    <source media="(prefers-color-scheme: light)" srcset="https://api.star-history.com/svg?repos=midjug3nine%2fawesome-iphone-duo&type=Date" />
    <img alt="Star History Chart" src="https://api.star-history.com/svg?repos=midjug3nine%2fawesome-iphone-duo&type=Date" />
  </picture>
</a>

## License

[![CC0](https://licensebuttons.net/p/zero/1.0/88x31.png)](https://creativecommons.org/publicdomain/zero/1.0/)

To the extent possible under law, the contributors have waived all copyright and related rights to this work.

iPhone is a trademark of Apple Inc. This list is not affiliated with Apple.

Links last checked: 2026-10-30.
