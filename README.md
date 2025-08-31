
# Activar configuración de control manual de ventilador

```bash
echo 'options thinkpad_acpi fan_control=1' | sudo tee -a /etc/modprobe.d/thinkpad_acpi.conf
````

---

## Servicio systemd

(Mejor opción si quieres que se ejecute al arrancar del sistema)

### 1. Crear un servicio

```bash
sudo nano /etc/systemd/system/fan-control.service
```

**Contenido del servicio:**

```bash
[Unit]
Description=Set fan speed to level 2
After=multi-user.target

[Service]
Type=oneshot
ExecStart=/bin/bash -c 'echo "level 2" > /proc/acpi/ibm/fan'

[Install]
WantedBy=multi-user.target
```

---

### 2. Habilitar el servicio

```bash
sudo systemctl enable fan-control.service
sudo systemctl start fan-control.service
```


