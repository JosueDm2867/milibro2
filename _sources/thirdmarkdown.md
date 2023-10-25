# Acciones con GitHub

![Plotting](github.jpg).

Una vez que tu contenido esté en GitHub, puedes alojarlo fácilmente como un sitio web de GitHub Pages. Este es un servicio en el que GitHub aloja tus archivos estáticos como si fueran un sitio web independiente.

Hay tres maneras de alojar rápidamente tu libro con GitHub Pages:

 1.Copia y pega el código HTML de tu libro en una carpeta o en una rama de tu repositorio.`docs/` `gh-pages`
 
 2.Utilice la herramienta para enviar automáticamente la documentación compilada a una rama.`ghp-import` `gh-pages`
 
 3.Usa una GitHub Action para compilar automáticamente tu libro y actualizar tu sitio web cuando cambies el contenido.

## Subir manualmente tu libro en linea 

Utilice la herramienta para enviar automáticamente la documentación compilada a una rama.ghp-importgh-pages

### OPCION 1

 1. Copie el contenido del directorio en (o en su otra rama).`_build/html` `docs`

 2.Agregue un archivo llamado junto con el contenido de su libro. Esto le dice a GitHub Pages que trate tus archivos como un "sitio web HTML estático".`.nojekyll`

 3.Inserte los cambios en GitHub y [configúrelo para empezar a hospedar la documentación](https://docs.github.com/en/github/working-with-github-pages).


### OPCION 2

La forma más fácil de usar GitHub Pages con tu HTML compilado es usar el paquete. es un paquete ligero de Python que facilita la inserción de contenido HTML en un repositorio de GitHub.`ghp-import`

 1.Instalar `ghp-import`
 ```
 pip install ghp-import
 ```
 2.Desde la rama del directorio raíz de tu libro (que debe contener la carpeta) llámalo y apúntalo a tus archivos HTML, de la siguiente manera:`master`  `_build/html` `ghp-import`


### OPCION 3

**Hospeda automáticamente tu libro con GitHub Actions**

Para compilar tu libro con GitHub Actions, tendrás que crear Una acción que hace lo siguiente:

 1. Se activa cuando se produce un evento de inserción en (o lo que sea) tiene el contenido de su último libro.`master`

 2.Instala Jupyter Book y las dependencias necesarias para compilar tu libro.

 3.Crea el HTML de tu libro.

 4.Utiliza una acción para cargar ese código HTML en la rama.`gh-pages` `gh-pages`


```{tip}
Puedes usar el cortador de cookies de Jupyter Book para crear rápidamente una plantilla de libro que ya incluya el archivo de flujo de trabajo de GitHub Actions necesario para implementar automáticamente tu libro en GitHub Pages:
 ```
 ```
jupyter-book create --cookiecutter mybookpath/

```


```{tip}
Puede ejecutar el comando `help ()`en su cuaderno para obtener asistencia interactiva sobre los comandos de Jupyter. Para obtener más información sobre un objeto en particular, puede usar **ayuda (objeto) .**
```