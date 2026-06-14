# Bluetooth Simple Connector

Bluetooth en Linux suele recordar dispositivos y volver a intentar reconexiones automáticas que a veces se fallan o generan errores de estado.

Este script evita ese comportamiento: simplemente escanea, lista y conecta dispositivos bajo demanda, sin depender de reconexiones automáticas.

---

## Dependencias

En Ubuntu normalmente ya vienen instalados. Si no:

```bash

sudo apt install bluez python3-gi gir1.2-appindicator3-0.1

```

Instalación, (sin root):

mkdir -p ~/.local/share/applications/
mkdir -p ~/.local/bin/
mkdir -p ~/.local/share/icons/

cp ./bluetooth-simple-connector.desktop ~/.local/share/applications/
chmod +x ~/.local/share/applications/bluetooth-simple-connector.desktop

cp ./bt-sc ~/.local/bin/
chmod +x ~/.local/bin/bt-sc


Nota importante sobre el .desktop

Asegúrate de que contenga:

Exec=bt-sc
Icon=bt-sc


Uso:

Desde el menú de aplicaciones:

Bluetooth Simple Connector

o desde terminal:

bt-sc

Concepto:
• no reconexión automática
• no cache de dispositivos problemáticos
• escaneo manual controlado
• conexión bajo demanda

Nota:

El programa aparece como un icono en la barra del sistema (AppIndicator).

Puedes:

- Abrirlo solo cuando necesites escanear o conectar dispositivos
- Usarlo como herramienta puntual (no requiere estar siempre en segundo plano)
- Cerrarlo cuando termines sin afectar el sistema Bluetooth
