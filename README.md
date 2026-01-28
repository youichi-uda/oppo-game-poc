# OPPO Games WebView PoC

This is a Proof of Concept demonstrating a JavaScript Bridge exposure vulnerability in `com.oplus.games`.

## Live Demo

👉 **[Open PoC Page](https://youichi-uda.github.io/oppo-game-poc/?v=2)**

👉 **[Open CSRF Page](https://youichi-uda.github.io/oppo-game-poc/csrf_test.html?v=2)**

👉 **[Open e Page](https://youichi-uda.github.io/oppo-game-poc/e.html)**

👉 **[Open escalation Page](https://youichi-uda.github.io/oppo-game-poc/escalation.html?v=2)**

👉 **[Open escalation Page](https://youichi-uda.github.io/oppo-game-poc/escalation.html?v=3)**

👉 **[Open escalation2 Page](https://youichi-uda.github.io/oppo-game-poc/escalation2.html?v=2)**

## How to Test

1. On an OPPO device, trigger the vulnerable deep link:
   ```
   app://com.oplus.games/jump?url=game_space://games_lobby/tangram/game_play?url=https://google.com&appid=1337
   ```
2. In the opened WebView, search for this GitHub repository
3. Navigate to the PoC page above
4. Observe that JavaScript bridges are detected

## Vulnerability Details

- **Package**: `com.oplus.games`
- **Component**: `ExternalJumpActivity` → `GameOnlyPlayActivity`
- **Issue**: Arbitrary URL loading in privileged WebView with JS Bridge exposed
