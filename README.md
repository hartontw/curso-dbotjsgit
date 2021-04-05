## Visual Studio Code

1. [Descargar](https://code.visualstudio.com/)
2. Instalar

## Node.js

1. [Descargar LTS](https://nodejs.org/)
2. Instalar

## Git

1. [Descargar](https://git-scm.com/)
2. Instalar

## GitHub
1. Crear una cuenta de GitHub
2. Crear un nuevo repositorio con el nombre de vuestro bot

## Proyecto
1. Crear una carpeta con el nombre del proyecto
2. Arrastrar esta carpeta a VSC o abrirla normalmente.
3. Abrir un terminal y escribir:
```properties
npm init
```
4. Completa la información que se solicita
5. Abrir un terminal y escribir:
```properties
git init
```
6. Crea un archivo ```index.js```
7. Crea un archivo ```config.json```
8. Crea un archivo ```.gitignore```
```sh
.vscode/*
node_modules/
config.json
```

## Discord API

1. Ingresar en [Discord](https://discord.com/)
2. Acceder a la [página de aplicaciones para desarrolladores](https://discord.com/developers/applications)
3. Crear una nueva aplicación
![New app](https://poshbot.readthedocs.io/en/latest/guides/backends/discord-new-application.png)
4. Darle un nombre a la aplicación y continuar
![Name App](https://poshbot.readthedocs.io/en/latest/guides/backends/discord-add-bot-name.png)
5. Ir a la pestaña "Bot" y pulsar en "Add Bot"
![Add Bot](https://poshbot.readthedocs.io/en/latest/guides/backends/discord-add-bot.png)
6. Pulsar en el botón de copiar token (no compartas jamás tu token)
![Token](https://assets.digitalocean.com/articles/node_discord_bot/step1d.png)
7. En el archivo ```config.json``` añadir:
```json
{
    "BOT_TOKEN": "TU_TOKEN"
}
```
8. Abrir Terminal e instala la [API oficial de Discord](https://discord.js.org/)
```properties
npm install discord.js
```

10. En el archivo ```index.js``` añadir:
```js
const Discord = require("discord.js");
const config = require("./config.json");

const client = new Discord.Client();

client.on("message", function(message) {
  if (message.author.bot) return;
  
  console.log(`${message.author.username}: ${message.content}`);
});

client.login(config.BOT_TOKEN);
```
11. Ejecuta la aplicación:
```sh
node index
```
12. Accede al [panel de aplicación de Discord](https://discord.com/developers/applications/)
13. Selecciona tu aplicación, ve a la pestaña de "OAuth2" y selecciona "Bot" y "Administrator"
![OAuth2](https://assets.digitalocean.com/articles/node_discord_bot/step1e.png)
14. Copia el enlace generado y pegalo en el navegador
15. Selecciona el servidor donde quieres desplegar a tu Bot.
16. Escribe mensajes en el servidor seleccionado y observa la consola

## Guardar los cambios
1. Añade todos los archivos no excluidos
```sh
git add --all
```
2. Haz tu primer commit
```sh
git commit -m "Primer commit"
```
3. Añade tu repositorio como remoto
```sh
git remote add origin <url>
```
4. Envía tu primer commit a tu repositorio
```sh
git push origin master
```

## Útiles
- [Discord.js Docs](https://discord.js.org/#/docs/main/stable/general/welcome)
- [Guía de DigitalOcean](https://www.digitalocean.com/community/tutorials/how-to-build-a-discord-bot-with-node-js-es)
- [Mi repositorio](https://github.com/hartontw/curso-dbotjsgit)