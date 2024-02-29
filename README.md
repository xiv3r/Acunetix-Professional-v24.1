<img width="1000" height="500" src="https://github.com/xiv3r/acunetix_23.11.231123131_x64/blob/main/logo/acunetix-logo.png">



# <h1 align="center"> Acunetix Professional v24.1 </h1>

<p align="center"> Acunetix is an automated web application security testing tool that audits your web applications by checking for vulnerabilities like SQL Injection, Cross site scripting and other exploitable vulnerabilities. </p>


<br></br>

## Setup:

1) Download Acunetix Professional
```
git clone https://github.com/xiv3r/Acunetix-Professional-v24.1.git
cd Acunetix-Professional-v24.1
wget
```
3) Before installing the tool, add to your hosts file (usually /etc/hosts) at the end:
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
