# Practica2_CC2
## Desarrollo y descripcion del Problema
   Para esta practica desarrollaremos una aplicacion con kubernerts usando opefaas para manipulaciones y creacion de funciones. 
   atraves de openfaas-cli.
   para ello debemos configurar el entorno y el sistema para tal.  Antes de configurar la plataforma para el servicio de funciones FaaS en OpenFaas, hicimos un par de cosas previamente, lo primero que tenemos que hacer es tener instalado kubernets.
   
   Para la instalacion de kubernets lo primero que hicimos fue instalar docker, en nuestro caso ya lo teniamos instalado así que solo proce   demos a instalar kubernets atraves de docker-desktop y habiltar un par de cosas, una vez hecho eso, pasamos a la instalacion de minikube que 
   es el comando que usamos para la creacion de clusteres, en seguida instalamos arkade comando que nos permitira instalar openfaas.
   
   La aplicacion consisti en pasar una url de una imagen desde el navegador, haciendo post de una url de una web donde tenga imagenes con caras
   y en seguida nos retornar la detecion de las caras en cuadraditos.
   
   Para nuestra practicas las herramientas que usamos para llevar a cabo los procedimientos son:
   
          - Postman
          - Kubernets
          - openFaas

   ## configuraracion de la plataforma para el servicio de funciones FaaS en OpenFaas.
   
 Para configurar la plataforma de OpenFaas para el servicio de funciones FaaS (Function as a Service), utilizamos los seguientes pasos:

 Instalación de OpenFaas: Primero, debemos instalar OpenFaas en el entorno. para tal procedimientos seguimos los pasos de la session 7 de la practica, a continuacion citamos algunos de los procedimientos que son importantes:

  Configuración de OpenFaas Gateway: Una vez que OpenFaas está instalado, configuraramos el Gateway de OpenFaas. El Gateway es el punto de entrada para las solicitudes a las funciones. que en nuestro caso la contraseña y el password, se genera solo.

  Autenticación y autorización: una vez configurada usamos el nombre de usuario y la contraseña para poder acceder a la interface web openFaas-cli para la manipulacion de las funciones en openfaas. lembrando que para la instalacion de openfaas-cli usamos el procedimiento 
  de la sesion 7 de la practica, explicado en clase. por defecto el nombre del usuario que se crea es admin, y para visualizar la contraseña creada si usa el comando que se ve en la figura de abajo:
  
 ![img](./img/Captura%20de%20pantalla%202023-05-20%20173109.png)
 
  Creación de funciones: Puedemos crear nuestras propias funciones utilizando lenguajes de programación compatibles con OpenFaas, como Python, Node.js, Go, etc. en nuestro caso usamos python.
    
 Despliegue de funciones: Una vez que tenemos desarrollado nuestra funcion, desplegamos en OpenFaas. 

Estos son los pasos básicos para configurar la plataforma de OpenFaas para el servicio de funciones FaaS.

## Implementación de la función de detección de rostros y Pasos para el despliegue de la función implementada 
  Para implementacion de la funcion usamos el linguagen de programacion de python, para visualizar la implementacion del mismo 
 [clica aqui...](https://github.com/Manzambi/Practica2_CC2/blob/main/facesdetection-python/handler.py), la razon por la que elegimos python 
 es por ser un linguagen de programacion sencillo y a la vez posee una sintaxe mas facil, ademas nos brinda un conjunto de librerias que nos
 facilitan la implementacion del mismo.
 
 para despliegar la funcion y pushearlo en dockerhub procedimos del seguiente modo:
  - Iniciar sesion en docker usando el seguiente comando:
  
            docker login
  
 ![img](./img/Captura%20de%20pantalla%202023-05-20%20171850.png)
 
 
 Ingresamos nuestras credenciales de docker y a continuacion accedimos desde la terminal para acceder a nuestra faas-cli y loguearse
 usando nuetras credenciales como nombre de usuario y contraseña como ve se en la imagen de abajo
 
 
  ![img](./img/Captura%20de%20pantalla%202023-05-20%20173345.png)
 
El  script para implementar una función en OpenFaaS utilizando la interfaz de línea de comandos (CLI) de OpenFaaS que utilizamos es la seguiente:

#### Construir y empaquetar la función

      faas-cli build -f facesdetection-python.yml
      faas-cli push -f facesdetection-python.yml

#### Desplegar la función en OpenFaaS

      faas-cli deploy -f facesdetection-python.yml

## Pruebas Realizadas
  Para verificar el correcto funcionamiento accedimos a la url URL: http://127.0.0.1:8080/function/facesdetection-python desde postman, en la funcionalidad post y realizamos los seguientes tests: 
  le passamos la url de la seguiente imagen en el body/Raw:
  
  ![img](./img/Captura%20de%20pantalla%202023-05-21%20132402.png)
  
  y obtuve como salida el seguiente resultado:
  
   ![img](./img/Captura%20de%20pantalla%202023-05-20%20201754.png)
  
   
   
