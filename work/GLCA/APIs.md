# Arquetipos

Dependiendo la funcionalidad de la API a desarrollar, existen 2 arquetipos (librerias nugget) que Galicia desarrollo para utilizar.

## POM 🟠

El nugget tiene las caracteristicas necesarias que ayuda a la comunicacion entre microservicios de distintos repositorios, por eso mismo se suele utilizar en apis que son puerta de entrada o puerta de salida de un flujo de una arquitectura de microservicios interna o que esta en un solo repositorio. Si se necesita consumir microservicios por fuera del proyecto en si (en terminos practicos, por fuera de la sigla del repositorio de Github) se suele desarrollar un microservicio con la implementacion del arquetipo POM.

## PAAS 🟣

El nugget tiene caracteristicas necesarias que ayuda a la comunicacion entre microservicios internos que estan en un mismo repositorio. A diferencia del arquetipo POM, no tiene tantas restricciones de apim ni tantos servicios por lo cual es mas simple de implementar y con menos seguridad, por lo cual facilita la comunicacion entre microservicios que estan en una misma sigla.

Se suele implementar el arquetipo en apis que no necesitan comunicacion con otros repositorios.

---

# Proceso de altas y deploys

## Alta en BackOffice

Solo para el arquetipo POM, Galicia documenta el microservicio, las funcionalidades y los endpoints en la plataforma BackOffice (de aqui en adelante BO). De esta manera cada vez que se consume una API, el arquetipo POM consulta (para cada ambiente) un servicio que trae las funcionalidades, los endpoints y toda la documentacion correspondiente de la api para su funcionamiento. El arquetipo PAAS no consulta este servicio por lo que no se da de alta en BO.

- **Links BO por cada ambiente**
    - **[DEV]**([[Links utiles#^99776e]])
    - **[INT]**([[Links utiles#^a990a5]])
    - **[QAS]**([[Links utiles#^62cc8d]])
    - **[PROD]**([[Links utiles#^868c0e]])

### En BO se da de alta una api solo para POM en los siguientes apartados:

1. **Microservicios**
    - Tiene que ver con el nombre de la api, la sigla e informacion general del microservicio.
2. **Funcionalidades**
    - El arbol de funcionalidades se refiere a que funcion va a cumplir la api.
3. **Endpoints**
    - Agregar cada enpoint que se va a desarrollar en el microservicio.

Este proceso de alta en BO, se puede dar en cualquier instancia del desarrollo, no hace falta que este terminada la api o no haberla arrancado, pero se recomienda hacerlo antes de iniciar para no tener problemas en pruebas locales ya que para funcionar la api, el arquetipo POM consulta las funcionalidades.

💡 **Consejo extra:** Utilizar para cada apartado una api similar de ejemplo.

## APIM 🔐

Todos los microservicios de Galicia son gestionados mediante APIM a partir de Inte hasta Prod exceptuando el ambiente de desarrollo. Por lo que hay que dar de alta cada microservicio en APIM mediante DevopsToolkit.

### 1- Publicar API en APIM

- previamente a publicar en apim, jenkins solicita que debe estar deployado al menos en INT y pasar correctamente las revisiones de veracode.
    
    - [[Links utiles#^35cb34]] → review modules → advanced mode → seleccionar dll correspondiente al nombre del microservicio.
- En la sigla correspondiente al microservicio, seleccionar opcion Middleware → Administrar Api → Publicar Api.

	⚠️ **Importante:** el endpoint del controller tiene que estar documentado con summary en el codigo, para generar correctamente el swagger.json que luego va a ser solicitado.
	ejemplo:
	
        [SwaggerOperation(Summary = "Endpoint functionality description")]
        [HttpPost("post", Name = "EndpointName")]


- Al solicitar el swagger, hay que colocar la url del archivo json que esta en el swagger de la api en dev.
    ⚠️ **Importante:** a partir del ambiente de Homologacion (QAS) jenkins solicita aprobacion del Technical Owner (el Product Owner tambien deberia poder aprobarlo)
    

### 2- Suscribir sigla como consumidor de la api

- En la sigla correspondiente al microservicio, seleccionar opcion Middleware → Administrar Api → Suscribir Api.
    
- Colocar el nombre de la api correspondiente que se obtiene en la propiedad ”title” del archivo json del swagger de la api en dev.
    
	⚠️ **Importante:** Si tu api consume otros servicios, hay que suscribir nuestro microservicio como consumidor del servicio que corresponda consumir.
	
    ⚠️ **Importante:** a partir del ambiente de Homologacion (QAS) las suscripciones se realizan por TICKET mediante Service Now
    
    ⚠️ **Importante:** Si la sigla es nueva, hay que suscribir la sigla como consumidor a los servicios FUNCTIONALITIES_SPECS, HOLIDAYS, PERMISSION_MANAGER y COMMONS_PARAMETERS.
### 3- Configurar variables de entorno del repo Devops

- Colocar como variables de entorno en el archivo configmap (lo ideal seria como secrets) las credenciales de apim correspondientes a la **sigla** y al **ambiente**.
- Si es el **arquetipo POM 🟠**, en el capa de servicio de la api hay que colocar los headers de las credenciales AppId y Appkey. El arquetipo PAAS al gestionarse internamente no precisa esas credenciales en el codigo.

### 4- Deployar en el ambiente

- Una vez dados de alta los **Midlewares** y la **Suscripcion de la sigla** se puede realizar el deploy de la api.

⚠️ **Importante:** Los deploys, publicaciones y suscripciones de APIM, se realizan por ambiente.

⚠️ **Importante:** A partir del ambiente de Homologacion (QAS) jenkins solicita aprobacion del Technical Owner (el product owner tambien deberia poder aprobarlos)

## Repo Devops 🐱 y Deploy ⚙️

El proceso de Deploy en Galicia para las apis se realiza mediante **Jenkins**.

Esta plataforma toma el repositorio de la sigla del proyecto que le indiques, realiza el deploy automaticamente.

### Carpeta Devops

Las variables de entorno del microservicio las toma desde el repositorio Devops donde para cada API de la sigla, hay una carpeta con los siguientes archivos en formato TextPlain.

- **configmap**
    
    El archivo que contiene las variables de entorno, urls, y utilidades de la api (el archivo launchSettings.json del proyecto .netCore).
    
- **secrets**
    
    Contraseñas y/o credenciales sensibles. → se dan de alta en Jenkins y se pueden ver en Openshift.
    
- **healt**
    
    Informacion de “salud” de la api (generalmente se hace un copypasteo de otra api similar).
    

### Deploy

- Agregar la carpeta de tu microservicio al repositorio Devops con los archivos mencionados anteriormente y su correspondientes datos
- Realizar un Release en github, creando un nuevo tag y continuar la version anterior del release que se haya realizado anteriormente (si se realizo un release V1.0.1 el nuevo tag deberia ser V1.0.2), y especificar en la descripcion a que api corresponde el nuevo release que se realizo.
- Una vez hecho esto, al momento de realizar el deploy de la API en Jenkins te va a sugerir los distintos tags de devops realizados, y tendras que seleccionar el tag que realizaste para ese microservicio en particular (exceptuando en DEV ya que toma el ultimo release hecho de la carpeta devops y realiza el deploy).

⚠️ **Importante:** Para cada API de la sigla tiene que haber una carpeta con exactamente del mismo nombre del repositorio del microservicio correspondiente.