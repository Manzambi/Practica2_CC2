﻿# Practica2_CC2
## Desarrollo y descripcion del Problema
   Para esta practica desarrollaremos una aplicacion con kubernerts usando opefaas para manipulaciones y creacion de funfiones 
   atraves de openfaas-cli.
   para ello debemos configurar el entorno y el sistema para tal.  Antes de configurar la plataforma para el servicio de funciones FaaS en OpenFaas, hicimos un par de cosas previamente, lo primero que tenemos que hacer es tener instalado kubernets.
   
   para la instalacion de kubernets lo primero que hicimos fue instalar docker, en nuestro caso ya lo teniamos instalado así que solo proce
   demos a instalar kubernets atraves de docker-desktop y habiltar un par de cosas, una vez hecho pasamos a la instalacion de minikube que 
   es el comando que usamos para la creacion de clusteres, en seguida instalamos arkade comndo que nos permitira instalar openfaas.
   
   La aplicacion consisti en pasar una url de una imagen desde el navegador, haciendo post de una url de una web donde tenga imagenes con caras
   y en seguida nos retornar la detecion de las caras en cuadraditos.
   
   Para nuestra practicas las herramientas que usamos para llevar a cabo los procedimientos son:
   
          - Postman
          - Kubernets
          - openFaas

   ## configuraracion de la plataforma para el servicio de funciones FaaS en OpenFaas.
   
 Para configurar la plataforma de OpenFaas para el servicio de funciones FaaS (Function as a Service), debes seguir estos pasos:

 Instalación de OpenFaas: Primero, debemos instalar OpenFaas en el entorno. para tal procedimientos seguimos los pasos de la session 7 de la practica, a continuacion citamos algunos de los procedimientos que son importantes:

  Configuración de OpenFaas Gateway: Una vez que OpenFaas está instalado, configuraramos el Gateway de OpenFaas. El Gateway es el punto de entrada para las solicitudes a las funciones. que en nuestro caso la contraseña y el password, se genera solo.

  Autenticación y autorización: una vez configurada usamos el nombre de usuario y la contraseña para poder acceder a la interface web openFaas-cli para la manipulacion de las funciones en openfaas. lembrando que para la instalacion de openfaas-cli usamos el procedimiento 
  de la sesion 7 de la practica, explicado en clase. por defecto el nombre del usuario que se crea es admin, y para visualizar la contraseña creada si usa el comando que se ve en la figura de abajo:
  
 ![pizzas2](./img/Captura%20de%20pantalla%202023-05-20%20173109.png)
 
  Creación de funciones: Puedemos crear nuestras propias funciones utilizando lenguajes de programación compatibles con OpenFaas, como Python, Node.js, Go, etc. en nuestro caso usamos python.
    
 Despliegue de funciones: Una vez que tenemos desarrollado nuestra funcion, desplegamos en OpenFaas. 

Estos son los pasos básicos para configurar la plataforma de OpenFaas para el servicio de funciones FaaS.

## Implementación de la función de detección de rostros y Pasos para el despliegue de la función implementada 
   
