---
title: Fase de inicio
keywords: interview meeting
last_updated: October 3, 2017
tags: [phase]
summary: "Reuniones y entrevistas iniciales con el Cliente y equipo."
sidebar: fssgest_sidebar
permalink: fssgest_fases_inicio.html
folder: fssgest
---

## Reunion inicial

**Objetivos Generales y especificos**

La aplicación tendrá un Front-End para el Usuario, al igual que una aplicación mobil.<br>
Las acciones de cada una de las Interfaces será incluido en futuras especificaciones.<br>

Ideas a pensar:

* Permisos:
    * Forma de articular y guardar los permisos, para cada uno de las entidades.
    * Forma de aplicar estos permisos.





###  Gestión de Usuarios de la Clinica

Son todos aquellos clientes de la clinica.<br>
Respecto a los usuarios se tienen que tomar en cuenta, que la idea es ofrecer otros servicios en la misma comunidad (ciudad),
y por tanto estos usuarios pueden ser compartidos por otros negocios o aplicativos.

* Diseño de estructura en base de datos para almacenamiento de usuarios.
* Los usuarios puede ser cualquier persona con unas credenciales, que se pueden registrar con las credenciales de providers relevantes *Facebook, Google, twiter, ...**
* Relacion Usuario -> Paciente.
    * Un usuario, La 1ª vez que se le cree una cita, pasa a ser paciente, por tanto, conectar Paciente con Usuario.
    * Un usuario, una vez vinculado a un paciente, está será su vinculacion, aunque al usuario se le podran cambiar datos de acceso, o cualquier otro dato.
* Independienteme de si el usuario se crea con desde la web directamente o se federa desde un provider, hay que crear un registro del mismo anotando:
    * Alias (unico)
    * Telefono (fundamental para saber quien es)
    * DNI (opcional, pero importante al crear el paciente)
    * Otros datos personales requeridos.

* Definir permisos del usuario, que acciones está permitido realizar.


### Gestion de Pacientes

Son todos aquellos personas que necesitan recibir algun tipo de terapia o tratamiento en la clinica.<br>
Cada paciente va a tener asociado un Historial clinico general, con documentación asociada relevante.<br>
Ademas, un paciente puede ser tratado a lo largo de su vida varias veces. Para separar estos tratamientos, se van a incluir este concepto *Tratamientos*,
donde se va a reflejar de forma independiente, y agrupado, estas sesiones dirigidas a conseguir la resolución de problema.

Datos a guardar sobre pacientes:
* Datos personales
* ...


### Gestion de Tratamientos

Los tratamientos son una entidad dependiente de pacientes y sin la cúal no tiene sentido.<br>
Son fundamentales para seguir la evolución del mismo dentro de la clinica, y tb separar los distintos episodios.

####  Funciones principales

####  Datos principales

* Nombre/Codigo: Los tratamientos se identificaran por Nombre o Codigo, (//TODO)
* Historial: Tendrá un historial asociado al mismo, con documentos asociados y notas incorporadas. 
* Finalizacion: Puede tener fecha de finalizacion abierta, si desconocemos el fin.
* Compañia: Particular (paciente particular), Mutua (gestiona una aseguradora), Sanidad Publica (gestina servicio publico de salud).
* Tipo: 
    * Hasta-Aviso: Sin fecha de finalización (de inicio). Cuando se sepa, se le incluirá fecha finalizacion.
    * Por-sesiones: No hay fecha limite, el limite lo marcan las sesiones restantes.

* Las sesiones se podran justifi

##### Sesiones

Sesion es un concepto muy importante en los tratamientos, pues son las que regulan normalmente la duración de los mismos.<br>
Entendemos por sesión, el hecho de recibir terapia en un dia y hora concretos, con una duración determinada.<br>

* Relación Sesión-Cita.
    * Las sesion se vincula a una cita, de muchas formas:
        * Previamente: Al ejecutar/planificar el tratamiento.
        * Posteriori: Al marcarla como completada, se vinculará a una disponible. Si una cita no está vinculado con una sesion, al
    *


* Estado-Completado
    * Pendiente: Su fecha/hora es superior al dia en curso. (=> automaticamente pasa a Vencida)
    * Completada: Indica que sesión no está pendiente. Se divide en:
        * Vencida: (Ausente). La cita


Una ver que la sesión concluye, se marca como completada.

* sesiones restantes = Total sesiones - sesiones completada (recibida, o marcada como completada)
* El Nº de sesiones se puede modificar en cualquier momento, nunca pudiendo ser inferior a las ya completadas.
* Cuando una sesión se planifique => creará una cita, a la cual estará asociada.


###### 1.1 Tipo
La finalización de un tratamiento puede estar definida por:
*










{% include links.html %}
