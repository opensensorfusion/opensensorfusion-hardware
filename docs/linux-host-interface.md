# Linux Host Interface

The Linux RFC driver targets the OSF0 UART stream from OSF GREEN.

## Path

STM32F405 OSF0 UART stream -> Raspberry Pi 4 UART serdev -> Linux IIO.

The driver registers IIO devices from the first valid capability report.

Observed device names:

- `osf-accel`
- `osf-gyro`
- `osf-magn`
- `osf-temp`

## RFC Scope

The current upstream RFC covers:

- OSF0 UART receive path
- capability report parsing
- device status parsing
- sensor sample parsing
- IIO raw reads
- IIO buffer reads

It does not add a private ioctl, broad custom sysfs ABI, USB transport,
calibration command ABI, yaw debug frames, or fusion output.

## Smoke Result

Raspberry Pi 4 smoke testing used kernel `6.12.75+rpt-rpi-v8`. The observed
path included serdev bind, IIO device registration, raw reads, buffer reads,
and module unload. No OSF oops, panic, or call trace was observed in that
smoke.
