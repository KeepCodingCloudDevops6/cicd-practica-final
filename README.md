# Keepcoding Devops 6 CI/CD Práctica Final

En esta práctica pondremos a prueba los conocimientos adquiridos en el módulo sobre CI/CD del bootcamp DevOps de KeepCoding.

:information_source: No hay única solución válida para esta práctica, emplea toda la creatividad posible, se valorará

El objetivo es montar un proyecto como cualquiera de los que nos piden en la empresa a los profesionales DevOps.

En este caso, la empresa ACME quiere empezar a probar la nube, por lo que vamos a crear de manera totalmente automatizada unidades de almacenamiento en la nube (AWS S3)

Los requerimentos que nos ha dado ACME son los siguientes:

- Quieren una unidad almacenamiento que se llamará `acme-storage`, será un bucket S3 de AWS
- Quieren que el flujo de despliegue sea "Continuous Delivery" en la rama `main`, es decir, un administrador validará el comando de puesta en producción de la infraestructura
- Sin embargo, en otras ramas distintas de `main`, el despliegue será "Continuous Deployment" y no habrá aprobación manual, será totalmente automático
- Los desarrolladores de ACME han de poder hacer el despliegue también desde sus máquinas
- Quieren que las credenciales para desplegar nunca estén guardadas en el código
- Además ACME también quiere revisar cada 10 minutos que el contenido que hay en la unidad de almacenamiento no supera los 20MiB. Si esto pasa, se vaciará de manera automatizada
- ACME lleva usando Jenkins mucho tiempo pero está actualmente abriéndose a probar nuevas teconologías con menor coste de gestión como Github Actions. Es por esto que también se requiere un pipeline de Github actions para el despliegue de la unidad de almacenamiento, de modo que ACME pueda comparar ambas tecnologías

### Entregables

> A continuación se describen los entregables que se tendrán en cuenta para evaluar la práctica. Lo más típico es que entregues todos juntos en un mismo proyecto de GitHub

- Proyecto terraform para la creación de la unidad de almacenamiento
- Makefile que usaran los desarrolladores para despliegue en local. README con instrucciones para desarrolladores
- Dockerfile del agente que se usará para correr los jobs en Jenkins. Puede heredar del agente base que tenemos del curso.
- Job DSL que correrá Jenkins para crear el job de despliegue
- Jenkinsfile del job de despliegue
- Fichero `yaml` con el pipeline de Github Actions para el despliegue ([OPCIONAL] Aprobación manual del pipeline)
- [OPCIONAL] Script para rellenar uno de los buckets con datos dummy, que se usará para testear el job de chequeo de almacenamiento. Para esto se puede usar bash o python
- Job DSL que correrá Jenkins para crear el job periódico de chequeo de almacenamiento
- README donde se especificará que versión de instancia de Jenkins se ha utilizado así como los plugins, secretos y configuraciones necesarias
- Jenkinsfile del job de chequeo de almacenamiento
- Fichero `yaml` con el pipeline de Github Actions para el despliegue de la unidad de almacenamiento
- README general explicando el proyecto y las decisiones de diseño tomadas. Explicar el porqué de las mismas, sus beneficios y sus inconvenientes
