# Settings Feature Testing Guide

## Quick Start Testing

### How to Access Settings
1. Play a game and lose
2. Click "Scores" button on start screen → View leaderboard
3. Click "⚙️ Settings" button on leaderboard screen
4. Adjust settings and click "✓ Save"

### Basic Functionality Test (5 minutes)
```
□ Settings screen displays all 4 sections
□ All 10 settings are visible and interactable
□ Sliders respond to mouse/touch input
□ Checkboxes toggle on/off
□ Radio buttons select properly
□ Value displays update in real-time
□ Save button closes settings
□ Cancel button closes without saving
```

### Preset Testing
```
□ Click "↺ Reset to Default" button
  - All sliders return to default values
  - All checkboxes are checked
  - Affectionate tips style is selected
  - Dark theme is selected

□ Click "⚡ Difficult Mode" button
  - Gravity set to 0.5 (harder)
  - Jump Power set to 9 (harder jumps)
  - Platform gaps wider (65-100)
  - Game speed at 1.2x
  - Power-up rate lower at 10%
  - Hint frequency at 5 (less frequent tips)
```

### Gameplay Integration Test (Each ~2 minutes)

#### Test 1: Gravity Impact
```
1. Set Gravity to minimum (0.1) → Save → Play
   □ Character falls SLOWLY
   □ Easy to make jumps
   □ Can hover briefly in air
   
2. Set Gravity to maximum (0.6) → Save → Play
   □ Character falls FAST
   □ Hard to make jumps
   □ Less control
```

#### Test 2: Jump Power Impact
```
1. Set Jump Power to minimum (8) → Save → Play
   □ Can barely reach next platforms
   □ Must be precise with timing
   □ Score stays low without platforms
   
2. Set Jump Power to maximum (14) → Save → Play
   □ Can reach very high
   □ Easy to clear platforms
   □ Score increases quickly
```

#### Test 3: Platform Gap Impact
```
1. Set gaps to tight (Min: 30, Max: 50) → Save → Play
   □ Platforms appear very close together
   □ Easy to climb quickly
   □ Less precision required
   
2. Set gaps to wide (Min: 70, Max: 120) → Save → Play
   □ Large distances between platforms
   □ Hard to reach next platform
   □ Requires precise jumps
```

#### Test 4: Game Speed Impact
```
1. Set Speed to 0.7x (slow) → Save → Play
   □ Gravity effect is slower
   □ Jump is slower
   □ Overall game feels sluggish
   □ Easier to control
   
2. Set Speed to 1.5x (fast) → Save → Play
   □ Everything happens faster
   □ Harder to react
   □ Game feels more intense
```

#### Test 5: Power-Up Spawn Rate
```
1. Set Power-Up Rate to 8% (minimum) → Play to score 500+
   □ Very few power-ups appear
   □ Game relies on normal jumping
   
2. Set Power-Up Rate to 35% (maximum) → Play
   □ Power-ups appear frequently
   □ Many benefits (shields, rockets, etc.)
   □ Game is easier with boosts
```

#### Test 6: Character Selection
```
1. Uncheck all characters except Cow → Save → Play 5 times
   □ Every game uses 🐄 character
   
2. Check only Bunny & Robot → Save → Play 10 times
   □ Only sees 🐰 or 🤖
   □ Random selection between the two
   
3. Check all characters → Save → Play 20 times
   □ Sees variety of all 6 characters
```

#### Test 7: Hint Frequency
```
1. Set to 2 (most frequent) → Play
   □ Romantic tip shows every 2 platforms
   □ Tips appear very often
   
2. Set to 8 (least frequent) → Play
   □ Tips only show every 8 platforms
   □ Fewer romantic messages
```

### Persistence Testing

#### Local Storage Test
```
1. Set custom values (e.g., Gravity 0.5, Jump 10) → Save
2. Close browser completely
3. Reopen game
4. Click Scores → Settings
□ All custom values are still there
□ Settings persisted correctly

5. Click "↺ Reset to Default" → Save
6. Close and reopen browser
□ Settings are back to defaults
```

#### Edge Cases
```
1. Set gravity to minimum (0.1) → Save → Play until game over
□ Game doesn't crash
□ Score is calculated correctly

2. Set jump power to maximum (14) → Save → Play
□ Physics work correctly
□ No visual glitches

3. Uncheck all characters → Save → Play
□ Game still selects a character (fallback works)
□ No crashes

4. Rapid setting changes (change sliders quickly) → Save
□ Game handles rapid updates
□ No lag or stuttering
```

### Performance Testing

#### FPS Test
```
1. Set all settings to maximum difficulty
2. Start game and play for 2 minutes
□ FPS stays above 55 (green or normal)
□ No drops or stuttering

2. Set all settings to maximum ease
3. Play for 2 minutes
□ FPS stays at 60
□ Smooth gameplay
```

### Mobile/Touch Testing
```
1. On mobile device, navigate to settings
□ Settings screen is readable
□ Sliders work with touch
□ Buttons are tappable (not too small)

2. Rotate device between portrait/landscape
□ Settings layout adapts properly
□ Controls remain accessible
```

### Stress Testing

#### Extreme Settings Combinations
```
Test 1: Maximum Difficulty
- Gravity: 0.6, Jump Power: 9
- Platform Gap: 65-100
- Speed: 1.2x
- Save & Play
□ Game is playable but very hard
□ FPS stable at 55+

Test 2: Extreme Ease
- Gravity: 0.1, Jump Power: 14
- Platform Gap: 30-50
- Speed: 0.7x
- Save & Play
□ Game is very easy
□ Can score 500+ easily
□ No lag

Test 3: Mismatched Settings
- Gravity: 0.6 (hard)
- Jump Power: 14 (easy)
- Gap: 30-50 (easy)
- Speed: 0.7x (slow)
□ Contradictory settings don't crash
□ Game balances them sensibly
```

## Test Report Template

```
Date: __________
Tester: __________
Build: v1.0.45

TEST RESULTS
============

Basic Functionality:        PASS / FAIL
Preset Testing:            PASS / FAIL
Gameplay Integration:      PASS / FAIL
Persistence:              PASS / FAIL
Edge Cases:               PASS / FAIL
Performance:              PASS / FAIL
Mobile Testing:           PASS / FAIL
Stress Testing:           PASS / FAIL

Issues Found:
1. ________________
2. ________________

Notes:
________________
________________
```

## Debugging Tips

### Check Browser Console (F12)
```
Errors related to:
- validateSettings(): Check console for validation errors
- localStorage: Check if browser allows localStorage
- settings parse: JSON parsing errors indicate corrupt data
```

### Test localStorage directly (Browser Console)
```javascript
// Check if settings were saved
localStorage.getItem('gameSettings')

// Clear settings to reset
localStorage.removeItem('gameSettings')

// Check what's in currentSettings variable
console.log(currentSettings)
```

### Visual Debugging
```
If settings don't apply:
1. Check if loadSettings() is called in startGame()
2. Verify currentSettings has correct values
3. Check if applySettingsToGame() modifies DOM correctly
4. Review game loop uses currentSettings (not constants)
```

## Acceptance Criteria

✅ All 10 settings are functional and persistent
✅ Both presets work correctly
✅ Game gameplay changes based on settings
✅ Settings don't crash the game
✅ Character selection filters work
✅ Persistence survives browser close/reopen
✅ FPS stays above 55 with any settings combination
✅ Settings apply at game start (not during play)
✅ All controls are responsive on mobile
✅ No console errors in normal usage

---

**Testing Date**: April 5, 2026
**Version**: v1.0.45
**Status**: Ready for QA
