## Juego de clicks

mi proyecto presenta un juego de clicks en una pagina web y este mismo esta soportado por una infraestructura de aws con vpc, bastion y privada(o por lo menos asi lo hice yo) 

#structura del Proyecto

el docker fue creado en la privada y esta corriendo en la misma 

se creo un tunel mediante la bastion para poder acceder desde el navegador local 


#Requisitos previos

Para ejecutar este proyecto en cualquier computador, necesitas:

Docker instalado

git si necesitas clonar el repo


# Instalación y ejecución local (en tu PC)

# Clonar el repositorio

git clone https://github.com/SHIVAGG40/juego-clicks-aws.git
cd juego-clicks-aws

# Para instalarlo ejecuta estos comandos

docker build -t juego-web .

docker run -d -p 8080:80 juego-web

con esto ya podrias ingresar desde un navegador pero si quieres realizarlo desde una estructura aws puedes utilizar un tunel desde la bastion y la privada para que el contenedor pueda tener acceso a la red primero tendrias que pasar de la bastion a la privada
el docker con todo sus componenetes y puglins y asi intalarlo en la privada para poder montar el dockfile

con este comando podras realizar el tunel

ssh -i bastion.pem -L 8080:10.0.0.138:80 ubuntu@<IP_PUBLICA_BASTION>

