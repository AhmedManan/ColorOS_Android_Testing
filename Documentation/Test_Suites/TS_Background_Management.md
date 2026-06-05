# Battery & Power Management

# Test Suite: Power Saving Mode

| Test Case ID | Description | Pre-conditions | Test Steps | Expected Result | Status |
| :--- | :--- | :--- | :--- | :--- | :--- |
| **TC_BPM_001** | Verify enabling Power Saving Mode manually. | Device battery is above 20%. | 1. Go to Settings > Battery.<br>2. Toggle Power Saving Mode to ON. | 1. The battery icon in the status bar must turn yellow.<br>2. Screen brightness should decrease slightly.<br>3. Auto-screen off time should drop to 15 seconds. | Pass |
| **TC_BPM_002** | Verify auto-turn off functionality of Power Saving Mode. | Power Saving Mode is ON. "Turn off when charged" is enabled. | 1. Connect the device to a charger.<br>2. Allow the battery to charge above the threshold (e.g., 60% or 90% depending on OS version). | Power Saving Mode must automatically toggle OFF, and the battery icon should return to its default color. | Pass |
| **TC_BPM_003** | Verify auto-turn on at a specified battery level. | Power Saving Mode is OFF. "Turn on at specified battery level" is set to 20%. | 1. Drain the device battery naturally or via a heavy benchmark app to reach 20%. | The system must prompt a warning and automatically enable Power Saving Mode exactly at the 20% mark. | Pass |

# Test Suite: Super Power Saving Mode
> **Note:** This mode heavily restricts background activities, limits CPU performance, and allows only a maximum of 6 apps on a dark home screen.

| Test Case ID | Description | Pre-conditions | Test Steps | Expected Result | Status |
| :--- | :--- | :--- | :--- | :--- | :--- |
| **TC_BPM_004** | Verify enabling Super Power Saving Mode. | Device is in normal operating mode. | 1. Go to Settings > Battery > Advanced/More Settings.<br>2. Toggle Super Power Saving Mode to ON.<br>3. Tap "Turn On" on the confirmation prompt. | The UI must transition to a simplified dark mode screen. Only Phone, Messages, Contacts, and up to 3 custom apps should be visible. System animations should be disabled. | Pass |
| **TC_BPM_005** | Verify adding and removing apps in Super Power Saving Mode. | Super Power Saving Mode is active. | 1. Tap the Add (+) icon on the simplified home screen.<br>2. Select an app (e.g., WhatsApp).<br>3. Long press the WhatsApp icon and select Remove. | 1. The selected app must be added to the allowed list and launch successfully.<br>2. The removed app must disappear from the screen, making the slot empty again. | Pass |
| **TC_BPM_006** | Verify system behavior for background notifications in Super Power Saving Mode. | Super Power Saving Mode is active. Wi-Fi/Mobile Data is ON. | 1. Send a test email or a third-party app notification (e.g., Telegram) from another device. | The notification must NOT be received in real-time unless the specific app is added to the allowed 6-app list, confirming background data restriction. | Pass |
| **TC_BPM_007** | Verify exiting Super Power Saving Mode. | Super Power Saving Mode is active. | 1. Tap the Exit icon (door icon) at the top left/right corner.<br>2. Confirm the exit prompt. | The device must smoothly transition back to the standard ColorOS Home Screen, restoring all UI elements, wallpapers, and background processes. | Pass |

# Test Suite: Advanced Battery Settings & Optimization

| Test Case ID | Description | Pre-conditions | Test Steps | Expected Result | Status |
| :--- | :--- | :--- | :--- | :--- | :--- |
| **TC_BPM_008** | Verify High Performance Mode functionality. | Device is normal. Battery is above 50%. | 1. Go to Settings > Battery > Advanced Settings.<br>2. Toggle High Performance Mode to ON. | A permanent notification/status bar icon must appear indicating the mode is active. CPU/GPU benchmarks should show higher scores, and power consumption should increase. | Pass |
| **TC_BPM_009** | Verify Optimized Night Charging (AI Battery Protection). | "Optimized Night Charging" is toggled ON. | 1. Plug the device into the charger late at night (e.g., 11:30 PM).<br>2. Monitor the charging graph via settings or adb logs over 8 hours. | The battery must charge to 80% and pause. It should intelligently resume and hit 100% just before the user's usual wake-up time (e.g., 6:00 AM). | Pass |
| **TC_BPM_010** | Verify App Battery Management (Background restrictions). | A third-party heavy app (e.g., Facebook) is installed. | 1. Go to Settings > Battery > App battery management.<br>2. Select Facebook.<br>3. Select Don't run in background.<br>4. Open Facebook, then go to the Home screen and wait 5 minutes. | The OS must forcefully kill the Facebook background process. No notifications from Facebook should arrive until the app is manually opened again. | Pass |
