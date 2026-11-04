# Hyperbid Official CocoaPods Specs

**English** | [中文说明](README.md)

The official CocoaPods Spec repository for Hyperbid iOS SDK and mediation adapters.

## Usage

Add the following spec sources at the **very top** of your `Podfile`:

```ruby
# 1. Hyperbid Official Specs (for Hyperbid SDK)
source 'https://github.com/hyperbidsdk-packages/Hyperbid_Specs.git'

# 2. CocoaPods Official Trunk CDN (for third-party SDK)
source 'https://cdn.cocoapods.org/'
```

### Example `Podfile`

```ruby
platform :ios, '11.0'
use_frameworks!

target 'MyAppTarget' do
 
  # Add Hyperbid XXX SDK
  pod 'HyperbidXXSDK'

end
```

## FAQ & Troubleshooting

### 1. Cannot find the latest version when running `pod install`?
CocoaPods caches spec repositories locally. When a new version is released, update your local spec repo with:
```bash
pod repo update Hyperbid_Specs
# Or install with repo update:
pod install --repo-update
```

### 2. Why is `https://cdn.cocoapods.org/` required?
Because mediation adapters depend on the official third-party network SDKs (such as CSJ, GDT, Baidu, etc.), which are hosted on the public CocoaPods registry.
