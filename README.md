# 🎉 Anniversary Run - 14 Years Together

A romantic, personalized HTML5 mobile game celebrating 14 years of love and adventure with Oz & Caroline. Climb platforms, earn points, unlock activities, and enjoy customizable gameplay settings.

**Current Version: v1.0.47** 🚀

---

## 📱 Core Features

### 🎮 Gameplay
- **Vertical Platformer**: Doodle Jump-style gameplay with anniversary theming
- **Progressive Difficulty**: Game gets 10% harder every 150 points (more gaps, faster speed, fewer power-ups)
- **Randomized Characters**: Play as different emoji characters (🐄 🐰 🐵 👶 🤖 🦄)
- **Infinite Climbing**: Generate unlimited platforms as you reach higher scores
- **Smooth 60 FPS**: Optimized Canvas rendering with RequestAnimationFrame
- **Real-time Score**: Calculated based on height climbed
- **Anniversary Levels**: Progress through 14 levels (every 50 points = 1 year)

### 💕 Romantic Features
- **Romantic Tips**: 50+ relationship advice messages displayed dynamically
- **Activity Suggestions**: 88 personalized anniversary activities based on score bracket
- **Platform Labels**: Each platform shows activity emoji (dinner 🍽️, beach 🏖️, etc.)
- **Anniversary Theming**: Celebrate 14 years together with themed UI and messaging

### ⏱️ Game Tracking
- **Stopwatch Timer**: Displays MM:SS format in top-right corner
  - Starts at 00:00 when game begins
  - Updates every frame during gameplay
  - Stops when reaching Level 14 (14 years milestone)
  - Resets on new game
- **Leaderboard**: Track top 5 scores with player names

### 🎮 Moving Platforms
- **Dynamic Platforms**: 10% of platforms move horizontally (configurable 0-100%)
- **Visual Indicators**: Moving platforms shown in blue with direction arrow (→ ←)
- **Player Movement**: Player moves with platform when standing on it
- **Progressive Scaling**: More platforms move as difficulty increases
- **Smooth Animation**: Platforms oscillate within 60-100 pixel ranges

### ⚡ Power-Up System
- **6 Power-Up Types**: Shield, Rocket, Score 2x, Love Bomb, Sound Boost, Bomb
- **Dynamic Spawning**: Configurable spawn rate (19% default)
- **Visual Feedback**: Emoji indicators for each power-up type
- **Effects System**:
  - 🛡️ **Shield**: One free jump without losing momentum
  - 🚀 **Rocket**: 50% increased jump height for 3 jumps
  - 💎 **Score 2x**: Doubles points for 300 points
  - 💕 **Love Bomb**: Score boost effect
  - 🎵 **Sound Boost**: Audio enhancement
  - 💣 **Bomb**: Reduces score (min 0 points)

### 🎵 Audio System
- **Background Music**: Celebratory 8-bar melody in C Major
- **Music Looping**: Seamless loop during gameplay, stops on game over
- **Sound Effects**: Bounce sounds on platform collision
- **Web Audio API**: Procedural sound generation using oscillators
- **Configurable Volume**: Adjust sound effects volume (0-100%)

### ⚙️ Settings System
- **10 Configurable Settings** organized in 4 categories:
  
  **🎮 Gameplay** (Not affected by gravity constraint)
  - Gravity Strength (0.1-0.6)
  - Jump Power (8-14)
  - Platform Gap Size (min/max ranges)
  - Game Speed Multiplier (0.7-1.5x)
  - Moving Platform Rate (0-100%)

  **💎 Power-Ups**
  - Power-Up Spawn Rate (8-35%)

  **🎵 Audio & Visual**
  - Sound Effects Volume (0-100%)
  - Visual Theme (Dark/Light)

  **💕 Experience & Content**
  - Playable Characters (6-character multi-select)
  - Romantic Tips Style (5 tone options: Affectionate, Playful, Thoughtful, Adventurous, Mixed)
  - Hint Frequency (2-8 platforms)

- **2 Presets**:
  - **Reset**: Returns to default settings
  - **Difficult Mode**: 15% moving platforms, tighter gaps, lower jump power
