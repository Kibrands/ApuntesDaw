## Unidad 6: Documentación y Control de versiones

## Índice
--- 
- ### Introducción
- ### Documentación con Markdown
- ### Control de versiones con git

## Introducción


### En esta Unidad aprenderemos a

- Identificar diferentes herramientas de generación de documentación.
- Utilizar diferentes formatos para la documentación.
- Utilizar herramientas colaborativas para la elaboración y mantenimiento de la documentación.
- Instalar, configurar y utilizar un sistema de control de versiones.



## Documentación con Markdown


### Cabeceras

```markdown
# Esto es una cabecera de nivel 1
## Esto es una cabecera de nivel 1
###### Esto es una cabecera de nivel 6
```


### Listas sin orden

```markdown
* Item 1
* Item 2
 * Item 2a
 * Item 2b
```


### Lista con orden

```markdown
1. Item 1
2. Item 2
3. Item 3
 * Item 3a
 * Item 3b
```


### Formato

```markdown
*Este texto se muestra en itálica*
_Este también se mostrará en itálica_

**Este texto se muestra en negrita**
__Este también se mostrará en negrita__

*Puedes **combinar** ambos formatos*
```


### Enlaces

```markdown
http://github.com - automático

[GitHub](http://github.com)
```


### Imágenes

```markdown
![GitHub Logo](/images/logo.png)

Formato: ![Texto alternativo](url)
```


### Citas

```markdown
Como dijo Grace Hopper:

> I’ve always been more interested
> in the future than in the past.
```


### Código fuente

<pre>
```javascript
var s = "Lenguaje javascript. Se realizará coloreado de sintaxis.";
alert(s); 
```

```python
s = "Lenguaje Python. Se realizará coloreado de sintaxis."
print s
```

```
No se indica lenguaje. No se realizará coloreado de sintaxis. 
```
</pre>


### Menciones y Referencias
- Menciones a usuarios:  ** @usuario **

- Referencias a Issues y Pull request:  **  #numero ** 



## Control de versiones con git


### Instalación de git

```bash
sudo  apt  install  git
```


### Configuración de git

```bash
git  config  --global  user.name   "Nombre y Apellidos"
git  config  --global  user.email  "nombre@mail.com"
```


### Iniciar repositorio local

```bash
git  init
```

- Es recomendable crear un archivo `.gitignore` con listado de carpetas y archivos a los que no se realizará seguimiento.


### Comandos básicos

```bash
git  status
git  add .
git  commit -m  "Mensaje"
```


### Clonar repositorio remoto 

```bash
git  clone   https://github.com/usuario/repositorio.git
git  clone   git@github.com:usuario/repositorio.git
```


### Vincular y desvincular repositorio remoto

```bash
git  remote  -v
git  remote  add  origin  https://github.com/usuario/repositorio.git
git  remote  rm   origin
```


### Bajar y subir contenido a repositorio remoto

```bash
git  pull  origin  master  // bajar commits
git  push  origin  master  // subir commits
```


###  Trabajo con ramas

```bash
git  branch    -va        // listado verbose, all (local y remoto)

git  branch    nuevo      // creación de rama
git  checkout  nuevo      // cambiar a dicha rama

git  checkout  -b nuevo   // equivalente a las 2 sentencias anteriores
```


### Checkout

- El comando **`checkout`** de `git` sirve para **cambiar de rama**.

```bash
git  checkout  rama
```

- También sirve para **cambiar de commit dentro de una rama**.

```bash
git  checkout  0f82
```


### Etiquetas de anotación

```bash
git tag -l                          // Listado
git tag -a v1.0 -m "Version 1.0"    // Añadir etiqueta
git tag -d v1.0                     // Eliminar etiqueta
```

- Las etiquetas deben enviarse explícitamente al repositorio remoto:

```bash
git  push  --tags
```
