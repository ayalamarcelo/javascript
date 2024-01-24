# Pasos para forkear el repositorio

1. Fork del repositorio:
   * Haz click en el botón "Fork" en la esquina superior derecha de github.
   * Esto creará una copia del repositorio en tu cuenta.
2. Clonar el repositorio forkeado:
   * Copia la URL de tu repositorio forkeado. Podes encontrar la URL en tu repositorio forkeado, a la derecha, en el botón verde "Code".
   * Abre tu terminal y navega al directorio donde deseas clonar el repositorio.

```bash
git clone <URL_de_tu_repositorio_forkeado>
```
## Mantener tu repositorio actualizado:

1. Actualizar tu repositorio con los cambios del repositorio original:
   * Antes de realizar cambios, siempre es recomendable actualizar tu repositorio local.
  
```bash
git pull
```
Esto fusionará los cambios más recientes del repositorio original a tu rama local.

```bash
git merge
```
## Realizar cambios y contribuciones
1. Crear una rama para tus cambios:

```bash
git checkout -b nombre_de_tu_rama
```
2. Realizar cambios y commits:

```bash
git add .
git commit -m "Descripción de tus cambios"
```
3. Subir cambios a tu repositorio forkeado:

```bash
git push origin nombre_de_tu_rama
```
4. Crear una pull request:
   * Ir a repositorio forkeado en github.
   * Cambiar a la rama que creaste.
   * Click en "Compare & pull request" para crear una pr.
  
```bash
git branch nombre_de_la_rama
```