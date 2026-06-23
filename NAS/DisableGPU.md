# Disable GPU (Radeon HD 8570 - TrueNAS Scale)

## Power management (auto-idle without unbinding)
sudo sh -c 'echo auto > /sys/bus/pci/devices/0000:01:00.0/power/control'

## Fully unbind the driver
sudo sh -c 'echo 0000:01:00.0 > /sys/bus/pci/drivers/radeon/unbind'

## Disable the device
sudo sh -c 'echo 0 > /sys/bus/pci/devices/0000:01:00.0/enable'

## Verify

# Should show: auto
cat /sys/bus/pci/devices/0000:01:00.0/power/control

# Should show: suspended
cat /sys/bus/pci/devices/0000:01:00.0/power/runtime_status

# Should show: 0 (device disabled)
cat /sys/bus/pci/devices/0000:01:00.0/enable

# PCI address should NOT appear here (driver unbound)
ls /sys/bus/pci/drivers/radeon/
