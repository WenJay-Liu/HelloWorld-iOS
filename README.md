# HelloWorld-iOS

最简单的 SwiftUI Hello World iOS 应用。

## 构建

使用 Xcode 打开 `HelloWorld.xcodeproj`，选择 iOS Simulator 或真机后运行。

## Codemagic 与免费 Apple ID 安装

选择 master 分支的 `ios-hello-world` 工作流，显示名称为
`HelloWorld iOS - unsigned for local signing`。

云端使用 iphoneos SDK 编译 ARM64 真机应用，禁用构建阶段签名，
再将应用按 Payload/HelloWorld.app 结构打包为
`build/ios/ipa/HelloWorld-unsigned.ipa`。不调用签名导出流程，
不需要 export_options.plist 或上传 Apple 证书。

该 IPA 尚未签名，不能直接在 iPhone 上点开安装。下载后在 Windows
使用 Sideloadly（https://sideloadly.io/），连接并信任自己的 iPhone，
选择 IPA，使用自己的免费 Apple ID 完成签名安装。
Apple ID 登录及验证由用户自己完成；不要将凭证提交到仓库。
免费账号安装的应用通常每 7 天需要重新签名。
按安装工具和手机提示完成开发者信任及开发者模式设置。

最低支持 iOS 17.0；iPhone 12 Pro Max 需运行 iOS 17 或更新版本。
Windows 无法运行 Xcode，本地修改后的实际编译结果以 Codemagic 为准。
