# Mercury Barometer - Gameplay Fact Card

## App Identity
- **App Name**: Mercury Barometer
- **Subtitle**: Whispers of Pressure
- **Bundle ID**: com.rosewood.mercurybarometer.game
- **Platform**: iOS 15.0+, iPhone only, Portrait
- **Framework**: SpriteKit + Objective-C
- **Version**: 1.0

## Core Gameplay Loop
1. Three instruments (barometer / thermometer / hygrometer) animate to daily readings
2. Player observes the readings and the weather hint text
3. Player taps one of 5 weather prediction buttons (Sunny / Cloudy / Rainy / Storm / Snowy)
4. Correct prediction: village safety unchanged. Wrong prediction: -20% village safety
5. Multi-day contracts (L9, L20, L35, L50): 3 or 5 consecutive daily predictions
6. Result panel: stars awarded based on accuracy (60) + speed (20) + village safety (20)

## Units / Characters
- **Player role**: Village weather observer (no on-screen avatar)
- **Instruments**:
  - Barometer (hPa, 940–1060, silver)
  - Thermometer (°C, -25 to 48, red)
  - Hygrometer (%RH, 0–100, blue)
- **Weather types**: Sunny, Cloudy, Rainy, Storm, Snowy
- **Village**: 4 houses + 5 trees, drawn as 2D shapes

## Level Progression
- **50 levels** across 5 atmospheric observation stations
- **Stations** (10 levels each):
  1. Royal Society London (L1–L10): all 3 instruments visible
  2. Alpine Monastery (L11–L20): 1 instrument hidden
  3. North American Plains (L21–L30): 1 instrument hidden
  4. Yangtze Observatory (L31–L40): 2 instruments hidden
  5. Arctic Field Station (L41–L50): 2 instruments hidden
- **Difficulty progression**:
  - L1–L5: 2 weather choices
  - L6–L15: 3 choices
  - L16–L30: 4 choices
  - L31+: 5 choices
- **Multi-day contracts**: L9, L20 (3 days); L35, L50 (5 days)
- **Unlock rule**: Level N unlocked only if Level N-1 earned ≥ 1 star

## Scoring
- **Accuracy**: (correct / total) × 60 = 60 max
- **Speed**: max(0, 20 − total_time × 0.5) = 20 max
- **Village Safety**: villageHealth × 0.2 = 20 max (starts at 100)
- **Total**: clamp to [0, 100]
- **Stars**:
  - 3 stars: total ≥ 80
  - 2 stars: 60 ≤ total < 80
  - 1 star: 40 ≤ total < 60
  - 0 stars (Try Again): total < 40

## Mechanics
- Tap-only controls
- Smoothstep instrument fill animation (0.8s)
- Red/green feedback text on prediction (1.5s)
- "Day X/Y" indicator on multi-day levels
- Daily results string on multi-day result panels (e.g., "YNYNY")
- No scoring loops or economy; pure prediction puzzle

## Monetization
- None. No IAP, no ads, no analytics, no tracking.

## Data Collection
- Local only via NSUserDefaults
- Keys: `mb_level_N_stars`, `mb_level_N_highscore`, `mb_unlockedLevels`, `mb_musicEnabled`, `mb_soundEnabled`
- No network calls of any kind

## Template Residue Check
- No `tw_*` assets
- No `game_01_*` assets
- No `Template` references
- No empty `Backgrounds.imageset`
- All class prefixes are `MB`, all node names are `kNode*`, all persistence keys are `mb_*`

## Debug UI Status
- `showsFPS = NO`
- `showsNodeCount = NO`
- Status bar hidden

## Notes for Reviewer
- The App is fully offline; no network calls at all
- ITSAppUsesNonExemptEncryption = false
- Music/Sound toggles exist in Settings but no audio files are shipped in v1.0 (silent game)
