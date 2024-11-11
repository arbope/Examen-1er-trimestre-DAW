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

[![N|Solid](data:image/jpeg;base64,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)](https://github.com/arbope/Examen-1er-trimestre-DAW)

# Examen-1er-trimestre-DAW
