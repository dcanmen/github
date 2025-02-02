# Práctica git & github

Esta práctica consta principalmente de 2 ejecicios, que están explicados en el fichero (Práctica git y github.pdf) que encontrareis en este repositorio, además de la solución detallada de su resolución (Solución Práctica git y github.pdf)

Además, se deben responder a unas serie de preguntas dentro de este fichero que sirve de respuesta a la práctica para el profesor. 

A continuación se detallan las preguntas que se deben responder y su respuesta.

## Ejercicio 1

1. ¿Qué comando utilizaste en el paso 11? ¿Por qué?
   
   Comando

   ```
   git reset --hard HEAD~1
   ```

   >Este comando nos permite volver al commit anterior, pero hay que tener en cuenta que perderemos todos los cambios del working copy hechos a partir de ese commit. .

2. ¿Qué comando o comandos utilizaste en el paso 12? ¿Por qué?
   
   Comando

   ```
   git reflog
   ```

   >Permite identificar el hash de todos los commits, y así poder identificar cual fue el commit que deshicimos en el paso anterior. Una vez identificado el id del commit que queremos re-establecer, ejecutamos el siguiente comando:

   ```
   git reset --hard <id>
   ```
   >El motivo de usar este comando es para volver a situar nuestro HEAD del repositorio en el commit que estaba antes de moverlo en el paso anterior usando HEAD~1

3. El merge del paso 13, ¿Causó algún conflicto? ¿Por qué?
   
   Comando

   ```
   git branch
   ```

   >Comprobamos que estamos en la rama activa "styled" y ejecutamos el comando de merge.

   Comando
   ```
   git merge main
   ```

   >No causado ningún conflicto porque no había modificaciones que colisionaran con los cambios realizados en styled.

4. El merge del paso 19, ¿Causó algún conflicto? ¿Por qué?
   
    Comandos

    ```
    git checkout styled
    ```

    > Nos cambiamos a la rama styled desde la rama htmlify

    ```
    git merge htmlify
    ```

    > Ejecutamos el comando merge, y nos dice que tenemos conflictos que resolver, que los resolvamos y luego ejecutemos un commit.
    > El motivo por el que genera conflicto es porque la versión del fichero git-nuestro.md que existe en styled es diferente al que existe en htmlify en las mismas lineas.

5. El merge del paso 21, ¿Causó algún conflicto? ¿Por qué?
6. ¿Qué comando o comandos utilizaste en el paso 25?
7. El merge del paso 26, ¿Podría ser fast forward? ¿Por qué?
8. ¿Qué comando o comandos utilizaste en el paso 27?
9.  ¿Qué comando o comandos utilizaste en el paso 28?
10. ¿Qué comando o comandos utilizaste en el paso 29?
11. ¿Qué comando o comandos utilizaste en el paso 30?
12. ¿Qué comando o comandos usaste en el paso 32?
13. ¿Qué comando o comandos usaste en el punto 33?