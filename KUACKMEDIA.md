# Fork de kuackmedia

Fork de [EddyVerbruggen/Toast-PhoneGap-Plugin](https://github.com/EddyVerbruggen/Toast-PhoneGap-Plugin) en la versión `2.7.3` publicada en npm (MIT, ver `LICENSE`). Lo usan las apps Cordova de
Kuack Media para el toast nativo en iOS y Android (`ui/ToastMessage.js`; la web usa Toastify).

Base: `55856bc` (tag `2.7.3`), idéntico al paquete `cordova-plugin-x-toast@2.7.3` de npm que las apps instalaban hasta noviembre de 2026.

**Lo publicado es el commit fijado en `_common/configTemplates/config-app*.xml`** del repo de las apps
(`github:kuackmedia-apps/cordova-plugin-x-toast#<sha>`), no la punta de una branch: un push a este repo no llega a ningún
binario hasta que se mueve ese pin, y mover el pin es un diff que se revisa. La branch `kuack` es la línea de
Kuack; `master` queda como el de upstream.

## Cambios respecto de upstream

Ninguno en el código: el fork existe para que el app dependa sólo de Apache Cordova y de repos de Kuack (fila A18 del RFP de Claro, CM-RFP-001).

## Para actualizar desde upstream

`git fetch upstream --tags`, en una branch merge (o rebase) de la versión nueva sobre `kuack`, revisar los
cambios de arriba, probarlo en un app con `config-app-local.xml` (path local del checkout), llevarlo a `kuack` y
mover el pin en los `config-app*.xml`. Nunca cambiar el `id` del plugin ni sus `clobbers`: el bundle remoto lo
comparten los binarios publicados.
