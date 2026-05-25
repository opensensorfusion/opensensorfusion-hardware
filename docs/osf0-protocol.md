# OSF0 Protocol Overview

OSF0 is the first host-visible frame format used by OSF GREEN for the Linux
IIO RFC path.

## Transport

- UART
- 115200 8N1 in the current test setup
- Device to host OSF0 binary frames

## Frame Classes

The current Linux RFC consumes:

- capability reports
- device status frames
- sensor sample frames

Samples are mapped to Linux IIO devices for accel, gyro, magnetometer, and
temperature data.

## Non-goals For OSF0 v0

The Linux RFC does not define:

- USB transport
- Web Serial JSON output
- calibration sysfs
- yaw debug frames
- fusion/AHRS/Kalman output
- production timestamp correlation

The detailed Linux-side reference should match
`Documentation/iio/open-sensor-fusion-protocol-v0.rst` in the Linux RFC
patch series.
