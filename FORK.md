# Code-Andy fork

Updated October 1, 2026 to upstream [Build_26.40.01](https://github.com/ChrGri/DIY-Sim-Racing-FFB-Pedal/releases/tag/Build_26.40.01), commit `a1ba636b723f9b0bd99fd576b4dc57a8f9c96749`.

`main` is the current release-based source. `gilphilbert-v12-48v-26.40.01` points to the same source checkpoint. Earlier work is retained on `gilphilbert-v12-48v-26.39.02`, and the original v88/48 V source remains on `legacy-v88-48v` at `6b4dad2cf242e25d6687adca7d23462ecda30970`.

## Local differences from upstream

- Gilphilbert v1.x 48 V tuning: `SERVO_MAX_VOLTAGE_IN_V_48V=49.0f`, giving the existing 51 V servo bleeder threshold. The current upstream's 40–55 V detection range already covers the old v88 voltage-range adjustment.
- Pedal and DevKit bridge version generation accepts an explicit override and defaults to release version `26.40.01` in the local PlatformIO projects.
- Gilphilbert v1.x and DevKit bridge use explicit USB/esptool upload configuration. The pedal port is the retained local `COM11`; the bridge port is deliberately `COM_SET_ME` until configured. Select the actual connected board's port before any upload. These port settings are not hardware identities.
- A VS Code Python environment preference is retained from the local working copy.

Targets used for this rig are `ControlBoard_PCBA_V1X` in `ESP32/` and `Bridge_esp32s3usbotg` in `ESP32_master/`. Upstream plugin and firmware versions must be kept together; the matching official plugin is in the release linked above.

The two previous v88 custom source edits are preserved in history. Their functionality was carried forward through the release-based voltage detection and 51 V threshold, rather than reapplying obsolete v88 source files onto newer firmware.

Source synchronization and successful compilation do not establish that hardware was flashed, calibrated or tested. Original upstream attribution, documentation and license remain in place.