- **Settings Persistence**: All settings save to localStorage
- **Settings Access**: Available from leaderboard screen

### 💾 Data Persistence
- **Best Score Tracking**: Saves highest score to localStorage
- **Settings Storage**: All game settings persist across sessions
- **Leaderboard**: Top 5 scores with player names and activity suggestions
- **Automatic Saving**: All data saves automatically

### 📱 Mobile Optimized
- **iOS Safari Support**: Full viewport fit and touch optimization
- **Responsive Design**: Works on any screen size
- **Touch Controls**: Left 35% of screen to move left, right 65% to move right
- **Keyboard Support**: Arrow keys for desktop testing (← →)
- **Retina Display Support**: Scales for high-DPI displays

---

## 🎮 How to Play

1. **Start**: Tap "Start Game" button from start screen
2. **Access Settings**: From leaderboard, click "⚙️ Settings" to customize gameplay
3. **Move**: Tap left (left 35%) or right (right 65%) of screen to move
4. **Jump**: Automatically jump when landing on platforms
5. **Climb**: Keep jumping to increase score and progress through levels
6. **Score**: Earn points based on height climbed
7. **Watch Timer**: Top-right stopwatch shows elapsed time (stops at Level 14)
8. **Collect Power-Ups**: Jump on special emoji to collect power-ups
9. **Game Over**: Fall too far below last platform
10. **Save Score**: Enter name to save high score to leaderboard

---

## 🏆 Scoring & Progression

### Score Brackets
- **0-100 points**: Free & local activities
- **100-200 points**: Casual dining & local experiences
- **200-300 points**: Fine dining experiences
- **300-400 points**: Domestic travel (Vegas, New Orleans, etc.)
- **400-500 points**: Beach getaways (Hawaii, Cancun, etc.)
- **500-600 points**: International luxury (Iceland, Japan, Egypt)
- **600-700 points**: Premium destinations (Caribbean, Maldives)
- **700-800 points**: Ultra-luxury (Swiss Alps, Antarctica)
- **800-900 points**: Exclusive experiences (Private villas, yacht charters)
- **900-950 points**: Ultra-premium (Private jets, cruise ships)
- **950+ points**: Ultimate luxury dreams

### Anniversary Levels
- Every 50 points = 1 anniversary level (max 14)
- Milestone celebrations at each level
- 14 years = 700 points milestone

### Difficulty Progression
- Game automatically gets 10% harder every 150 points
- **0-149 points**: Base difficulty
- **150-299 points**: 10% harder (larger gaps, faster speed)
- **300-449 points**: 20% harder
- **450+ points**: Continues scaling by 10% per 150 points

### What Scales with Difficulty
✅ Platform gaps (increase = harder jumps)
✅ Game speed (increase = faster gameplay)
✅ Moving platform rate (increase = more moving platforms)
✅ Jump power (decrease = harder to reach platforms)
✅ Power-up frequency (decrease = fewer boosts)

**What Stays Constant**:
❌ Gravity (NOT affected as requested)

---

## 🎨 Technical Stack

### Core Technologies
- **HTML5 Canvas**: 2D rendering at 60 FPS
- **Web Audio API**: Procedural music and sound effects
- **localStorage**: Data persistence for scores, leaderboard, and settings
- **Responsive CSS**: Media queries and viewport optimization
- **Touch & Keyboard**: Input handling for mobile and desktop

### Game Systems

#### Game Loop
- Updates player position and velocity
- Detects platform collisions with moving platform support
- Spawns new platforms dynamically with progressive difficulty
- Updates moving platforms each frame
- Updates stopwatch timer
- Renders game state with visual indicators
- Monitors FPS performance

#### Platform Generation
- Spawns 25 screen heights ahead of camera
- Dynamic gap sizing based on difficulty (affected by progressive scaling)
- Dynamic distribution across screen width
- 10% of platforms marked as moving (configurable)
- Automatic cleanup of off-screen platforms
- Guaranteed starting platform

#### Collision Detection
- Rectangle-based with 15px tolerance
- Moving platform detection: Player moves with platform
- Power-up collision detection with deduplication flags
- Multiple collision type handling (static and moving platforms)

