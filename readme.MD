##Step by step to deploy an app in heroku

* git init
* añadir el `index.js`, `package.json` & `Procfile`
  * En el Procfile tiene que estar el script que se lanzará `web: node index.js`
  * EN el `package.json` tienen que estar:
    * La versión de node:
    ```javascript 
    "engines": {
      "node": "4.4.3"
    },
    ```
    * Las dependencias que emplea el código:
    ```javascript 
    "dependencies": {
      "express": "4.13.3"
    },
    ````
    En caso de no tenerlas en el `pachage.json` tendremos que añadirlas con el comando(en este ejemplo para `express`: `npm install express --save`
* Corremos el comando `npm init` para isntalar los paquetes, se creará el directorio de `node_modules`
* Chekeamos que funciona en local con `heroku local`
* Creamos en `.gitignore` para no subir lo módulos al repo
* Creamos y enviamos la aplicación a *Heroku*
  * `git add .`
  * `git commit -m "master commit"`
  * `heroku login`
  * `heroku create` Aquí podemos añadir el nombre de la app si queremos un concreto: `heroku create my-app`
  * `git push heroku master`
* `heroku open`