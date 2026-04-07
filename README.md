# KvmOverUsb
A plug-and-play KVM (Keyboard Video Mouse) device control.  Control any PC's keyboard/mouse over serial with interactive preview, web viewer, and TCP API for AI automation.

## What It Does

Control any PC's keyboard and mouse over USB while watching its screen via HDMI capture — all from another PC, a script, or an AI agent.

```mermaid
flowchart LR
    subgraph Controller["Controller PC"]
        APP[software]
    end

    subgraph Middle["kvm-over-usb adapter"]
        USBHOST[USB HOST]
        DEVICE[Core Processing]
    end

    subgraph Target["Target PC"]
        HID["Keyboard/Mouse"]
        HDMI_OUT["HDMI out"]
    end

    APP -- USB --> USBHOST
    USBHOST --> DEVICE
    DEVICE -- HDMI --> HDMI_OUT
    DEVICE -- USB --> HID

    USBHOST -- USB --> EXT["External USB Device<br>(USB drive / HDD)"]
```

## Features

.1.HID protocol transmission, driver-free
.2.Support BIOS keyboard control
.3.Upper computer program compatible with non-board video capture card
.4.On-board USB-HUB chip, reduce the number of interfaces
.5.Single MCU dual USB Device controller, reduce transmission delay
.6.The USB-A socket, used for USB expansion of the Controller PC, can connect wireless keyboards, Mouse, USB flash drives, external hard drives, and other USB devices.

## There are many, many open-source software options to choose from

[sunasaji](https://github.com/sunasaji) / [mcp-serial-hid-kvm](https://github.com/sunasaji/mcp-serial-hid-kvm)
[sunasaji](https://github.com/sunasaji)/[cli-serial-hid-kvm](https://github.com/sunasaji/cli-serial-hid-kvm)
[Jackadminx](https://github.com/Jackadminx)/[KVM-Card-Mini](https://github.com/Jackadminx/KVM-Card-Mini)
[ElluIFX](https://github.com/ElluIFX)/[KVM-Card-Mini-PySide6](https://github.com/ElluIFX/KVM-Card-Mini-PySide6)
[binnehot](https://github.com/binnehot)/[KVM-over-USB](https://github.com/binnehot/KVM-over-USB)

### FAQ

Q: Why doesn't the mouse work when the controlled end is a Linux distribution?

A: Some operating systems do not support the mouse in absolute coordinate mode. Please try switching to relative coordinate mode for operation.

Q: How to send the Ctrl + Alt + Delete key combination?

A: To send these key combinations to the controlled end, it is recommended to use the shortcut function in the Keyboard menu.

Q: What should I do if there is an input abnormality when using the software?

A: Please use the reload or reset function in the software's device menu. If the problem persists after use, it is recommended to try restarting the controlled end's operating system.

Q: What should I do if the case is incorrect when fast-pasting or using clipboard input?

A: Please sync the keyboard status using the sync indicator function in the menu before trying again.
