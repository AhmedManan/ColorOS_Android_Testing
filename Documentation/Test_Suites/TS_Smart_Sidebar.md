## Test Suite: Smart Sidebar Configuration and Launch

| Test Case ID | Description | Pre-conditions | Test Steps | Expected Result | Status |
| :--- | :--- | :--- | :--- | :--- | :--- |
| **TC_SB_001** | Verify enabling/disabling Smart Sidebar from Settings. | Device is unlocked. | 1. Go to Settings > Special Features > Smart Sidebar.<br>2. Toggle the switch to ON.<br>3. Go to Home Screen.<br>4. Return and toggle the switch to OFF. | 1. When ON, a translucent indicator bar should appear on the edge of the screen.<br>2. When OFF, the indicator bar should disappear completely. | Pass |
| **TC_SB_002** | Verify pulling out the Smart Sidebar. | Smart Sidebar is enabled. | 1. Swipe inward from the translucent sidebar indicator. | The Smart Sidebar panel should slide out smoothly with haptic feedback, displaying app shortcuts and tools. | Pass |
| **TC_SB_003** | Verify customizing shortcuts in the Smart Sidebar. | Smart Sidebar is open. | 1. Scroll to the bottom of the sidebar and tap Edit (Plus icon).<br>2. Add a new app and remove an existing app.<br>3. Tap Done. | 1. The newly added app should appear in the sidebar.<br>2. The removed app should no longer be visible. | Pass |


## Test Suite: Floating Windows (Flexible Windows) Interaction

| Test Case ID | Description | Pre-conditions | Test Steps | Expected Result | Status |
| :--- | :--- | :--- | :--- | :--- | :--- |
| **TC_FW_004** | Verify opening an app in a Floating Window from the Smart Sidebar. | Smart Sidebar is enabled and populated with apps (e.g., Calculator). | 1. Swipe to open the Smart Sidebar.<br>2. Tap on the Calculator app icon. | The Calculator app should open in a smaller, floating window on top of the current screen/home screen. | Pass |
| **TC_FW_005** | Verify moving/repositioning the Floating Window. | An app is running in a floating window. | 1. Tap and hold the top bar/handle of the floating window.<br>2. Drag it to different areas of the screen. | The window should move smoothly following the finger drag and snap safely within screen boundaries. | Pass |
| **TC_FW_006** | Verify resizing the Floating Window. | An app is running in a floating window. | 1. Drag inward or outward from the bottom-left or bottom-right corners of the floating window. | The window should resize dynamically according to the drag direction. | Pass |
| **TC_FW_007** | Verify minimizing the Floating Window to the screen edge. | An app is running in a floating window. | 1. Drag the floating window completely to the left or right edge of the screen. | The window should shrink into a small, floating icon/tab attached to the screen edge. | Pass |
| **TC_FW_008** | Verify maximizing the Floating Window to full screen. | An app is running in a floating window. | 1. Double-tap the top handle of the floating window OR tap the maximize icon. | The app should smoothly transition into standard full-screen mode. | Pass |
| **TC_FW_009** | Verify closing the Floating Window. | An app is running in a floating window. | 1. Tap the X (Close) icon on the top control bar of the window. | The floating window should close immediately, destroying the background process if applicable. | Pass |


## Test Suite: Boundary & Negative Scenarios (Edge Cases)

| Test Case ID | Description | Pre-conditions | Test Steps | Expected Result | Status |
| :--- | :--- | :--- | :--- | :--- | :--- |
| **TC_FW_010** | Verify Floating Window behavior during screen rotation. | Auto-rotate is enabled. An app is running in a floating window. | 1. Rotate the physical device from Portrait to Landscape mode. | The floating window should adjust its proportions and position to fit the landscape layout without crashing. | Pass |
| **TC_FW_011** | Verify opening an unsupported app in a floating window. | An app that does not support multi-window (e.g., certain heavy games or banking apps) is in the sidebar. | 1. Attempt to open the unsupported app from the Smart Sidebar. | ColorOS should display a toast message: "This app does not support floating windows" and open it in full screen instead. | Pass |
| **TC_FW_012** | Verify Floating Window behavior when a phone call is received. | An app is active in a floating window. | 1. Trigger an incoming voice/video call to the device. | The incoming call UI should take priority. The floating window should stay paused in the background or minimize to the edge cleanly. | Pass |
