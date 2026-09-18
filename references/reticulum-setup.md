# Reticulum + LXMF Setup for Raspberry Pi + Pluto+

## Installation

```bash
sudo apt update
sudo apt install -y python3-pip python3-venv
python3 -m venv ~/reticulum-env
source ~/reticulum-env/bin/activate
pip install rns lxmf
```

## Basic Config (`~/.reticulum/config`)

```ini
[reticulum]
  enable_transport = Yes
  share_instance = Yes
  shared_instance_port = 37428
  instance_control_port = 37429
  panic_on_interface_error = No

[logging]
  loglevel = 4

[interfaces]

  [[UDP Interface]]
    type = UDPInterface
    enabled = yes
    listen_ip = 0.0.0.0
    listen_port = 4242
    forward_ip = 255.255.255.255
    forward_port = 4242

  # Example for RNode / LoRa module
  # [[RNode Interface]]
  #   type = RNodeInterface
  #   enabled = yes
  #   port = /dev/ttyACM0
  #   frequency = 868000000
  #   bandwidth = 125000
  #   txpower = 14
  #   spreadingfactor = 7
  #   codingrate = 5
```

## Useful Commands

```bash
# Show status
rnstatus

# Show identities
rnid

# Announce
rnsd   # run as service or in screen/tmux

# LXMF daemon
lxmd
```

## Integrating with Pluto+ / SDR

Reticulum does not have a native SoapySDR interface yet.
Common patterns:

1. **GNU Radio → Virtual Serial / UDP**
   - Create a flowgraph that modulates/demodulates packets.
   - Expose a UDP or serial port that Reticulum can use as a custom interface.

2. **Python custom interface**
   - Write a Reticulum Interface class that uses `pyadi-iio` or SoapySDR to TX/RX.

3. **Hybrid**
   - Use Pluto+ for spectrum monitoring + RNode/LoRa for actual mesh traffic.

## systemd Service Example

```ini
[Unit]
Description=Reticulum Network Stack
After=network.target

[Service]
Type=simple
User=pi
WorkingDirectory=/home/pi
ExecStart=/home/pi/reticulum-env/bin/rnsd
Restart=always
RestartSec=5

[Install]
WantedBy=multi-user.target
```
