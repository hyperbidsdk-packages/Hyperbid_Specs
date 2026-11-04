# Hyperbid Official CocoaPods Specs

[English](README_EN.md) | **中文说明**

本仓库为 Hyperbid iOS SDK 及各类广告平台 Mediation Adapter 的官方 CocoaPods Specs 仓库。

## 接入方式 (Usage)

在您项目的 `Podfile` **最顶部** 添加以下两个源：

```ruby
# 1. Hyperbid 官方 Specs 源 (用于获取 Hyperbid SDK)
source 'https://github.com/hyperbidsdk-packages/Hyperbid_Specs.git'

# 2. CocoaPods 官方公共源 (用于解析第三方SDK依赖)
source 'https://cdn.cocoapods.org/'
```

### 示例 (Example)

```ruby
platform :ios, '11.0'
use_frameworks!

target 'MyAppTarget' do

  #Add Hyperbid XXX SDK
  pod 'HyperbidXXSDK'

end
```

## 常见问题 (FAQ)

### 1. 执行 `pod install` 提示找不到新版本？
由于 CocoaPods 本地会缓存 Spec 仓库，当 Hyperbid 发布新版本后，请使用以下命令更新本地源：
```bash
pod repo update Hyperbid_Specs
# 或者在安装时强制更新源：
pod install --repo-update
```

### 2. 为什么必须保留 `cdn.cocoapods.org`？
因为各个广告平台 Adapter（如穿山甲、广点通、百度等）依赖三方广告平台官方发布的底层 SDK，保留官方源才能正常拉取三方广告依赖。
