[![GitHub Latest Release][releases_shield]][latest_release]
[![GitHub All Releases][downloads_total_shield]][releases]

[latest_release]: https://github.com/clipman/Xiaomi-cloud-tokens-extractor/releases/latest
[releases_shield]: https://img.shields.io/github/release/clipman/Xiaomi-cloud-tokens-extractor.svg?style=popout

[releases]: https://github.com/clipman/Xiaomi-cloud-tokens-extractor/releases
[downloads_total_shield]: https://img.shields.io/github/downloads/clipman/Xiaomi-cloud-tokens-extractor/total

# Xiaomi Cloud Tokens Extractor

This tool retrieves tokens for all devices connected to Xiaomi cloud and encryption keys for BLE devices.

It supports two ways of authentication:
- username (e-mail/Xiaomi Cloud account ID) & password
- QR code

After logging in you have to select a Xiaomi's server region (`cn` - China, `de` - Germany etc.). Leave it empty to check all available

In return all of your devices connected to account will be listed, together with their name and IP address.

## Windows
Download and run [token_extractor.exe](https://github.com/clipman/Xiaomi-cloud-tokens-extractor/releases/latest/download/token_extractor.exe).

## Linux & Home Assistant (in [SSH & Web Terminal](https://github.com/hassio-addons/addon-ssh))

Execute following command:
```bash
bash <(curl -L https://github.com/clipman/Xiaomi-cloud-tokens-extractor/raw/master/run.sh)
```

> If installation fails try Docker version

## Docker & Home Assistant (in [SSH & Web Terminal](https://github.com/hassio-addons/addon-ssh))

Execute following command:
```bash
bash <(curl -L https://github.com/clipman/Xiaomi-cloud-tokens-extractor/raw/master/run_docker.sh)
```

> To run this command in HA you have to disable `protected mode` in addon's settings and restart it

## Manual run in python

Download and unpack archive:
```bash
wget https://github.com/clipman/Xiaomi-cloud-tokens-extractor/releases/latest/download/token_extractor.zip
unzip token_extractor.zip
cd token_extractor
```

Install dependencies and run script:
```bash
pip3 install -r requirements.txt
python3 token_extractor.py
```

## Troubleshooting

If you have problems with using this tool try following solutions:
- Make yourself sure that you provide correct credentials (_e.g. not ones from Roborock app!_)
- Remove Cloudflare DNS
- Disable network ad blockers (AdGuard, PiHole, etc.) and restrictions (UniFi Country Restriction etc.)
- Check SPAM folders for 2FA e-mail
- Use QR code authentication instead of username & password
- Just wait - there is a [limit of 3/5 (depending on region) 2FA requests per day](https://account.xiaomi.com/helpcenter/faq/en_US/02.faqs/05.sms-and-email-verification-code/faq-3)

## Home Assistant additional tools

* [Map extractor](https://github.com/PiotrMachowski/Home-Assistant-custom-components-Xiaomi-Cloud-Map-Extractor) - live map for Xiaomi Vacuums
* [Map card](https://github.com/PiotrMachowski/lovelace-xiaomi-vacuum-map-card) - manual vacuum control from a Lovelace card
