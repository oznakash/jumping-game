# 🎉 Anniversary Run - 14 Years Together

A romantic, personalized HTML5 mobile game celebrating 14 years of love and adventure with Oz & Caroline.

## 📱 Features

### 🎮 Gameplay
- **Vertical Platformer**: Doodle Jump-style gameplay with anniversary theming
- **Randomized Characters**: Play as different emoji characters each game (🐄 🐰 🐵 👶 🤖)
- **Infinite Climbing**: Generate unlimited platforms as you reach higher scores
- **Smooth 60 FPS**: Optimized Canvas rendering with RequestAnimationFrame
- **Score Tracking**: Real-time score calculation based on height climbed
- **Anniversary Levels**: Progress through 14 anniversary levels (0-600+ points)

### 💕 Romantic Features
- **Romantic Tips**: 50 unique relationship advice messages displayed every 3 platforms
- **Activity Suggestions**: 100+ personalized anniversary activity suggestions based on score
- **Platform Labels**: Each platform shows activity types (dinner 🍽️, beach 🏖️, flight ✈️, etc.)
- **Anniversary Theming**: Celebrate 14 years together with themed UI and messaging

### 🎵 Audio System
- **Background Music**: Original 8-bar Mario-inspired celebratory melody in C Major
- **Music Looping**: Seamless loop during gameplay, stops on game over
- **Character Sounds**: Character-specific bounce sound effects (coming soon - currently in debug)
- **Web Audio API**: Procedural sound generation using oscillators

### 💾 Data Persistence
- **Best Score Tracking**: Saves highest score to localStorage
- **Leaderboard**: Top 5 scores with player names and activity suggestions
- **Automatic Saving**: All data persists across sessions

### 📱 Mobile Optimized
- **iOS Safari Support**: Full viewport fit and touch optimization
- **Responsive Design**: Works on any screen size
- **Touch Controls**: Left 35% of screen to move left, right 65% to move right
- **Keyboard Support**: Arrow keys for desktop testing (← →)
- **Retina Display Support**: Scales for high-DPI displays with devicePixelRatio

### 🔧 Production Ready
- **Error Handling**: Comprehensive try-catch and validation
- **Performance Monitoring**: Real-time FPS counter with low-FPS warnings
- **Debug Console**: Detailed logging for troubleshooting
- **Canvas Validation**: Prevents crashes from missing render contexts

## 🎮 How to Play

1. **Start**: Tap "Start Game" button
2. **Move**: Tap left side (left 35%) or right side (right 65%) of screen to move
3. **Jump**: Automatically jump when landing on platforms
4. **Climb**: Keep jumping to climb higher and increase your score
5. **Score**: Earn 20 points per pixel climbed
6. **Levels**: Reach milestone scores for anniversary levels (50, 100, 150... up to 14 years)
7. **Game Over**: Fall too far without landing on a platform
8. **Leaderboard**: Save your score and view top 5 scores

## 🏆 Scoring

- **Score to Points Ratio**: 1 point = 20 pixels climbed
- **Anniversary Level**: Every 50 points = 1 anniversary level (max 14)
- **High Score Example**: 
  - 50 points = Anniversary 1 🎁
  - 100 points = Anniversary 2 🎁
  - 600+ points = Anniversary 12+ 🎁

## 🎨 Technical Stack

### Core Technologies
- **HTML5 Canvas**: 2D rendering at 60 FPS
- **Web Audio API**: Procedural music and sound effects
- **localStorage**: Data persistence for scores and leaderboard
- **Responsive Design**: CSS media queries and viewport optimization
- **Touch & Keyboard**: Input handling for mobile and desktop

### Key Systems

#### Game Loop
```javascript
requestAnimationFrame(gameLoop)
- Updates player position and velocity
- Detects platform collisions
- Spawns new platforms dynamically
- Updates camera position
- Renders game state
- Monitors FPS performance
```

#### Platform Generation
- Spawns 25 screen heights ahead of camera
- 50-80 pixel gaps between platforms (randomized)
- Dynamic distribution across screen width
- Automatic cleanup of off-screen platforms
- Guaranteed starting platform to prevent instant death

#### Coordinate System
- Y increases downward (standard canvas)
- Player starts at 40% screen height
- Negative Y values above screen
- Camera follows player at 30% down screen
- Score based on maximum Y descent

#### Physics
- Gravity: 0.3 pixels/frame²
- Jump Power: -11 pixels/frame (upward)
- Collision Detection: Rectangle-based with 15px tolerance
- Falling Threshold: 1/3 screen height below last jump

## 🐛 Known Issues & Debug Tips

### Bounce Sound Effect (In Progress)
- Test sound plays 300ms after game start
- Open DevTools (F12) to check console for:
  - `"Playing test bounce sound for character: 🐄"`
  - `"Platform collision detected!"`
  - `"Bounce sound played"`
- This helps identify if issue is collision detection or audio

### Performance Monitoring
- FPS counter displayed in top-left corner
- Turns red if FPS drops below 55
- Console warns about low FPS
- Target: 60 FPS for smooth gameplay

## 📊 Game Statistics

