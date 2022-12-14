[![Abre en GitHub Codespaces](https://github.com/codespaces/badge.svg)](https://github.com/codespaces/new?hide_repo_select=true&ref=main&repo=526669888)

# Plantilla de Python en Codespaces

_Crea o amplia un repositorio listo para usar para ense帽ar Python en minutos_

Con esta plantilla puedes crear r谩pidamente un entorno normalizado para ense帽ar o aprender Python. Haz que tus estudiantes se centren en su aprendizaje en lugar de configurar su entorno. Esta plantilla utiliza Codespaces, un entorno de desarrollo alojado en la nube con [Visual Studio Code](https://visualstudio.microsoft.com/?WT.mc_id=academic-77460-alfredodeza), un poderoso editor de texto.

<details>
   <summary><b>馃帴 Ve el video tutorial para obtener m谩s informaci贸n sobre Codespaces</b></summary>
   
   [![Codespaces Tutorial](https://img.youtube.com/vi/ozuDPmcC1io/0.jpg)](https://aka.ms/CodespacesVideoTutorial "Codespaces Tutorial")
</details>

馃殌 Caracter铆sticas de Codespaces:

- Entorno de nube repetible que ofrece una experiencia incre铆ble.
- Se puede configurar y personalizar.
- Se integra con sus repositorios en GitHub y [VSCode](https://visualstudio.microsoft.com/?WT.mc_id=academic-77460-alfredodeza)

Como profesor, eso significa que puede crear un entorno, en la nube, para que en su clase todos los estudiantes puedan usar una configuraci贸n cero o casi nula, independientemente del sistema operativo que est茅n utilizando.

## Personalizaci贸n

Personaliza tu proyecto para GitHub Codespaces al confirmar archivos de configuraci贸n en tu repositorio (a menudo conocido como _Configuration-as-Code_), lo que crea una configuraci贸n repetible de Codespaces para todos los usuarios de tu proyecto.

Puedes configurar:

- Extensiones, puedes especificar qu茅 extensiones deben estar preinstaladas.
- Dotfiles y configuraciones.
- Bibliotecas y dependencias del sistema operativo.

> 馃挕 M谩s informaci贸n sobre [personalizaci贸n y configuraci贸n en la documentaci贸n oficial](https://docs.github.com/en/codespaces/customizing-your-codespace/personalizing-github-codespaces-for-your-account)


## Plantilla de Codespaces

Este repositorio es una plantilla de GitHub, la cual contiene lo siguiente:

- [example-notebook.ipynb](./example-notebook.ipynb), Este notebook utiliza la librer铆a [Pandas](https://pandas.pydata.org/) para ense帽ar operaciones b谩sicas con un peque帽o archivo CSV (_Comma Separated Value_) [dataset](./wine-regions.csv)
- [.devcontainer/Dockerfile](./.devcontainer/Dockerfile), para que pueda configurar qu茅 sistema operativo utilizar谩 el Codespace y c贸mo se debe construir el contenedor.
- [.devcontainer/devcontainer.json](./.devcontainer/devcontainer.json), Un archivo de configuraci贸n utilizado por Codespaces para configurar [Visual Studio Code](https://visualstudio.microsoft.com/?WT.mc_id=academic-77460-alfredodeza), por ejemplo, para agregar y habilitar una extensi贸n.
- `README.md`. Este archivo describe este repositorio y lo que contiene.

### 馃攷 驴Ha encontrado un problema o tienes una idea para mejorarlo?
Ay煤danos a mejorar este repositorio al [hacernos lo saber y abriendo un issue!](/../../issues/new). 

## 馃 隆Pru茅balo!

Prueba este repositorio de plantillas con Codespaces siguiendo estos pasos:

1. Crea un repositorio desde esta plantilla. Utiliza este link [crea un repositorio](https://github.com/microsoft/codespaces-teaching-template-py/generate)
1. Ve a la p谩gina principal del repositorio reci茅n creado.
1. Debajo del nombre del repositorio, usa el men煤 desplegable C贸digo y, en la pesta帽a Codespaces, selecciona "Crear Codespace en main".
   ![Crea un codespace](https://docs.github.com/assets/cb-138303/images/help/codespaces/new-codespace-button.png)
1. Se empieza a crear tu Codespace

   ![Creando el codespace](./images/Codespace_build.png)


### Inspeccionar el entorno de Codespaces

Lo que tienes en este momento es un entorno preconfigurado donde todos los tiempos de ejecuci贸n y bibliotecas que necesitas ya est谩n instalados - esto es una experiencia de configuraci贸n cero.

Tambi茅n tienes un Jupyter Notebook que puedes comenzar a usar sin ninguna configuraci贸n.

> Este entorno se ejecutar谩 independientemente de si tus estudiantes est谩n en Windows, macOS o Linux.

Abre tu archivo Jupyter Notebook [example-notebook.ipynb](./example-notebook.ipynb) y observa c贸mo puedes agregar c贸digo y ejecutarlo.

## Personaliza tu Codespace

Hagamos cambios en tu entorno. Cubriremos dos desaf铆os diferentes que es probable que desees hacer:

1. Cambiar la versi贸n de Python instalada
1. Agregar una extensi贸n


### Paso 1: Cambiar el entorno de Python

Digamos que deseas cambiar la versi贸n de Python que est谩 instalada. Esto es algo que puedes controlar.

Abre [.devcontainer/devcontainer.json](./.devcontainer/devcontainer.json) y reemplaza la siguiente secci贸n:

```json
"VARIANT": "3.8-bullseye"
```

con las siguientes instrucciones:

```json
"VARIANT": "3.9-bullseye"
```

este cambio usar谩 Python 3.9 en lugar de 3.8.

### Paso 2: A帽ade una extensi贸n

Tu entorno viene con extensiones preinstaladas. Puedes cambiar con qu茅 extensiones comienza tu entorno de Codespaces, a continuaci贸n, te indicamos c贸mo:


1. Abre el archivo [.devcontainer/devcontainer.json](./.devcontainer/devcontainer.json) y busca el siguiente elemento JSON **extensions**:

   ```json
   "extensions": [
    "ms-python.python",
    "ms-python.vscode-pylance"
   ]
   ```

1. Agrega _"ms-python.black-formatter"_ a la lista de extensiones. Deber铆a terminar pareci茅ndose a lo siguiente:

   ```json
   "extensions": [
    "ms-python.python",
    "ms-python.vscode-pylance",
    "ms-python.black-formatter"
   ]
   ```

   Lo que hiciste anteriormente fue agregar el identificador 煤nico de una extensi贸n de Python [Black Formatter](https://marketplace.visualstudio.com/items?itemName=ms-python.black-formatter&WT.mc_id=academic-77460-alfredodeza). Esto permitir谩 a Codespaces saber que esta extensi贸n debe estar preinstalada al iniciarse.

   Recuerda: Cuando cambies cualquier configuraci贸n en el json, aparecer谩 un cuadro despu茅s de guardar.

   ![Recreando codespace](./images/Codespace_rebuild.png)

   Haz clic en reconstruir. Espera a que el espacio de c贸digo vuelva a generar el entorno de VS Code.

Para encontrar el identificador 煤nico de una extensi贸n:

- Ingresa a la p谩gina web de la extensi贸n, por ejemplo [https://marketplace.visualstudio.com/items?itemName=ms-python.black-formatter](https://marketplace.visualstudio.com/items?itemName=ms-python.black-formatter&WT.mc_id=academic-77460-alfredodeza)
- Localiza el campo *Unique Identifier* bajo la secci贸n **More info** en tu lado derecho.


## Aprende m谩s

- [GitHub Codespaces docs - Visi贸n general](https://docs.github.com/en/codespaces/overview)
- [GitHub Codespaces docs - Comienza rapido](https://docs.github.com/en/codespaces/getting-started/quickstart)