#### Physics (Configurable)
- **Gravity**: 0.3 pixels/frame² (default, not affected by difficulty)
- **Jump Power**: 11 pixels/frame (default, scales with difficulty)
- **Game Speed Multiplier**: 1.0x (default, scales with difficulty)
- **Collision Detection**: Rectangle-based
- **Falling Threshold**: 1/3 screen height below last jump

---

## ✨ Power-Up Details

### Shield (🛡️)
- **Effect**: One free jump without penalty
- **Duration**: Single collision
- **Strategy**: Safe way to recover from bad positioning

### Rocket (🚀)
- **Effect**: 50% increased jump height for 3 jumps
- **Duration**: 3 platform jumps
- **Strategy**: Reach otherwise impossible platforms

### Score 2x (💎)
- **Effect**: Doubles all points earned for 300 points worth of climbing
- **Duration**: Until 300 points are earned at 2x rate
- **Strategy**: Maximize score during calm sections

### Love Bomb (💕)
- **Effect**: Instant score boost
- **Duration**: One-time
- **Strategy**: Quick points when needed

### Sound Boost (🎵)
- **Effect**: Enhanced audio feedback
- **Duration**: Gameplay session
- **Strategy**: Auditory satisfaction

### Bomb (💣)
- **Effect**: Reduces score by up to 50 points (min 0)
- **Duration**: Immediate
- **Strategy**: Avoid! Risk vs. reward element

---

## 📊 Game Statistics

| Metric | Value |
|--------|-------|
| **Version** | v1.0.47 |
| **Canvas FPS Target** | 60 FPS |
| **Platform Spawn Range** | 25 screen heights |
| **Max Active Platforms** | ~100+ |
| **Moving Platforms** | 0-100% (configurable) |
| **Power-Up Types** | 6 types |
| **Leaderboard Size** | Top 5 scores |
| **Romantic Tips** | 50+ messages |
| **Activity Suggestions** | 88 personalized activities |
| **Playable Characters** | 6 emoji (🐄🐰🐵👶🤖🦄) |
| **Settings Groups** | 4 categories, 10 total settings |
| **Difficulty Levels** | Dynamic (1.0x - 3.0x+) |

---

## 🚀 Installation & Usage

### Browser
Simply open `index.html` in a modern web browser:
```bash
# Open in default browser
open index.html

# Or use a local server (recommended for iOS testing)
python -m http.server 8000
# Then visit: http://localhost:8000
```

### iOS Safari
1. Open Safari on iPhone/iPad
2. Enter URL: `http://[your-computer-ip]:8000`
3. For full-screen: Share → Add to Home Screen
4. Game runs in full-screen app mode

### Desktop Testing
- Use arrow keys (← →) to move left/right
- Works in Chrome, Firefox, Safari, Edge
- Open DevTools (F12/Cmd+Option+I) for debugging

---

## 🔧 Configuration

### Game Settings (via Settings Screen)
All major gameplay parameters are configurable through the in-game settings screen accessible from the leaderboard. No code editing needed!

**Gameplay Settings**:
```
Gravity Strength: 0.1 - 0.6 (default: 0.3)
Jump Power: 8 - 14 (default: 11)
Platform Gaps: Min 30-70, Max 70-120 (default: 50-80)
Game Speed: 0.7x - 1.5x (default: 1.0x)
Moving Platforms: 0% - 100% (default: 10%)
```

**Customization via Code** (in index.html):
- **Colors**: Modify gradient in `drawGame()` function
- **Music**: Edit melody array in `playGameMusic()`
- **Romantic Tips**: Add to `ROMANTIC_TIPS` array
- **Activities**: Modify `ANNIVERSARY_ACTIVITIES` array
- **Characters**: Edit `CHARACTERS` array
- **Platform Items**: Update `PLATFORM_ITEMS` array

---

## 📈 Development History

### v1.0.47 - Activity Variety & Difficulty Scaling (Latest)
- ✅ Redesigned activity recommendations for better variety
  - 11 score brackets with 8+ unique activities each
  - No more French Riviera repetition
  - Clear progression from local → international → luxury
- ✅ Added progressive difficulty scaling
  - Game gets 10% harder every 150 points
  - Scales platform gaps, speed, jump power, moving platforms, power-ups
  - Gravity remains constant (user request)

