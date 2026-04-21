# Recuperación de archivo borrado con Git

## Error simulado

Borré el archivo `errores.sh` usando `git rm` y lo confirmé con un commit.
Esto simula lo que pasa cuando alguien borra un archivo sin querer y encima
hace commit del cambio.

## Comandos usados

```bash
git rm errores.sh
git commit -m "Borrado accidental de errores.sh"
git reflog
git checkout HEAD~1 -- errores.sh
git add errores.sh
git commit -m "Recupero errores.sh tras borrado accidental"
```

## Qué aprendí

El `reflog` guarda todos los movimientos del repositorio aunque no aparezcan
en `git log` normal. Con `git checkout HEAD~1 -- archivo` puedes recuperar
un archivo concreto de un commit anterior sin tocar el resto del historial.
