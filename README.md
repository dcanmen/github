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
   
   Comandos

   ```
   git checkout main
   ```

   > Cambiamos a la rama main con el comando anterior

   ```
   git merge styled
   ```

   > Hacemos merge de la rama main con styled

   > No ha causado conflictos, pero si indica que hay bastantes cambios tanto en el fichero README.md como en el fichero git-nuestro.md, y el motivo de que no haya conflictos es porque main está en el repositorio y hemos cambiado el local.
   
6. ¿Qué comando o comandos utilizaste en el paso 25?

   Comando
   ```
   git log --graph
   ```
   > Este comando nos dibuja el gráfico de las ramas y commits, pero en un formato muy extenso. Que en nuestro caso es entendible, pero si tuvieramos cientos miles de commits y algunas ramas más, no sería comodo de ver.

   Comando
   ```
   git log --graph --decorate --pretty=oneline
   ```
   > Utilizando el comando anterior obtenemos una forma reducida del gráfico y mas entendible.

7. El merge del paso 26, ¿Podría ser fast forward? ¿Por qué?

   Comando
   ```
   git merge --no-ff title
   ```
   > Este merge no fast-forward lo que ha hecho es generar un nuevo commit en la rama main que absorve el trabajo realizado en la rama title.

   > Si podría haber sido un fast-forward porque la rama title nacía en el HEAD o último commit de la rama main, pero en este caso hubieramos movido el HEAD al último commit de la rama title.

8. ¿Qué comando o comandos utilizaste en el paso 27?

   Comando
   ```
   git reset HEAD~1
   ```
   > Este comando mueve el HEAD al commit anterior de la rama main. Ese commit era anterior al merge con no fast forward realizado anteriormente. Además este comando no modifica el contenido del working copy que es el mismo que teniamos despues de hacer el merge de la rama title en main. 

   > Podemos utilizar el comando *git log* para comparar los commits antes y despues del comando para garantizar que hace lo que hemos explicado en el párrafo anteior.

9.  ¿Qué comando o comandos utilizaste en el paso 28?

    Comando
    ```
    git restore git-nuestro.md
    ```

    > Este comando reestablece la versión almacenada en el commit HEAD de la rama main, eliminado de la copia local (working copy) el título añadido al fichero en la rama title previamente.

    > Adicionalmente podemos utilizar el comando *git status* antes de ejecutar el restore para entender en que area (working o staging) tenemos que hacer el cambio. En mi caso el fichero estaba en el working copy.
    
10. ¿Qué comando o comandos utilizaste en el paso 29?
    
    Comando
    ```
    git branch -D title
    ```
    > Se ejecuta el comando desde la rama main.

    > Se puede comprobar que la rama se elimina usando el comando *git branch* antes y despues de la ejecución del comando anterior, para comparar los resultados.

11. ¿Qué comando o comandos utilizaste en el paso 30?
    
    Comando
    ```
    git reflog
    ```
    > Con este comando mostramos los identificadores de los commits y acciones realizadas en el repositorio, permitiendo encontrar el punto exacto al que se quiere regresar.

    Comando
    ```
    git reset --hard <id>
    ```
    > Este comando nos permite volver al punto donde se hizo el merge de la rama title con la rama main. En mi caso el id es dd343ce. 

    > Se comprueba que el fichero git-nuestro.md tiene el título después de la ejecución del comando. Verificando que volvemos a tener el repositorio en el punto que necesitamos, justo despues del merge de las dos ramas.

12. ¿Qué comando o comandos usaste en el paso 32?
    
    Comando
    ```
    git reflog
    ```
    > Buscamos cual es el id del commit inicial para usarlo en el comando que nos permite mover el repositorio a la posición inicial.

    Commando
    ```
    git reset --hard <id>
    ```
    > Podemos comprobar que el fichero git-nuestro.md es el original y no el modificado que hicimos en la rama title que era el actual antes del comando.

13. ¿Qué comando o comandos usaste en el punto 33?
    
    Comando
    ```
    git reflog
    ```
    > Buscamos cual es el id del commit al que queremos volver, en este caso al merge de title con main.

    Comando
    ```
    git reset --hard <id>
    ```
    > Comprobamos que tenemos el último fichero git-nuestro.md con el título añadido. Podemos usar cat para verificar el contenido del fichero.

## Ejercicio 2

Hemos realizado los siguientes pasos:

1. Realizar un fork del repositorio https://github.com/kasappeal/nerdquotes.git
2. Clonar el repositorio a local de mi fork (mi cuenta de github)
3. Editar el fichero README.md para añadir una cita friki en mi repositorio local
4. Hacer commit y push de los cambios a mi repositorio (fork) de mi cuenta
5. Solicitar pull request al repositorio original (resolver conflictos si los hubiera)