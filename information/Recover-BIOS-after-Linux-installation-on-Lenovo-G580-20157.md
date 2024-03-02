# Recover BIOS after Linux installation on Lenovo G580 (20157)

---

* Download the BIOS update utility from [the Lenovo website](https://pcsupport.lenovo.com/us/en/products/laptops-and-netbooks/lenovo-g-series-laptops/lenovo-g580-notebook/20157/downloads/driver-list/) that matches your OS architecture. I'm not sure about the version, I used `62CN97WW`.
* Run it from cmd with the `/ext` flag.

---

Open the file `default.rsp` with a text editor and replace its contents with the following:
```
/bak BIOS.bak /patch /silent /cvar /sd /sn /cac /cbp 30
```
Run `SctWinFlash64.exe` or `SctWinFlash32.exe` (again, depending on your OS architecture).

---

* Wait for the system to reboot automatically. **Do not try to enter the BIOS at this stage!**
* Done. Now you can safely enter the BIOS in any way you like.

---

> [!CAUTION]
> I assume that if you still have Linux installed, it will stop booting!