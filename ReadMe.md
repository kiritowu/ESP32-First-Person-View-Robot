# First Person View Robot Documentation

# First Person View Robot by SP-RITE

Title : First Person View Robot

Date of Published : 25 Dec 2020

Team Members : 

1. Wong Zhao Wu (Project Leader & Software Manager)
2. Nur 'Arifah binte Mohd Shahri  (Modelling & Electronics Manager)
3. Ye Ye Taut (Hardware Manager)

# Electronics & Hardware Configuration

![First%20Person%20View%20Robot%20Documentation%2077f1a5deff0344c2b96dc75bc3dfc474/Untitled.png](First%20Person%20View%20Robot%20Documentation%2077f1a5deff0344c2b96dc75bc3dfc474/Untitled.png)

[List of Components](https://www.notion.so/0d2a1703a1f74ff1b30ac4c3d93e549b)

# Software Configuration

## Software Setup

1. Download all the source code from [GitHub Repo](https://github.com/kiritowu) and put it under the same folder.
2. Install ESP32 Add-on in Arduino IDE by following steps below:
    1. Go to File > Preference > Additional Boards Manager URLs

    ![First%20Person%20View%20Robot%20Documentation%2077f1a5deff0344c2b96dc75bc3dfc474/Untitled%201.png](First%20Person%20View%20Robot%20Documentation%2077f1a5deff0344c2b96dc75bc3dfc474/Untitled%201.png)

    2. Paste the link: [https://dl.espressif.com/dl/package_esp32_index.json](https://dl.espressif.com/dl/package_esp32_index.json) into the text field.

    3. Tools>Board>Boards Manager

    ![First%20Person%20View%20Robot%20Documentation%2077f1a5deff0344c2b96dc75bc3dfc474/Untitled%202.png](First%20Person%20View%20Robot%20Documentation%2077f1a5deff0344c2b96dc75bc3dfc474/Untitled%202.png)

    4. Click Install

3. Boot ESP32-Cam up into flash mode with the configuration below.
(*In our case, we uses an Arduino Genuino Uno to upload our code into the ESP32-Cam board but theoretically any FTDI programmer would do the job*)

    ![First%20Person%20View%20Robot%20Documentation%2077f1a5deff0344c2b96dc75bc3dfc474/Untitled%203.png](First%20Person%20View%20Robot%20Documentation%2077f1a5deff0344c2b96dc75bc3dfc474/Untitled%203.png)

    *Make Sure GPIO 0 is connected to Ground (Blue Wire) to boot ESP32-Cam into flashing mode.

    *Make Sure Arduino Reset is connected to Ground (Purple Wire) to keep the chip in Reset Mode.

4. Open the source code folder and configure Arduino IDE into following setup:

    ![First%20Person%20View%20Robot%20Documentation%2077f1a5deff0344c2b96dc75bc3dfc474/Untitled%204.png](First%20Person%20View%20Robot%20Documentation%2077f1a5deff0344c2b96dc75bc3dfc474/Untitled%204.png)

    - Board: "ESP 32 Wrover Module"
    - Upload Speed: "115200"
    - Flash frequency: "40 MHz"
    - Flash Mode: "QIO"
    - Patrician Scheme : "Huge APP (3MB No OTA/1MB SPIFFS)"
5. Setup and Open Phone Hotspot under the following configuration.

    > SSID : FPV
    Password : FPV-SP-RITE

6. Click upload buttons in Arduino IDE to compile & upload the source code, once upload is completed, Remove GPIO 0 to Ground wires (^Blue from the diagram above) and reboot the ESP32-Cam.
7. Flash light will blink 5 times to indicate that the board have connected to your mobile's hotspot.
8. Go to 192.168.43.220 with your mobile's browser and you should see the HTML user interface.
(*You may also choose to connect other device to your phone's hotspot and communicate to the board with the same local IP Address but the connection might not be that stable.*)

# User Manual

### Before

1. Configure the Electronics and upload the source code to ESP-32 Cam module as mentioned above.
2. Make sure both the 2S 25C Batteries is charged within the range of 7.7V(*Maximum*) to 7.4(*Minimum*)

    Overcharging or Discharging of battery will cause damage or possible Explosion.

    Both batteries should have close to same cycle and voltage as much as possible to prevent damaging the battery. (E.g. Batt1 = 7.7V, Batt2 = 7.69V)

3. Make sure LM2596 DC Power Module is configured to output 12 V.
4. Make sure the mobile hotspot is configured and kept alive before connecting the batteries.

### During

1. After seeing flash light blinking 5 times, connect to 192.168.43.220 with mobile browser
2. Adjust resolution to minimize the latency of images
3. Check the battery voltage and stop operation when the battery dropped to 14.8V (Over discharge may cause damage to LiPo batteries)

### After

1. Unplug the batteries.
2. Store the batteries at 7.6V in a controlled environment for each battery.
3. Do not drop or puncture any components and handle it with love and care.
