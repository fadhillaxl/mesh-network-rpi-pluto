# Legal & Power Considerations (Critical)

Always remind the user of these points:

## Frequency Bands

Common mesh-friendly ISM / amateur bands (check local regulations):

| Band       | Typical Use          | Notes                          |
|------------|----------------------|--------------------------------|
| 433 MHz    | LoRa / ISM           | Very popular in Europe/Asia   |
| 868 MHz    | LoRa (EU)            | Duty cycle limits apply       |
| 915 MHz    | LoRa (US/AU)         | Different power rules         |
| 2.4 GHz    | WiFi / custom        | Crowded, shorter range        |
| Amateur    | 144 / 430 / 1296 etc | Requires amateur radio license|

**Never transmit outside legal bands or above legal power.**

## Power & EIRP

- Pluto+ / ADALM-Pluto TX power is relatively low (typically < 10 dBm without external PA).
- Adding external PA + antenna gain can easily exceed legal limits.
- Always calculate EIRP = TX power + antenna gain - cable loss.
- In many countries duty-cycle limits also apply (especially 868 MHz).

## Safety

- Do not point high-gain antennas at people at close range.
- Use proper RF connectors and cables.
- Protect against lightning if outdoor antenna is used.

## Recommendation in Skill Responses

Always include a short legal reminder when giving TX-related advice:

> "Pastikan kamu mematuhi regulasi frekuensi dan power di negara kamu. Pluto+ sendiri dayanya rendah, tapi kalau pakai PA eksternal + antena high-gain bisa cepat melebihi batas legal."
