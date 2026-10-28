# YouTube Speed Remote

Android app for controlling YouTube playback speed on a Samsung TV by sending local-network Samsung remote commands.

## What works

- Save a Samsung TV IP address.
- Pair with the TV over the local Samsung remote WebSocket endpoint.
- Launch the Samsung YouTube app.
- Send manual remote keys.
- Run editable speed macros for `0.5x`, `0.75x`, `1x`, `1.25x`, `1.5x`, and `2x`.

## Limitation

Samsung's TV remote protocol can send remote key presses, but it cannot directly call YouTube's internal `set playback speed` action. The speed buttons are therefore macros. They work only if the YouTube app on the TV exposes a Speed menu and the configured key sequence matches the current YouTube TV UI.

## First Run

1. Open the project in Android Studio.
2. Build and install the `app` module on an Android phone connected to the same Wi-Fi as the TV.
3. Enter the TV IP address.
4. Tap `Pair`.
5. Accept the permission prompt shown on the Samsung TV.
6. Tap `Pair` again if the token was not captured on the first attempt.
7. Tap `YouTube`.
8. Play a video, then test a speed button.

## Macro Editing

Tap the settings icon beside a speed and edit its comma-separated Samsung key sequence.

Common keys:

- `KEY_UP`
- `KEY_DOWN`
- `KEY_LEFT`
- `KEY_RIGHT`
- `KEY_ENTER`
- `KEY_RETURN`
- `KEY_HOME`
- `KEY_TOOLS`
- `KEY_PLAY`
- `KEY_PAUSE`

The default macros are only a starting point. Use the manual remote pad to find the exact route through your TV's YouTube controls, then save that route as a macro.

## Build Notes

This is a normal Gradle Android project:

```bash
./gradlew :app:assembleDebug
```

This workspace does not include a Gradle wrapper. Android Studio can generate one, or you can run the build with a local Gradle installation compatible with Android Gradle Plugin `8.7.3`.
# remote
