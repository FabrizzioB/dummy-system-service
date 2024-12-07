# dummy-system-service

Systemd service example

https://roadmap.sh/projects/dummy-systemd-service

### Introduction

The goal of this project is to get familiar with systemd; creating and enabling a service, checking the status, keeping an eye on the logs, starting and stopping the service, etc.

### Requirements
Create a script called dummy.sh that keeps running forever and writes a message to the log file every 10 seconds simulating an application running in the background. Here is an example script:

```bash
#!/bin/bash

while true; do
  echo "Dummy service is running..." >> /var/log/dummy-service.log
  sleep 10
done
```

Create a systemd service dummy.service that should start the app automatically on boot and keep it running in the background. If the service fails for any reason, it should automatically restart.

You should be able to start, stop, enable, disable, check the status of the service, and check the logs i.e. following commands should be available for the service:

###  Interacting with the service
```bash
sudo chmod +x dummy.sh
sudo systemctl start dummy
sudo systemctl stop dummy
sudo systemctl enable dummy
sudo systemctl disable dummy
sudo systemctl status dummy
```

### Check the logs
```bash
sudo journalctl -u dummy -f
```

After completing this project, you will have a good understanding of systemd, creating custom services, managing existing services, debugging issues, and more.

### Set

```bash
sudo mv dummy.sh /home/fabrizzio/
sudo chmod +x /home/fabrizzio/dummy.sh
sudo mv dummy.service /etc/systemd/system/
sudo systemctl daemon-reload
sudo systemctl enable dummy.service
sudo systemctl start dummy.service


```