# OSF GREEN

OSF GREEN is the first Open Sensor Fusion hardware target.

## Hardware Identity

- Board name: OSF GREEN
- MCU: STM32F405RGT6
- IMU: ICM42688P-class device
- Magnetometer: MMC5983MA
- Host interface used by the Linux RFC: UART OSF0 frame stream

## Host Interface

The board firmware sends OSF0 frames over a 115200 8N1 UART link. The Linux
RFC driver binds as a UART serdev client and registers IIO devices after the
first valid capability report.

Observed IIO devices during Raspberry Pi smoke testing:

- `osf-accel`
- `osf-gyro`
- `osf-magn`
- `osf-temp`

## Test Scope

The tested path is:

STM32F405 OSF0 UART stream -> Raspberry Pi 4 serdev -> Linux IIO raw and
buffer reads.

This document describes hardware identity and host interface behavior. It does
not define USB demo output, calibration sysfs, yaw debug frames, or
fusion/AHRS/Kalman output.
