# mesh-network-rpi-pluto

**Antigravity / Agent Skill** for building mesh network projects using **Raspberry Pi + Pluto+ (ADALM-Pluto+) SDR**.

This skill helps AI agents (especially Google Antigravity) guide users through designing, setting up, and troubleshooting long-range mesh networks that combine Raspberry Pi compute with software-defined radio.

## Features

- Hardware stack guidance (Raspberry Pi 4/5/Zero 2W + Pluto+)
- Preferred mesh layer: **Reticulum Network Stack + LXMF**
- Alternatives: Meshtastic, custom GNU Radio SDR mesh
- SoapySDR, libiio, pyadi-iio setup
- Antenna, power, GPS/RTC recommendations
- Deployment (systemd, hardening)
- Legal & power safety reminders

## Skill Structure

```
mesh-network-rpi-pluto/
├── SKILL.md                          # Main skill instructions
└── references/
    ├── reticulum-setup.md            # Reticulum + LXMF config & systemd
    ├── pluto-plus-firmware.md        # Firmware & networking tips
    └── legal-and-power.md            # Frequency & EIRP reminders
```

## Installation (Antigravity)

### Global (available in all projects)

```bash
mkdir -p ~/.gemini/antigravity/skills

git clone https://github.com/fadhillaxl/mesh-network-rpi-pluto.git \
  ~/.gemini/antigravity/skills/mesh-network-rpi-pluto
```

### Workspace (project only)

```bash
cd /path/to/your/project
mkdir -p .agents/skills

git clone https://github.com/fadhillaxl/mesh-network-rpi-pluto.git \
  .agents/skills/mesh-network-rpi-pluto
```

After installation, the skill is automatically available. You can also invoke it manually with:

```
/mesh-network-rpi-pluto
```

## Example Prompts

- "Buatkan setup mesh network chat jarak jauh pakai Raspberry Pi 4 dan Pluto+"
- "How to run Reticulum on Pi with Pluto SDR"
- "Troubleshoot Pluto not detected on Raspberry Pi"
- "Mesh node with solar power and GPS"

## License

MIT — feel free to use, modify, and share.

## Credits

Created for use with Google Antigravity agent platform.
