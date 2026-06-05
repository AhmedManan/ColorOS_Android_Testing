# System Cloner (Dual System Space)

## Test Suite: Creation and Switching

| Test Case ID | Description | Pre-conditions | Test Steps | Expected Result | Status |
| :--- | :--- | :--- | :--- | :--- | :--- |
| **TC_SC_001** | Verify the creation of a System Clone. | Device has enough storage (minimum 2GB free). | 1. Go to Settings > Privacy > System Cloner.<br>2. Tap Get Started.<br>3. Set a unique Lock Screen Password (different from the Main System).<br>4. (Optional) Assign a specific fingerprint for the clone. | The system must successfully generate a secondary space and boot into a fresh ColorOS home screen layout. | Pass |
| **TC_SC_002** | Verify switching systems from the Lock Screen using Passwords. | System Clone is active with Password 'B'. Main System has Password 'A'. Phone is locked. | 1. Wake the screen.<br>2. Enter Password 'B'.<br>3. Lock the phone again.<br>4. Wake the screen and enter Password 'A'. | 1. Entering 'B' must boot directly into the Clone System.<br>2. Entering 'A' must boot directly into the Main System. | Pass |
| **TC_SC_003** | Verify switching systems using assigned Fingerprints. | Right Thumb is mapped to Main System. Left Thumb is mapped to Clone System. | 1. Lock the device screen.<br>2. Scan the Left Thumb on the fingerprint sensor. | The device must unlock and seamlessly transition into the Clone System without asking for a PIN. | Pass |

## Test Suite: Data Isolation & Edge Cases

| Test Case ID | Description | Pre-conditions | Test Steps | Expected Result | Status |
| :--- | :--- | :--- | :--- | :--- | :--- |
| **TC_SC_004** | Verify data isolation between Main and Clone systems. | A photo is captured and saved in the Main System. | 1. Switch to the Clone System.<br>2. Open the Photos/Gallery app.<br>3. Open the File Manager. | The photo captured in the Main System must NOT be visible or accessible anywhere in the Clone System. | Pass |
| **TC_SC_005** | Verify incoming call behavior when active in the Clone System. | User is currently using the Clone System. | 1. Receive an incoming call from an external number. | The call screen must appear normally, allowing the user to answer or reject the call, regardless of the active space. | Pass |
| **TC_SC_006** | Verify the deletion of the System Clone. | User is in the Main System. System Clone exists. | 1. Go to Settings > Privacy > System Cloner.<br>2. Tap Delete System Clone.<br>3. Authenticate with the Main System password. | The Clone System and all its associated data must be permanently erased. Storage space should be freed up. | Pass |

# App Cloner (Dual Apps)

## Test Suite: Creation and Execution

| Test Case ID | Description | Pre-conditions | Test Steps | Expected Result | Status |
| :--- | :--- | :--- | :--- | :--- | :--- |
| **TC_AC_001** | Verify creating a clone of a supported application. | A supported app (e.g., WhatsApp) is installed. | 1. Go to Settings > Apps > App Cloner.<br>2. Select WhatsApp.<br>3. Toggle Create app clone to ON. | A secondary WhatsApp icon with a distinct "Cloned" badge must appear on the Home Screen/App Drawer. | Pass |
| **TC_AC_002** | Verify concurrent execution of both original and cloned apps. | App Cloner is active for WhatsApp. | 1. Open the original WhatsApp.<br>2. Go to the Home screen.<br>3. Open the Cloned WhatsApp.<br>4. Check the Recent Apps menu. | Both applications must run simultaneously in the background without crashing. Both should appear as separate instances in the Recent Apps menu. | Pass |
| **TC_AC_003** | Verify data independence between original and cloned apps. | User is logged into an account on the original app. | 1. Launch the Cloned app. | The Cloned app must open to a fresh login/setup screen. It must not automatically inherit the login session or cache of the original app. | Pass |

## Test Suite: Deletion & Edge Cases

| Test Case ID | Description | Pre-conditions | Test Steps | Expected Result | Status |
| :--- | :--- | :--- | :--- | :--- | :--- |
| **TC_AC_004** | Verify the behavior of the Cloned app when the original app is uninstalled. | Both original and Cloned apps are present. | 1. Long-press the original app icon and select Uninstall.<br>2. Confirm uninstallation. | The system must prompt a warning that uninstalling the original app will also delete the Cloned app and its data. Upon confirmation, both must be removed. | Pass |
| **TC_AC_005** | Verify deleting only the Cloned app. | Both original and Cloned apps are present with data. | 1. Go to Settings > Apps > App Cloner.<br>2. Toggle Create app clone to OFF for the specific app.<br>3. Confirm deletion. | The Cloned app and its data must be removed. The original app and its data must remain completely unaffected. | Pass |
