# Kernel v3 Identity Notes

These notes track the public project identity issues raised during Linux RFC
review. They are not part of the kernel patch series.

## Proposed Concrete Device Identity

Use OSF GREEN as the first concrete hardware target.

## Compatible Direction

Review `opensensorfusion,osf-green` for v3.

`opensensorfusion,osf-uart` can read like a bus or protocol suffix rather than
a concrete device. The binding should describe the hardware endpoint, not only
the transport.

## Vendor Prefix Support

The Open Sensor Fusion GitHub organization and public repositories provide
project identity, hardware documentation, firmware location, and Linux host
documentation.

## Remaining Risk

Reviewers may still reject the prefix or compatible if schematic, PCB, BOM, and
board photos are not published before v3.

## Action

Publish OSF GREEN board photo, schematic export, PCB export, and BOM before
the next binding revision if possible.
