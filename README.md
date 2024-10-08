# BFGlassView
![frontPhoto](https://github.com/Chaehui-Seo/BFGlassView/assets/73422344/347a0b5f-08a2-477e-861f-993278ba5f35)


Glassmorphism is a design style using a background blur effect, which makes the view look like a floating translucent glass.

## Requirements
- iOS 11.0+

## Installation
### Swift Package Manager
Use [Swift Package Manager](https://swift.org/package-manager/) by adding following line to `Package.swift`:
```
dependencies: [
 .package(url: "https://github.com/Chaehui-Seo/BFGlassView.git", from: "1.0.1")
]
```
### Cocoapods
Use [Cocoapods](https://cocoapods.org/) by adding following line to `Podfile`:
```
pod "BFGlassView", "~> 1.0.1"
```

## Usage
### Create glassmorphismView
METHOD #1 <br>
Import `BFGlassView` module in your viewController. Now, you can create glassmorphism view programmatically like code below.

```swift
import BFGlassView

let glassmorphismView = BFGlassView()
```
METHOD #2 <br>
Or make existing UIView as glassmorphism view by changing the Custom Class to `BFGlassView`

<img width="700" alt="storyboard" src="https://user-images.githubusercontent.com/73422344/225058917-118067e4-eaab-4a3f-ac72-326ac5d203d0.png"> <br>

### Change customizing options
```swift
// MARK: - [Theme]
glassmorphismView.setTheme(theme: .light) // choose theme .light or .dark (default value is .light)
```
| Light theme | Dark theme |
| :-: | :-: |
| <img src="https://user-images.githubusercontent.com/73422344/224743779-0b29a653-5d8c-409a-b9a2-355f933521e7.png" width=250> | <img src="https://user-images.githubusercontent.com/73422344/224717507-192408ee-7bec-4297-be67-ec943307cc41.png" width=250> |

```swift
// MARK: - [Blur Density]
glassmorphismView.setBlurDensity(with: 0.5) // value from 0 to 1 is available (default value is 0.65)
```
| Light theme | Dark theme |
| :-: | :-: |
| ![Simulator Screen Recording - iPhone 11 - 2023-03-22 at 00 45 27](https://user-images.githubusercontent.com/73422344/226663271-572b705b-df21-4dcd-8745-7e56628bcb4d.gif) | ![Simulator Screen Recording - iPhone 11 - 2023-03-22 at 00 45 54](https://user-images.githubusercontent.com/73422344/226664138-af73c66a-86f3-4216-bd28-f945838dbe78.gif) |
```swift
// MARK: - [Corner Radius]
glassmorphismView.setCornerRadius(30) // change cornerRadius as you want (default value is 20)
```
```swift
// MARK: - [Shadow Radius (Shadow Spread)]
glassmorphismView.setDistance(30) // change shadowRadius(shadow spread) that makes a sense of distance  (default value is 20)
```

## SampleApp
You can run SampleApp Project located in `SampleApp` folder.
All the functions that provided by the package are testable through the SampleApp project.

![Simulator Screen Recording - iPhone 11 - 2023-03-23 at 18 47 01](https://user-images.githubusercontent.com/73422344/227165502-9c7548a7-dd1b-4273-9196-d923bd3e8ac4.gif)


## Caution
Be aware that any views underneath blurred view got affected by glassmorphism effect. That means if some views are inserted before blurred view, it would not be visible as expected.
Do not insert any views at 0 if you don’t want the elements to be dimmed
```swift
// DO ⭕️
glassmorphismView.addSubview(yourOwnView)

// DO NOT ❌
glassmorphismView.insertSubview(yourOwnView, at: 0)
```
