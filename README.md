# Prueba Desarrollo de interfaces interactivas con framework Vue

## Descripción

Entre los capítulos de Pokémon aparecía un momento de interacción con los espectadores
donde se debía adivinar el nombre de un pokemon viendo solo la silueta.
La aplicación que deberás construir sigue esta misma temática mostrando 20 pokemones
cuyas imágenes poseen en primera instancia un filtro que no deja ver con claridad cuál
pokémon es.

Para que el usuario intente descubrir y adivinar cada pokémon deberás permitir el ingreso de
su nombre por medio de un input debajo de cada una de las imágenes.

Al presionar en el botón “Descubrir” o simplemente apretar la tecla Enter, en caso de que el
usuario haya escrito correctamente el nombre del pokémon deberá descubrirse quitando el
filtro aplicado por defecto, de lo contrario se debe mostrar una ventana emergente indicando
que el nombre ingresado es incorrecto.

Al descubrir un pokémon se deben tomar 2 consideraciones:

1. Ocultar el input y el botón y dejar el nombre del pokémon descubierto
2. Mostrar un contador con la cantidad de pokémons descubiertos hasta el momento.
