Realizadas ampliaciones 1, 2, 3 y 5

Ampliación 1:

Se ha añadido una nueva blueprint class llamada BP_Skeleton que representa un nuevo tipo de enemigo.
Tiene mayor velocidad que el cactus y además cuenta con animación al moverse. Se ha utilizado un blend space de 1 dimensión para ello ya que
la animación a usar va a depender solo de la velocidad del enemigo. El comportamiento es homólogo al cactus ya que usa la misma AI controller
class y los proyectiles le afectan de la misma forma.
También se ha modificado BP_EnemyGenerator para que genere el nuevo tipo enemigo. Por cada 3 cactus generará 1 esqueleto.

Ampliación 2:

En BP_Cowboy se ha creado una variable Ammo que representa la munición actual del jugador. Si esta es menor que 0, el jugador no puede disparar.
También se ha creado la widget blueprint WBP_Ammo para que el jugador pueda ver cuánta munición le queda.

Ampliación 3:

Para poder recargar la munición se han de recoger unas cajas que sueltan los esqueletos al matarlos. Estas cajas están representadas por
BP_AmmoBox. Al pasar por encima el jugador recarga 5 de munición.

Ampliación 5:

El jugador ahora dispone de granadas. Se lanzan con la tecla 'E', son infinitas y tienen un cooldown de 3 segundos.
Se han creado las bluepprint class BP_Grenade y BP_Explosion, que representan la granada y la explosión respectivamente.
Cuando la granada haga overlap con algún enemigo, esta hara spawn de una explosión. La explosión cuenta con una amplia cápsula de colisiones,
y todos los enemigos que hagan overlap con ella serán eliminados, es decir, la granada hace daño en área. También tiene gravedad y menor
velocidad que los disparos normales.
Se ha añadido un nuevo componente arrow en BP_Cowboy que representa la trayectoria de disparo de la granada. Para diferenciarla de las 
flechas del disparo estándar se le ha asignado un tag diferente. El spawn de la granada se lleva a cabo en BP_ShootingComponent de la misma
forma que con los disparos normales, pero en get component by tag se especifica el tag de la arrow de la granada.