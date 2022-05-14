<h1 align="center">OCEAN FRIEND FRONT</h1>

**OceanFriend Frot** es la UI que consumira los servicios de la API [OceanFriend Frot](https://github.com/GabrielaEsquivel/ocean_friend_api)

## Caracteristicas

Este proyecto fue contruido con VueJs 3 pensando en la separación de responsabilidades, TDD y Style Guide para crear un código consistente y escalable.

- VUE3 CLI
- TDD: Jest
- ESLint + StandardJS
- ES6
- Git
- SASS
- RWD

## Instalación del proyecto

Pasos para descarga el proyecto en tú PC:
1. Abre una terminal (cmd, windows bash (wsl), etc.) en la ruta que desees guardar el proyecto.
2. Ok, una vez estés en la raíz del proyecto, escribe el siguiente comando para descargar el proyecto: `git clone url-del-repositorio-github`.
3. El sig. comando descargará los paquetes necesarios para el correcto funcionamiento del proyecto: `npm install`.
4. Para verificar que el proyecto se instaló correctamente, ejecuta el sig. comando: `npm run serve`.

**Nota**: La terminal siempre debe apuntar a la ubicación del proyecto para ejecutar correctamente los comandos anteriores.

## Antes de hacer un commit

Antes de hacer un commit y antes de subir tus cambios nuevos verifica que tu código no tenga errores de estilo ejecutando el sig. comando: `npm run lint`. Si todo esta correcto has commit y push.

## Siempre manten actualizado tu repo local

Importante, cada vez que se haga un cambio al proyecto en este repositorio, deberás bajar dicho cambio a tu máquina local, tú PC, y así obtener la última versión del proyecto. Recuerda es mejor prevenir que lamentar en el futuro, pueden ocurrir cosas raras.

Entonces, antes de empezar a codear lo primero que debes hacer al abrir el proyecto en VSCode es:

- *git pull*: Actualizara el proyecto local con los utlimos cambios en el repo.
- *npm install*: Actualiza las dependencias en el package.json.
