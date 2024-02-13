# raspi-pico-dap

Small PCB for a Raspberry Pi Pico to 2x5 1.27mm pin socket.<br>

<img src=https://github.com/shufps/raspi-pico-dap/assets/3079832/b1f20629-d737-4bdf-a932-fb5c4001894b width=300px>

**note**: This works best with a PCB thickness of 0.8mm

SWD Pinout:<br>

![image](https://github.com/shufps/raspi-pico-dap/assets/3079832/17f463d0-9c8e-42b3-9b7a-456a66526952)

Digikey parts:<br>
1175-1627-ND <br>
<img src=https://github.com/shufps/raspi-pico-dap/assets/3079832/58be0c35-87c3-4fe1-9db0-5edd3bd3a5c5 width=200px>
<br>
1528-2009-ND<br>
<img src=https://github.com/shufps/raspi-pico-dap/assets/3079832/5d9f2f8c-975f-4ab3-84c6-70076ab2c00e width=200px>
<br>
2648-SC0915CT-ND<br>
<img src=https://github.com/shufps/raspi-pico-dap/assets/3079832/f8ba36de-ad2e-407d-8181-f5979e96ee4d width=200px>

## Install probe-rs

```bash
# install probe-rs
curl --proto '=https' --tlsv1.2 -LsSf https://github.com/probe-rs/probe-rs/releases/latest/download/probe-rs-installer.sh | sh
```

It is also suggested to install the udev rules:
```
# /etc/udev/rules.d/99-pico.rules
#picoprobe
SUBSYSTEM=="usb", ATTRS{idVendor}=="2e8a", MODE="0666"
```

After adding execute following lines and disconnect and connect the USB device:
```
sudo udevadm control --reload-rules &&  sudo udevadm trigger 
```
