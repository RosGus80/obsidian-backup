
To make laptops run with lid closed:

`sudo nano /etc/systemd/logind.conf`

add/uncomment: 
```
HandleLidSwitch=ignore
HandleLidSwitchExternalPower=ignore
HandleLidSwitchDocked=ignore
```

then apply:
`systemctl restart systemd-logind`
