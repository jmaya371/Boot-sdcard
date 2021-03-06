---
grand_parent: SDCARD Bootloader Applications
parent: SDCARD Bootloader
title: Building and Running on PIC32MZ Embedded Graphics with Stacked DRAM (DA) Starter Kit (Crypto)
has_toc: false
---

[![MCHP](https://www.microchip.com/ResourcePackages/Microchip/assets/dist/images/logo.png)](https://www.microchip.com)

# Building and Running the SDCARD Bootloader applications

## Downloading and building the application

To clone or download this application from Github,go to the [main page of this repository](https://github.com/Microchip-MPLAB-Harmony/bootloader_apps_sdcard) and then click Clone button to clone this repo or download as zip file. This content can also be download using content manager by following [these instructions](https://github.com/Microchip-MPLAB-Harmony/contentmanager/wiki)

Path of the application within the repository is **apps/sdcard_bootloader/**

To build the application, refer to the following table and open the project using its IDE.

### Bootloader Application

| Project Name      | Description                                    |
| ----------------- | ---------------------------------------------- |
| bootloader/firmware/pic32mz_das_sk.X    | MPLABX Project for [PIC32MZ Embedded Graphics with Stacked DRAM (DA) Starter Kit (Crypto)](http://www.microchip.com/DevelopmentTools/ProductDetails/DM320010-C)|

### Test Application

| Project Name      | Description                                    |
| ----------------- | ---------------------------------------------- |
| test_app/firmware/pic32mz_das_sk.X    | MPLABX Project for [PIC32MZ Embedded Graphics with Stacked DRAM (DA) Starter Kit (Crypto)](http://www.microchip.com/DevelopmentTools/ProductDetails/DM320010-C)|

## Setting up [PIC32MZ Embedded Graphics with Stacked DRAM (DA) Starter Kit (Crypto)](http://www.microchip.com/DevelopmentTools/ProductDetails/DM320010-C)

- Connect a micro USB cable to the UART-USB port J5
- For programming, connect a micro USB cable to the USB Debug port J19
- Use the micro sdcard slot J10 of the device to insert a micro sdcard

## Running the Application

1. Open the test application project *test_app/firmware/pic32mz_das_sk.X* in the IDE
2. Build the project to generate the binary **(Do not program the binary)**
3. Open the bootloader project *bootloader/firmware/pic32mz_das_sk.X* in the IDE
4. Build and program the application using the IDE

5. **LED1** will be Turned On once programming is completed and bootloader starts running

6. Open the Terminal application (Ex.:Tera Term) on the computer to get test application messages through UART once bootloaded
7. Configure the serial port settings as follows:
    - Baud : 115200
    - Data : 8 Bits
    - Parity : None
    - Stop : 1 Bit
    - Flow Control : None

8. Copy the generated application binary file to a micro sdcard from the Host PC
    - *\<harmony3_path\>\bootloader_apps_sdcard\apps\sdcard_bootloader\test_app\firmware\pic32mz_das_sk.X\dist\pic32mz_das_sk\production\pic32mz_das_sk.X.production.bin*

9. Rename the copied application binary file to **image.bin**

10. Insert the micro sdcard with the application binary **image.bin** to the micro sdcard slot on the device

11. Once the application is successfully programmed **LED3** should start blinking and you should see below output on the console

    ![output](./images/btl_sdcard_test_app_console_success.png)

12. Remove the micro sdcard from the sdcard slot

13. Press and hold the Switch **SW1** to trigger Bootloader from test application and you should see below output

    ![output](./images/btl_sdcard_test_app_console_trigger_bootloader.png)

14. Repeat Steps 10-12 once and jump to Step-15
    - This step is to verify that bootloader is running after triggering bootloader from test application in Step 13

15. **Press and hold** the Switch **SW1** and then press Reset button or Power cycle the device to force trigger bootloader at startup
16. Repeat Steps 10-12 once
    - This step is to verify whether bootloader is triggered by switch press at reset


## Additional Steps (Optional)
- To bootload any other application refer to [Application Configurations](../../docs/readme_configure_application_pic32m.md)

- Once done repeat the applicable steps mentioned in [Running The Application](#running-the-application)