ACTIVAR CONFIGURACION DE MANUAL DE VENTILADOR
echo 'options thinkpad_acpi fan_control=1' | sudo tee -a /etc/modprobe.d/thinkpad_acpi.conf
