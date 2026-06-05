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
