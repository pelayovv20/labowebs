---
author: Pelayo Vázquez Vidal
módulo: Despliegue de Aplicaciones Web
---

# Ejercicio de Git - proyecto labowebs

> Pelayo Vázquez Vidal 			
>
> Despliegue de Aplicaciones Web
>
> 2ºDAW



[TOC]

## Trabajo en local

> Trabajo individual en tu ordenador - Esta parte se resuelve con comandos. Tu solución debe incluir el enunciado de cada cuestión, un bloque de código con los  comandos GIT utilizados y captura/s de pantalla donde se vea la ejecución de los  comandos y su salida.

1.  Inicializa un nuevo repositorio Git en una carpeta llamada  `"labowebs"` y agrega los  archivos proporcionados en el aula virtual. Renombra la rama master a  `main`, si es  necesario. Realiza el primer commit. Muestra el log del repositorio.

   - Añado los contenidos proporcionados y inicializo el repositorio

     ```bash
     git init
     ```

     ![image-20241114085251657](./proyecto_labowebs.assets/image-20241114085251657.png)

   - Realizo el primer commit y miro el log del repositorio

     ```bash
     git add .
     git commit -m "Commit inicial"
     git log
     ```

     ![image-20241114085438038](./proyecto_labowebs.assets/image-20241114085438038.png)

   - Renombro la rama master a main y lo compruebo

     ```bash
     git branch -M main
     git branch
     ```

     ![image-20241114085609710](./proyecto_labowebs.assets/image-20241114085609710.png)

2. Incluye un fichero  `.gitignore` para que  los ficheros  `README.md`,  `LICENCE.txt` y  `passwords.txt` sean ignorados por el control de versiones. Realiza el commit y muestra  los logs del repositorio en una línea.

   - Creo el fichero `.gitignore` para los ficheros `README.md`, `LICENSE.txt` y `passwords.txt` y realizo un commit sobre ello

     ```bash
     git add .gitignore
     git commit -m "Añadido .gitignore"
     ```

     ![image-20241114090052494](./proyecto_labowebs.assets/image-20241114090052494.png)

   - Muestro los logs del repositorio en una sola línea

     ```bash
     git log --oneline
     ```

     ![image-20241114090231986](./proyecto_labowebs.assets/image-20241114090231986.png)

3. En el repositorio, crea los archivos   `README.md`,  `LICENCE.txt` y  `passwords.txt` con  algún contenido. Muestra el estado del repositorio. Muestra el listado de archivos  ignorados.

   - Creo los archivos y los modifico. Posteriormente, observo el estado del repositorio

     ```bash
     git status
     ```

     ![image-20241114090730641](./proyecto_labowebs.assets/image-20241114090730641.png)

   - Muestro el listado de archivos ignorados

     ```bash
     git status --ignored
     ```

     ![image-20241114090936577](./proyecto_labowebs.assets/image-20241114090936577.png)

4. Crea una rama  `feature-estilos`. Cámbiate a ella.

   - Creo una rama llamada `feature-estilos` y me cambio a ella

     ```bash
     git branch feature-estilos
     git checkout feature-estilos
     ```

     ![image-20241114091232313](./proyecto_labowebs.assets/image-20241114091232313.png)

   - Modifica el archivo  `estilos.css`: 

     ​	a)	propiedad color del  `body` y de `h2`:  `#0a0a0a` 

     ![image-20241114092153584](./proyecto_labowebs.assets/image-20241114092153584.png)

     ​	b)	propiedad `background-color` de  `header` y  `footer`:  `#8892C6`

     ![image-20241114092227251](./proyecto_labowebs.assets/image-20241114092227251.png)

   - Comprueba el estado del repositorio. Añade los cambios, realiza un commit con el  mensaje "actualizados estilos a azules"

     ```bash
     git status
     git add .
     git commit -m "actualizados estilos a azules"
     ```

     ![image-20241114092105599](./proyecto_labowebs.assets/image-20241114092105599.png)

5. Vuelve a la rama  `main`. En el archivo  `index.html` añade un comentario donde se indique  tu nombre como autor de la página. Comprueba el estado del repositorio. Añade los  cambios, realiza un commit con el mensaje ' añadido autor en index'. Muestra los logs del  repositorio en una línea, gráficamente y con 'decoración'

   - Vuelvo a la rama `main` y lo compruebo

     ```bash
     git checkout main
     git branch
     ```

     ![image-20241114092352672](./proyecto_labowebs.assets/image-20241114092352672.png)

   - En el archivo `index.html` añado un comentario con mi nombre

     ![image-20241114092648124](./proyecto_labowebs.assets/image-20241114092648124.png)

   - Compruebo el estado del repositorio. Añado los cambios, realizo un commit con el mensaje "añadido autor del index"

     ```bash
     git status
     git add index.html
     git commit -m "añadido autor del index"
     ```

     ![image-20241114092914265](./proyecto_labowebs.assets/image-20241114092914265.png)

   - Muestro los logs del  repositorio en una línea, gráficamente y con 'decoración'

     ```bash
     git log --all --oneline --decorate --graph
     ```

     ![image-20241114093106112](./proyecto_labowebs.assets/image-20241114093106112.png)

