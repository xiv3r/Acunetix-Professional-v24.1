# Acunetix-Professional-v24.1

## Setup:

1) Download Acunetix Professional

2) Before installing the tool, add to your hosts file (usually /etc/hosts) at the end:
  ```
127.0.0.1  erp.acunetix.com
127.0.0.1  erp.acunetix.com.
::1  erp.acunetix.com
::1  erp.acunetix.com.

192.178.49.174  telemetry.invicti.com
192.178.49.174  telemetry.invicti.com.
2607:f8b0:402a:80a::200e  telemetry.invicti.com
2607:f8b0:402a:80a::200e  telemetry.invicti.com.
  ```
3) Now install the tools with sudo : `sudo bash acunetix_xxxxx.sh`

4) Once installed let's stop its service with: `sudo systemctl stop acunetix`

5) Let's replace wvsc file:
  ```
  - sudo cp wvsc /home/acunetix/.acunetix/v_240111130/scanner/wvsc
  - sudo chown acunetix:acunetix /home/acunetix/.acunetix/v_240111130/scanner/wvsc
  - sudo chmod +x /home/acunetix/.acunetix/v_240111130/scanner/wvsc
  ```
6) Time to add licenses:
  ```
  - sudo rm /home/acunetix/.acunetix/data/license/*
  - sudo cp license_info.json /home/acunetix/.acunetix/data/license/
  - sudo cp wa_data.dat /home/acunetix/.acunetix/data/license/
  - sudo chown acunetix:acunetix /home/acunetix/.acunetix/data/license/license_info.json
  - sudo chown acunetix:acunetix /home/acunetix/.acunetix/data/license/wa_data.dat
  - sudo chmod 444 /home/acunetix/.acunetix/data/license/license_info.json
  - sudo chmod 444 /home/acunetix/.acunetix/data/license/wa_data.dat
  - sudo chattr +i /home/acunetix/.acunetix/data/license/license_info.json
  - sudo chattr +i /home/acunetix/.acunetix/data/license/wa_data.dat
  ```

7) Now restart acunetix:
  ```
  - sudo systemctl start acunetix
  ```
