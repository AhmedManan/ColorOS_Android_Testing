## Test Suite: Initial Setup and Authentication

| Test Case ID | Description | Pre-conditions | Test Steps | Expected Result | Status |
| :--- | :--- | :--- | :--- | :--- | :--- |
| **TC_PS_001** | Verify first-time setup of Private Safe. | No prior privacy password is set on the device. | 1. Go to Settings > Privacy > Privacy tab > Private Safe.<br>2. Attempt to toggle or open it.<br>3. Follow prompts to set up a 6-digit Privacy Password and a security question. | 1. The system must prompt for a dedicated Privacy Password.<br>2. It must successfully register the password and recovery questions. | Pass |
| **TC_PS_002** | Verify authentication via Biometrics (Fingerprint/Face Unlock). | Private Safe is configured. Biometrics are registered on the device. | 1. Navigate to Private Safe settings.<br>2. Enable "Fingerprint" or "Face Unlock" for Private Safe.<br>3. Close settings, reopen Private Safe, and authenticate using your fingerprint. | 1. The toggle for biometric link should save properly.<br>2. Private Safe should unlock immediately upon successful biometric read. | Pass |


## Test Suite: File Operations (Moving In and Out)

| Test Case ID | Description | Pre-conditions | Test Steps | Expected Result | Status |
| :--- | :--- | :--- | :--- | :--- | :--- |
| **TC_PS_003** | Verify moving a photo from the Photos/Gallery app into Private Safe. | A media file exists in the native Photos app. Private Safe is active. | 1. Open the native Photos app.<br>2. Long-press an image.<br>3. Tap the Set as private icon on the bottom action bar. | 1. The image should instantly disappear from the public gallery view.<br>2. A confirmation toast message ("Setting as Private...") should appear briefly. | Pass |
| **TC_PS_004** | Verify accessing and viewing hidden files inside Private Safe. | Files have been successfully moved into Private Safe. | 1. Access Private Safe via Settings or by long-pressing the Photos app top tab.<br>2. Authenticate.<br>3. Tap on the Images and videos directory. | The previously hidden photo must render correctly and securely within the Private Safe interface. | Pass |
| **TC_PS_005** | Verify restoring (moving out) a file from Private Safe back to public storage. | Files exist inside Private Safe. | 1. Open Private Safe > Images and videos.<br>2. Select the file and tap Set as public.<br>3. Choose a target directory folder (e.g., Camera or Pictures). | 1. The file must disappear from Private Safe.<br>2. The file must reappear intact in the chosen public folder. | Pass |

## Test Suite: Security & Negative Scenarios (Edge Cases)

| Test Case ID | Description | Pre-conditions | Test Steps | Expected Result | Status |
| :--- | :--- | :--- | :--- | :--- | :--- |
| **TC_PS_006** | Verify system behavior when attempting to take a screenshot inside Private Safe. | User is inside an active, unlocked Private Safe directory. | 1. Trigger a screenshot using the 3-finger swipe gesture or Power + Volume Down keys. | ColorOS must block the action. A system toast notification should display: "Can't take screenshots due to security policy" or generate a completely black screenshot file. | Pass |
| **TC_PS_007** | Verify screen recording behavior inside Private Safe. | Screen recording is turned on from the Quick Settings toggle. | 1. Start a screen recording session.<br>2. Navigate into Private Safe and authenticate. | The recorded video file must capture a completely black screen for the entire duration the user stays inside Private Safe. | Pass |
| **TC_PS_008** | Verify auto-lock behavior when the app is minimized or backgrounded. | Private Safe is currently unlocked and open. | 1. Press the Home button or use gestures to go to the Home screen.<br>2. Immediately tap the Recents key to bring Private Safe back to focus. | Private Safe must auto-lock instantly upon being backgrounded. It must demand re-authentication before displaying any files. | Pass |
| **TC_PS_009** | Verify data integrity during an OTA (Over-The-Air) ColorOS update. | Files are present inside Private Safe. | 1. Perform a system software update via Settings > About Device > Software Update.<br>2. Wait for the phone to reboot.<br>3. Open Private Safe. | All encrypted files must remain intact, undamaged, and accessible with the original privacy password. | Pass |