6. Fusiona la rama  `feature-estilos` en la rama  `main` . Muestra los logs del repositorio en  una línea, gráficamente y con 'decoración'

   - Fusiono la rama `feature-estilos` en la rama `main`

     ```bash
     git merge feature-estilos
     ```

     ![image-20241114093241959](./proyecto_labowebs.assets/image-20241114093241959.png)

   - Muestro los logs del  repositorio en una línea, gráficamente y con 'decoración'

     ```bash
     git log --all --oneline --decorate --graph
     ```

     ![image-20241114093342141](./proyecto_labowebs.assets/image-20241114093342141.png)

## Trabajo en remoto

> Esta parte se realizará con la herramienta gráfica  Sourcetree y con  GitHub. Para cada cuestión, incluye el enunciado y las capturas de pantalla donde se muestre la  solución. Si es necesario, incluye alguna explicación 

1. Continúa con el repositorio  `labowebs`.  Añade el repositorio a Sourcetree.

   ![image-20241114093937279](./proyecto_labowebs.assets/image-20241114093937279.png)

2. Crea un repositorio remoto y sube al remoto los ficheros de tu repositorio local. Debes  subir todas las ramas.

   ```bash
   git remote add origin https://github.com/pelayovv20/labowebs.git
   git push -u origin main
   git push -u origin feature-estilos
   ```

   ![image-20241114094533130](./proyecto_labowebs.assets/image-20241114094533130.png)

   ![image-20241114094609562](./proyecto_labowebs.assets/image-20241114094609562.png)

3. Crea una rama  `feature-index`.  Añade el siguiente código dentro de la `<section class="about">`. Añade los cambios y crea un commit. Sube los cambios al remoto.

   - Creo la rama `feature-index`

     ![image-20241114095037679](./proyecto_labowebs.assets/image-20241114095037679.png)

     ![image-20241114095104033](./proyecto_labowebs.assets/image-20241114095104033.png)

   - Añado el siguiente código en el archivo `index.html` dentro de la <section class="about">.

     ![image-20241114095208713](./proyecto_labowebs.assets/image-20241114095208713.png)

   - Añado los cambios y creo un commit

     ![image-20241114095326340](./proyecto_labowebs.assets/image-20241114095326340.png)

     ![image-20241114095346307](./proyecto_labowebs.assets/image-20241114095346307.png)

   - Subo los cambios al remoto

     ![image-20241114095430407](./proyecto_labowebs.assets/image-20241114095430407.png)

     ![image-20241114095529117](./proyecto_labowebs.assets/image-20241114095529117.png)

4. En el repositorio local, fusiona la rama  `feature-index` en la rama  `main`.

   ![image-20241114095938084](./proyecto_labowebs.assets/image-20241114095938084.png)

5. Edita el fichero  `contacto.html`. Borra unas líneas. Muestra los ficheros con cambios  pendientes y las diferencias. Añade los cambios y haz un commit.

   ![image-20241114100233155](./proyecto_labowebs.assets/image-20241114100233155.png)

   ![image-20241114100250808](./proyecto_labowebs.assets/image-20241114100250808.png)

   

6. Te das cuenta del error. Deshaz el commit anterior. Captura el estado actual del  repositorio.

   ![image-20241114100446952](./proyecto_labowebs.assets/image-20241114100446952.png)

   ![image-20241114100647271](./proyecto_labowebs.assets/image-20241114100647271.png)

   ![image-20241114100702057](./proyecto_labowebs.assets/image-20241114100702057.png)

   **El estado del repositorio está vacío porque al deshacer el último commit no hay ningún cambio pendiente**