### v1.0.46 - Moving Platforms & Stopwatch
- ✅ Added moving platform system
  - 0-100% configurable rate
  - Visual indicators with direction arrows
  - Player moves with platform when standing on it
- ✅ Added stopwatch timer
  - Displays MM:SS format
  - Starts at game begin
  - Stops at Level 14
  - Resets on new game

### v1.0.45 - Settings System
- ✅ Complete settings page with 10 configurable options
  - 4 categories: Gameplay, Power-Ups, Audio & Visual, Experience
  - 2 presets: Reset to Default, Difficult Mode
  - Settings persistence via localStorage
  - Settings accessible from leaderboard

### v1.0.44 - Bomb Power-Up
- ✅ Added Bomb power-up (💣)
  - Reduces score by up to 50 points
  - Minimum score capped at 0
  - Risk vs. reward element

### v1.0.43 - Power-Up System
- ✅ Complete 6-type power-up system
  - Shield, Rocket, Score 2x, Love Bomb, Sound Boost, Bomb
  - Visual feedback and emoji indicators
  - Effect lifecycle management
  - 19% spawn rate

### v1.0.42 - Production Ready
- ✅ Fixed score calculation
- ✅ Comprehensive error handling
- ✅ FPS monitoring and performance warnings
- ✅ Canvas context validation

### Earlier Versions
- ✅ Character randomization with emoji
- ✅ Romantic tips system
- ✅ Activity suggestions
- ✅ Platform label system
- ✅ Music system
- ✅ Mobile-optimized touch
- ✅ Leaderboard with persistence

---

## 🧪 QA Testing Checklist

### Core Gameplay
- [x] Player spawn at 40% height
- [x] Platform generation at all score ranges
- [x] Score calculation accuracy
- [x] Level progression (1-14)
- [x] Game over on fall
- [x] Character randomization

### Settings System
- [x] All 10 settings functional
- [x] Settings persistence
- [x] Both presets work
- [x] Settings apply to new game
- [x] Settings accessible from leaderboard

### Moving Platforms
- [x] Platform movement physics
- [x] Player moves with platform
- [x] Visual indicators correct
- [x] Rate scaling with difficulty

### Power-Ups
- [x] All 6 types spawn correctly
- [x] Collision detection works
- [x] Effects apply properly
- [x] Spawn rate configurable

### Audio & Visuals
- [x] Music plays and loops
- [x] Music stops on game over
- [x] Sound effects volume controllable
- [x] Theme switching works

### Stopwatch
- [x] Timer starts at 00:00
- [x] Updates every frame
- [x] Stops at Level 14
- [x] Resets on new game

### Difficulty Scaling
- [x] Gaps increase properly
- [x] Speed increases properly
- [x] Jump power decreases
- [x] Moving platform rate increases
- [x] Gravity unchanged
- [x] No impossible jumps

### Mobile & Desktop
- [x] Touch controls work
- [x] Keyboard controls work
- [x] Responsive design
- [x] FPS maintained 55+
- [x] No crashes on edge cases

---

## 💡 Tips for Best Experience

1. **Mobile**: Use iOS Safari or Chrome on mobile
2. **Sound**: Ensure device volume is on
3. **Settings**: Customize difficulty to your preference
4. **Presets**: Try "Difficult Mode" for extra challenge
5. **Power-Ups**: Collect strategically for maximum benefit
6. **Timer**: Watch stopwatch to see your attempt duration
7. **Activities**: Check recommendations for great date ideas

---

## 🎁 Dedication

> This game celebrates 14 years of love, adventure, and countless memories together. Here's to 14 more years and beyond! 💕
>
> *For Caroline & Oz - Happy Anniversary!*

---

## 📝 License

This game is a personal project created as an anniversary gift. Feel free to modify and personalize for your own celebration! 🎉

---

## 🤝 Support

For issues or improvements:
1. Check browser console (F12) for errors
2. Review FPS counter (top-left) for performance
3. Test with cache cleared
4. Try different settings configuration
5. Verify mobile platform permissions

---

**Made with ❤️ for an Anniversary Celebration**

*Version 1.0.47 - Feature Complete & Fully Customizable*