- **Version**: v1.0.42 (Production Ready)
- **Canvas Resolution**: Full viewport with devicePixelRatio scaling
- **Target FPS**: 60 (60 FPS refresh rate)
- **Platform Spawn Range**: 25 screen heights ahead
- **Maximum Active Platforms**: ~100 on screen
- **Audio Channels**: 2 (music + effects)
- **Leaderboard Size**: Top 5 scores
- **Romantic Tips**: 50 unique messages
- **Activity Suggestions**: 100+ personalized activities
- **Character Selection**: 5 emoji characters

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
2. Enter URL: `http://[your-computer-ip]:8000` or `http://localhost:8000`
3. For full-screen experience: Add to Home Screen (Share → Add to Home Screen)
4. Game will run in full-screen app mode

### Desktop Testing
- Use arrow keys (← →) to move left/right
- Game works in Chrome, Firefox, Safari, Edge
- Open DevTools (F12/Cmd+Option+I) for debugging

## 🔧 Configuration

### Game Constants (in HTML)
```javascript
const GRAVITY = 0.3;                          // Gravity strength
const JUMP_POWER = 11;                        // Jump velocity
const PLAYER_W = 24, PLAYER_H = 32;          // Player dimensions
const PLATFORM_W = 50, PLATFORM_H = 10;      // Platform dimensions
const PLATFORM_GAP_MIN = 50;                 // Min distance between platforms
const PLATFORM_GAP_MAX = 80;                 // Max distance between platforms
const LEVEL_POINTS = 50;                     // Points per level
const MAX_LEVEL = 14;                        // Maximum anniversary level
const FALLING_DISTANCE_MULTIPLIER = 1/3;     // Game over threshold
```

### Customization
- **Colors**: Modify gradient colors in `drawGame()` function
- **Music**: Edit melody array in `playGameMusic()` function
- **Tips**: Add to `ROMANTIC_TIPS` array (50 messages)
- **Activities**: Add to `ANNIVERSARY_ACTIVITIES` array (100+ suggestions)
- **Characters**: Modify `CHARACTERS` array emoji
- **Platform Items**: Modify `PLATFORM_ITEMS` array

## 📈 Development History

### v1.0.42 - Production Ready (Latest)
- ✅ Fixed score calculation for 40% spawn height
- ✅ Added comprehensive error handling to gameLoop
- ✅ Added canvas context validation
- ✅ Implemented FPS monitoring and performance warnings
- ✅ Added collision detection logging for debugging
- ✅ Improved test bounce sound timing (300ms timeout)

### v1.0.41
- ✅ Replaced prayer tip with relationship advice

### v1.0.40
- ✅ Fixed audio context check in playBounceSound()
- ✅ Added collision detection logging

### v1.0.39
- ✅ Fixed critical platform filter range bug (major fix)
- ✅ Platform filter now matches spawn distance

### v1.0.38
- ✅ Increased platform spawn distance from 15 to 25 screen heights
- ✅ Fixed platform generation at high scores (410+)

### Earlier Versions
- ✅ Character randomization with emoji
- ✅ Emoji rendering (36px, 50% larger)
- ✅ Romantic tips system (every 3 platforms)
- ✅ Anniversary activity suggestions
- ✅ Platform label system
- ✅ Music system with Web Audio API
- ✅ Mobile-optimized touch controls
- ✅ Leaderboard with localStorage persistence
- ✅ 60 FPS smooth gameplay

## 🧪 QA Testing Checklist

- [x] Player spawn at 40% height
- [x] Platform generation at low scores (0-100)
- [x] Platform generation at medium scores (100-400)
- [x] Platform generation at high scores (400-600+)
- [x] Score calculation accuracy
- [x] Level progression (1-14)
- [x] Game over on fall
- [x] Music plays and loops
- [x] Music stops on game over
- [x] Leaderboard saves/loads
- [x] Best score persistence
- [x] Character randomization
- [x] Touch input (left/right)
- [x] Keyboard input (arrow keys)
- [x] FPS monitoring
- [x] Error handling
- [x] No crashes on edge cases
- [ ] Bounce sound effect audible (in progress)

## 💡 Tips for Best Experience

1. **Mobile**: Use iOS Safari or Chrome on mobile for best experience
2. **Sound**: Ensure device volume is on and not muted
3. **Screen**: Full-screen for better gameplay
4. **Network**: Game requires no network after loading
5. **Privacy**: All data stored locally on device (no cloud sync)

## 🎁 Dedication

> This game celebrates 14 years of love, adventure, and countless memories together. Here's to 14 more years and beyond! 💕
>
> *For Caroline & Oz - Happy Anniversary!*

## 📝 License

This game is a personal project created as an anniversary gift. Feel free to modify and personalize for your own celebration! 🎉

## 🤝 Support

For issues or improvements:
1. Check the console (F12) for error messages
2. Review the FPS counter for performance issues
3. Look for debug logs about platform generation and collisions
4. Test in a fresh browser session (clear cache)

---

**Made with ❤️ for an Anniversary Celebration**

Version 1.0.42 - Production Ready