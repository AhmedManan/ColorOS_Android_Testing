## Test Suite: Smart Sidebar Configuration and Launch

| Test Case ID | Description | Pre-conditions | Test Steps | Expected Result | Status |
| :--- | :--- | :--- | :--- | :--- | :--- |
| **TC_SB_001** | Verify enabling/disabling Smart Sidebar from Settings. | Device is unlocked. | 1. Go to Settings > Special Features > Smart Sidebar.<br>2. Toggle the switch to ON.<br>3. Go to Home Screen.<br>4. Return and toggle the switch to OFF. | 1. When ON, a translucent indicator bar should appear on the edge of the screen.<br>2. When OFF, the indicator bar should disappear completely. | Pass |
| **TC_SB_002** | Verify pulling out the Smart Sidebar. | Smart Sidebar is enabled. | 1. Swipe inward from the translucent sidebar indicator. | The Smart Sidebar panel should slide out smoothly with haptic feedback, displaying app shortcuts and tools. | Pass |
| **TC_SB_003** | Verify customizing shortcuts in the Smart Sidebar. | Smart Sidebar is open. | 1. Scroll to the bottom of the sidebar and tap Edit (Plus icon).<br>2. Add a new app and remove an existing app.<br>3. Tap Done. | 1. The newly added app should appear in the sidebar.<br>2. The removed app should no longer be visible. | Pass |
