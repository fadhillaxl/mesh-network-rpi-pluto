# Pluto+ / ADALM-Pluto Firmware & Networking Notes

## Official vs Pluto+ Firmware

- Official ADI firmware works on both ADALM-Pluto and Pluto+.
- Pluto+ community firmware (https://github.com/plutoplus/plutoplus) adds better support for Gigabit Ethernet, SD card, dual TX/RX improvements, etc.

## Default Access

- USB gadget mode IP: **192.168.2.1**
- Username: `root`
- Password: `analog`

```bash
ssh root@192.168.2.1
```

## Useful Commands on Pluto

```bash
# Check version
fw_printenv | grep version
cat /etc/version

# Network
ifconfig
ip addr

# IIO devices
iio_info -s
iio_attr -a
```

## Making Pluto Visible on the Host Network (recommended for Pi)

On the Raspberry Pi side after connecting Pluto via USB:

```bash
# Usually creates usb0 or eth1
ip addr show

# You can bridge or route if needed
```

For Pluto+ with Ethernet port: just plug Ethernet and it can get DHCP or use static IP.

## Firmware Update (USB method)

1. Download latest `.zip` from ADI or Pluto+ releases.
2. Extract and put the files on a USB drive or use the mass-storage mode of Pluto.
3. Follow the official update procedure (usually involves putting Pluto into update mode).

## Recommended for Mesh Projects

- Keep firmware reasonably recent.
- Prefer external clock / GPSDO if available for multi-node frequency stability.
- Disable unnecessary services on Pluto to free CPU/RAM.
