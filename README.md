# Netki Specs

CocoaPods spec source for Netki's iOS SDKs.

CocoaPods Trunk stops accepting new Podspecs on **2 December 2026**
([announcement](https://blog.cocoapods.org/CocoaPods-Specs-Repo/)). Versions published after
that date live here instead. Everything already on Trunk stays there and keeps resolving, so
existing builds are unaffected.

## Using it

Add **both** sources to your `Podfile`:

```ruby
source 'https://cdn.cocoapods.org/'
source 'https://github.com/netkicorp/Specs.git'

pod 'NetkiSDK', '~> 13.1'
```

The first line is not optional. CocoaPods uses the CDN implicitly *only* while a Podfile
declares no sources of its own; the moment you add one, the default is dropped and every other
pod in your project stops resolving. The resulting errors name those pods rather than this
change, so it is an easy hour to lose.

Nothing else changes — the same `pod` lines, versions and version operators work as before.

## Layout

```
Specs/NetkiSDK/<version>/NetkiSDK.podspec.json
```

Published automatically by `onboardid-pod` when a release is tagged. Each podspec points at the
`NetkiSDK.xcframework` carried by the matching `onboardid-pod` tag.
