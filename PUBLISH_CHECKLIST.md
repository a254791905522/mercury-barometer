# Mercury Barometer - Publish Checklist

## 1. Project Configuration
- [x] Bundle ID contains 'rosewood': com.rosewood.mercurybarometer.game
- [x] TARGETED_DEVICE_FAMILY: "1" (iPhone only) at target level
- [x] No iPad support (UIDeviceFamily = 1 only)
- [x] project.yml has no hardcoded signing restrictions
- [x] DEVELOPMENT_TEAM empty (uses Xcode Signing & Capabilities selection)
- [x] CODE_SIGN_STYLE: Automatic
- [x] MARKETING_VERSION: "1.0"
- [x] CURRENT_PROJECT_VERSION: "1"
- [x] Deployment target: iOS 15.0

## 2. Info.plist
- [x] CFBundleDisplayName: "Mercury Barometer"
- [x] CFBundleIconName: "AppIcon"
- [x] ITSAppUsesNonExemptEncryption: false
- [x] UILaunchStoryboardName: "LaunchScreen"
- [x] UIRequiredDeviceCapabilities: arm64
- [x] UISupportedInterfaceOrientations: UIInterfaceOrientationPortrait only

## 3. App Icon
- [x] AppIcon.appiconset has all required sizes (12 icons: 8 iPhone + 3 iPad + 1 marketing)
- [x] 1024x1024 marketing icon: no Alpha channel (RGB)
- [x] All icons: no Alpha channel (RGB)
- [x] Contents.json complete and valid

## 4. Launch Screen
- [x] LaunchScreen.storyboard root tag is `<document>` (lowercase)
- [x] No references to non-existent images
- [x] Shows game title "Mercury Barometer" and subtitle "Whispers of Pressure"

## 5. Debug UI
- [x] showsFPS: NO
- [x] showsNodeCount: NO
- [x] Status bar hidden

## 6. Template Residue
- [x] No tw_* assets
- [x] No game_01_* assets
- [x] No Template assets
- [x] No Backgrounds.imageset residue
- [x] All class prefixes are MB, all node names are kNode*, all persistence keys are mb_*

## 7. Screenshots
- [x] screenshots_65/ (1284x2778, 6.5" display) - 5 screenshots (01_menu, 02_game1, 03_game2, 04_game3, 05_game-success)
- [x] screenshots_55/ (1242x2208, 5.5" display) - 5 screenshots (01_menu, 02_game1, 03_game2, 04_game3, 05_game-success)
- [x] All screenshots: no Alpha channel (RGB mode)
- [x] Screenshots show real gameplay

## 8. Release Project
- [x] MercuryBarometer-ReleaseProject/ created
- [x] Sources synced from MercuryBarometerGame
- [x] project.yml synced (no signing restrictions)
- [x] xcodegen generate successful
- [x] Info.plist has arm64 (not armv7)
- [x] TARGETED_DEVICE_FAMILY = 1 only in .xcodeproj

## 9. Publish Files
- [x] index.html (uses screenshots_65/ images, /privacy.html link)
- [x] privacy.html (offline, no data collection)
- [x] keywords.txt (94 chars, under 100 limit)
- [x] README.md
- [x] GAMEPLAY_FACT_CARD.md
- [x] PUBLISH_CHECKLIST.md (this file)
- [x] appstore-review-text.html (Format 3: .field + label + pre.value)

## 10. Archive Build
- [ ] xcodebuild archive with CODE_SIGNING_ALLOWED=NO - ARCHIVE SUCCEEDED
- [ ] Verify .app contains: Assets.car, AppIcon*.png, LaunchScreen.storyboardc
- [ ] Verify CFBundleIdentifier = com.rosewood.mercurybarometer.game
- [ ] Verify CFBundleDisplayName = Mercury Barometer
- [ ] Verify UIDeviceFamily = 1

## 11. GitHub/Vercel Deployment
- [ ] Push publish/MercuryBarometer/ to GitHub (gh account: a254791905522, repo: mercury-barometer)
- [ ] Use proxy 127.0.0.1:7897
- [ ] Vercel deployed: https://mercury-barometer.vercel.app
- [ ] curl verify index.html live (HTTP/2 200)
- [ ] curl verify /privacy.html live (HTTP/2 200, no 308 redirect)

## 12. App Store Connect
- [ ] App name: Mercury Barometer
- [ ] Subtitle: Whispers of Pressure
- [ ] Bundle ID: com.rosewood.mercurybarometer.game
- [ ] SKU: mercurybarometer-ios-001
- [ ] Support URL: https://mercury-barometer.vercel.app
- [ ] Privacy Policy URL: https://mercury-barometer.vercel.app/privacy.html
- [ ] Screenshots uploaded (1284x2778 and 1242x2208)
- [ ] Keywords from keywords.txt
- [ ] Description from appstore-review-text.html
- [ ] Reviewer: Evans Omondi (Last: Omondi / First: Evans)
- [ ] Phone: +1 2096550297
- [ ] Email: croitorzamkov@gmail.com

## 13. Validation
- [ ] validate_appstore_review_text.py: ALL CHECKS PASSED

## 14. Notes
- Music/Sound toggles exist in Settings but no audio files are shipped in v1.0 (silent game)
- Multi-day contracts at L9/L20 (3 days) and L35/L50 (5 days)
- Difficulty progression by available weather choices: L1-5 (2), L6-15 (3), L16-30 (4), L31+ (5)
