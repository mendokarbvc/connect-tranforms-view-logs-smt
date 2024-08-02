# connect-tranforms-view-logs-smt
SMT transformation to view logs of records


Proyecto de Ejemplo con Kafka Connect y Transformación "ViewLogs"

Este proyecto es un ejemplo de cómo configurar y compilar un proyecto Maven que utiliza Kafka Connect con una transformación personalizada llamada "ViewLogs".

Requisitos previos
Antes de comenzar, asegúrate de tener instalados los siguientes requisitos:

Java Development Kit (JDK) 8 o superior
Apache Maven 3.6.0 o superior
Apache Kafka
Estructura del proyecto
La estructura del proyecto es la siguiente:

├── pom.xml
├── src
│   ├── main
│   │   ├── java
│   │   │   └── com
│   │   │       └── nuamx
│   │   │           └── temp
│   │   │               └── kafka
│   │   │                   └── connect
│   │   │                       └── smt
│   │   │                           └── ViewLogs.java
│   │   └── resources
│   │       └── log4j.properties
│   └── test
│       └── java
│           └── com
│               └── nuamx
│                   └── temp
│                       └── kafka
│                           └── connect
│                               └── smt
│                                   └── ViewLogsTest.java
└── README.md

Compilación del proyecto
Para compilar el proyecto, sigue estos pasos:

Clona el repositorio o descarga el código fuente.

Navega al directorio raíz del proyecto.

Ejecuta el siguiente comando para compilar el proyecto utilizando Maven:

mvn clean package

Esto generará un archivo JAR en el directorio target.

Configuración de Kafka Connect
Para utilizar la transformación "ViewLogs" en Kafka Connect, debes configurar tu conector. Aquí tienes un ejemplo de configuración en formato JSON:

{
  "name": "mi-conector",
  "config": {
    "connector.class": "org.apache.kafka.connect.file.FileStreamSourceConnector",
    "tasks.max": "1",
    "file": "/path/to/input/file.txt",
    "topic": "mi-topic",
    "transforms": "ViewLogs",
    "transforms.ViewLogs.type": "com.nuamx.temp.kafka.connect.smt.ViewLogs$Value"
  }
}
