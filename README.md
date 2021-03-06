# rpi-rasptank-pro

This is a robotics project that uses an Adeept RaspTank Pro.

| Key        | Value |
|:---------- |:----- |
| **Model**  | Adeept RaspTank Pro
| **Device** | Raspberry PI 3B+


## Requirements

- `dtparam=i2c_arm=on` in `/boot/config.txt`
- Build rpi_ws281x as instructed by [rpi-ws281x/rpi-ws281x-go](https://github.com/rpi-ws281x/rpi-ws281x-go)


### Controller

```
sudo apt install xboxdrv
echo 'options bluetooth disable_ertm=Y' | sudo tee -a /etc/modprobe.d/bluetooth.conf
```

Sometimes, you might have to restart the bluetooth service to get bluetoothctl working:
```
sudo systemctl restart bluetooth.service
```

You also need SDL2:
```
sudo apt-get install libsdl2-dev
```

You might also have to disable to `sap` plugin:
- Type `sudo systemctl edit --full bluetooth.service`
- Add `--noplugin=sap` at the end of the line starting with `ExecStart=`