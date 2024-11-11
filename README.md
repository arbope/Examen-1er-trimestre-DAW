# Aron Bou
## _Examen primer trimestre DAW_

- Parte 1: Realiza el test asignado (3 puntos).

- Parte 2: SSH + Command line (3 puntos).

- Parte 3: Virtualhost (2 puntos).

- Parte 4: Documentación + Github (2 puntos).

## **Parte 1:**  
 He buscado ciertas preguntas en los apuntes, stackoverflow o probandolas yo mismo en la terminal como
 por ejemplo el comando de  _time who -p %e_
 
## **Parte 2:**
 Para conectarme a la máquina remota del profesor mediante ssh he tirado el siguiente comando: sudo ssh usuario@(IP.DEL.PROFESOR)..
![ssh](https://i.imgur.com/BG7Hr8z.png)
 A continuación nos pedira la contraseña de nuestro usuario:
![pass](https://i.imgur.com/EZC1fc8.png)
 Tras eso nos dirá que la autentificación del host no ha podido establecerse, por defecto diremos que queremos continuar conectandonos igualmente escribiendo _' yes '_
![host](https://i.imgur.com/hTLHQbO.png)
 Posteriormente nos pedirá la password del host al que nos conectarmos, tras introducirla, ya estaremos dentro de la máquina virtual del profe ^^
![conection](https://i.imgur.com/ZsEg2kX.png)
 Para ir al escritorio nos bastará con escribir en la terminal _' cd Escritorio '_, o _' cd escritorio '_ o _' cd Desktop '_, para no probar los tres, podemos tirar un _' ls '_ antes y comprobar cómo es que se llama dicha carpeta en el host. 
 En este caso el nombre era Escritorio, por lo tanto con _' cd Escritorio '_ accedemos al escritorio, ojo porque es case sensitive y por lo tanto si la _' E '_ no la ponemos en mayúsculas no nos lo interpreta correctamente.
 ![desktop](https://i.imgur.com/2v2jjd5.png)
 Ahora hemos de crear un (miNombre).txt en el escritorio con el contenido del comando _' whoami '_ y del comando _' who '_..
 Vamos a ello!
 Empezamos tirando el comando _' whoami '_, que nos dice quienes somos, por lo tanto al estar conectados virtualmente a el host usuario, nos saca usuario:
 ![ususario](https://i.imgur.com/TZBaxDv.png)
 Creamos el archivo con mi nombre mediante el comando _' cat > (nombreArchivo.extension)'_ 
 ![cat](https://i.imgur.com/mdmYsKr.png)
 Le añadimos el texto del comando con _' whoami >> (nombreArchivo.extension)'_ :
 Y con el mismo comando concatenamos el output de _' who '_ que nos dirá quienes se encuentran conectados al host virtual, _' who >> (nombreArchivo.extension)'_ :
 ![catOutput](https://i.imgur.com/b8LfF5r.png)
 Entonces ahí tendríamos el output de ambos comandos. El del comando _' whoami '_ que nos dice quienes somos y el del comando _' who '_ quienes se encuentran conectados.
 

## **Parte 3:**
En esta parte crearemos un virtualHost: **l e t 's G o** 
Lo primero será crear el directorio dónde alojaremos los archivos que posteriormente serviremos, esto lo haremos dirigiedonos a _' /var/www '_ y tirando el _' comando sudo mkdir (nuestroDirectorio) '_

![www](https://i.imgur.com/QbksVev.png)
![mkdir](https://i.imgur.com/vEOP1OR.png)

A continuación creamos un archivo _' index.html '_ dentro del directorio de la web que hemos creado:
![index.html](https://i.imgur.com/l1ZKzKD.png)
Con este comando se nos abrirá el editor de texto VIM mediante el cual podremos introducir el contenido de nuesto index.html, en el cual pondremos algo sencillo, una estructura estándar de HTML5.
>  GNU nano 6.2                       index.html                                 
> <html>
>   <head>
>        <title>Welcome to Pepeland!</title>
>    </head>
>    <body>
>        <h1>Success!  The holy grail is near!</h1>
>    </body>
> </html>

![VIM](https://i.imgur.com/XdnYo1Y.png)
Ahora nos dirigimos a _' /etc/apache2/sites-available/ '_ y creamos un archivo de configuración que se llame _' miWeb.conf '_ 

![sites](https://i.imgur.com/QKaTouc.png)
![miWeb.conf](https://i.imgur.com/jxUByis.png)
Con este comando nos abrirá nuevamente el editor de VIM en el cual introduciremos la estructura básica para configurar nuestro host virtual:
![VIM2](https://i.imgur.com/nJ3oVTz.png)
En _' ServerAdmin '_ pondremos nuestro correo, en _' ServerName '_ un nombre, en _' ServerAlias '_ el dominio web y en _' DocumentRoot '_  la ruta en la que se encuentra el archivo _.conf_ de nuestra página Web, creado previamente.

Ahora pondremos dentro de /etc/hosts nuestra ip conjunto a nuestro dominio de web
![etc](https://i.imgur.com/6BcoEtV.png)

De esa forma al introducir en nuestro navegador el dominio de nuestra página, nos abrira el index.html:
![html](https://i.imgur.com/R9bit00.png)


## **Parte 4:** **WIP ;)**

[![repo](https://i.imgur.com/iJHli1s.png)](https://github.com/arbope/Examen-1er-trimestre-DAW)

