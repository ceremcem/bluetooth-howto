# bluetooth-howto

On Linux:

* Check if bluetooth is blocked or not:

```
# rfkill list
0: dell-rbtn: Wireless LAN
	Soft blocked: no
	Hard blocked: no
2: phy0: Wireless LAN
	Soft blocked: no
	Hard blocked: no
4: hci0: Bluetooth
	Soft blocked: no
	Hard blocked: no
```

* list available Bluetooth interfaces:

```
hcitool dev
Devices:
	hci0	XX:XX:XX:XX:XX:XX
```

> **TROUBLESHOOTING**: If there is no devices listed above, try restarting your computer. 
> This usually happens after resuming from a suspension.

* scan devices nearby:

```
# hcitool scan
Scanning ...
	28:A4:ED:35:B1:67	Foo
```

# Pairing 

(see https://raspberrypi.stackexchange.com/a/53456/24257)

```
bluetoothctl
[bluetooth]# scan on 
[bluetooth]# pair XX:XX:XX:XX:XX:XX
[bluetooth]# trust XX:XX:XX:XX:XX:XX
[bluetooth]# quit
```