7. Crea una rama  `feature-mapa` . Incluye este código en el archivo  `contacto.html`. Añade  los cambios. Realiza un commit. Sube los cambios al remoto. Muestra en el remoto los  cambios del archivo  `contacto.html` en la rama  `feature-mapa.` 

   >  Asegurarse de que  contacto.html queda con TODAS sus líneas

   - Creo la rama `feature-mapa`

   ![image-20241114100758119](./proyecto_labowebs.assets/image-20241114100758119.png)

   - Añado el código a `contacto.html`

     ![image-20241114100954944](./proyecto_labowebs.assets/image-20241114100954944.png)

   - Añado los cambios , hago un commit y lo subo al remoto

     ![image-20241114101145435](./proyecto_labowebs.assets/image-20241114101145435.png)

     ![image-20241114101159938](./proyecto_labowebs.assets/image-20241114101159938.png)

     ![image-20241114101251122](./proyecto_labowebs.assets/image-20241114101251122.png)

     ![image-20241114101417186](./proyecto_labowebs.assets/image-20241114101417186.png)

   

8. En GitHub,  en la rama  `main`, fusiona la rama  `feature-mapa`. Baja los cambios del remoto  a local. Deja los dos repositorios sincronizados.

   - Fusiono la rama `feature-mapa` en la rama `main` mediante una pull-request

   ![image-20241115084739972](./proyecto_labowebs.assets/image-20241115084739972.png)

   ![image-20241115084800007](./proyecto_labowebs.assets/image-20241115084800007.png)

   - Miro el historial de commits. El último commit es el del fusionado

   ![image-20241115084820241](./proyecto_labowebs.assets/image-20241115084820241.png)

   - Bajo los cambios al local mediante la opción `push` en SourceTree

   ![image-20241115085242958](./proyecto_labowebs.assets/image-20241115085242958.png)

   ![image-20241115085257950](./proyecto_labowebs.assets/image-20241115085257950.png)

## Conflictos

> Esta parte se realizará con la herramienta gráfica  Sourcetree y con  GitHub. Para cada cuestión, incluye el enunciado y las capturas de pantalla donde se muestre la  solución. Si es necesario, incluye alguna explicación  

1. Crea una rama  `hotfix-js`. Cámbiate a ella. Añade este código en el fichero `script.js`  Confirma el cambio y haz un commit.  (Fíjate en los números de línea...)

   - Creo la rama `hotfix-js` y me cambio a ella

   ![image-20241115085548889](./proyecto_labowebs.assets/image-20241115085548889.png)

   ![image-20241115085525984](./proyecto_labowebs.assets/image-20241115085525984.png)

   - Añado el código al fichero `script.js`

   ![image-20241115085707338](./proyecto_labowebs.assets/image-20241115085707338.png)

   - Confirmo el cambio y hago un commit

     ![](./proyecto_labowebs.assets/image-20241115085819996.png)

     ![image-20241115085922836](./proyecto_labowebs.assets/image-20241115085922836.png)

     ![image-20241115090142058](./proyecto_labowebs.assets/image-20241115090142058.png)

     

2. Vuelve a la rama  `main`. En el fichero  `script.js` en las mismas líneas que en la cuestión  anterior, añade el código siguiente. Confirma el cambio y haz un commit.

   - Añado el código en el archivo `script.js` desde la rama `main`

   ![image-20241115090340332](./proyecto_labowebs.assets/image-20241115090340332.png)

   - Confirmo cambios y hago un commit

   ![image-20241115090449006](./proyecto_labowebs.assets/image-20241115090449006.png)

   ![image-20241115090503394](./proyecto_labowebs.assets/image-20241115090503394.png)

   ![image-20241115090606551](./proyecto_labowebs.assets/image-20241115090606551.png)

3. Fusiona la rama  `hotfix-js` en  `main`. Debe producirse un conflicto. Resuélvelo. Cuando  termines la resolución del conflicto sube los cambios al remoto - Deja los repositorios  sincronizados

   - Fusiono las ramas 
   - Hago click derecho en el archivo, resolve Conflicts y resolve Using Theirs. (ya lo habíoa hecho por eso ahora no me deja)

   ![image-20241115091555496](./proyecto_labowebs.assets/image-20241115091555496.png)

   - Hago el commit y lo subo al remoto

   ![image-20241115091715800](./proyecto_labowebs.assets/image-20241115091715800.png)

   ![image-20241115091736339](./proyecto_labowebs.assets/image-20241115091736339.png)

## Subida de documentación

- Creo la carpeta `docs` e introduzco el archivo .md, la carpeta de imágenes y el pdf final

  ![image-20241115093007868](./proyecto_labowebs.assets/image-20241115093007868.png)

- Lo llevo al remoto

  ```bash
  git push -u origin main
  ```

  ![image-20241115093119258](./proyecto_labowebs.assets/image-20241115093119258.png)

  ![image-20241115093133252](./proyecto_labowebs.assets/image-20241115093133252.png)

> URL del repositorio: https://github.com/pelayovv20/labowebs.git
