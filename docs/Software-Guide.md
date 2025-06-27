---
layout: project
---

# <span style="display:inline-block;margin-bottom:1rem;">Software Guide</span>

This section covers the software used in the IoT School PH Kit, including how to install and configure it for your development needs.

# Installation of Arduino IDE

Go to the official [Arduino website](www.arduino.cc.)

Hover over the Software tab and select Downloads.

Download the installer for your operating system (e.g., Windows Installer).

Open the downloaded file and follow the on-screen instructions:

Agree to the license terms.

Choose installation options (default selections are recommended).

Select the installation path or leave it as default.

Click Install and wait for the process to complete.

Once installed, launch the Arduino IDE from your desktop or Start menu

# Adding Boards Lorfi-L RAK3172

Open Arduino IDE.

Go to File > Preferences.

![Software Guide 1](\assets\Images\LORFI Components\Software-Guide_Images\Software_Guide1.png)

In the Additional Board Manager URLs field, add the following URL:

```c
https://raw.githubusercontent.com/RAKWireless/RAKwireless-Arduino-BSP-Index/main/package_rakwireless_com_rui_index.json
```

If there are existing URLs, add this on a new line or separate with a comma. Click OK to save.

Restart the Arduino IDE.

Go to Tools > Board > Boards Manager. In the search bar, type RAK.

![Software Guide 2](\assets\Images\LORFI Components\Software-Guide_Images\Software_Guide2.png)

![Software Guide 3](\assets\Images\LORFI Components\Software-Guide_Images\Software_Guide3.png)

Locate RAKwireless RUI STM32 Boards and click Install.

After installation, select your RAK3172 board via Tools > Board > RAKWireless RUI STM32 Modules > WisDuo RAK3172 Evaluation Board.

![Software Guide 4](\assets\Images\LORFI Components\Software-Guide_Images\Software_Guide4.png)

# Adding Boards Lorfi-WB ESP32

