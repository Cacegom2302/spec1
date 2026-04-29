---
title: "Agenda Basica CLI con python"
version: "0.1"
date: "29/04/2026"
---
# spec.md - Esopecificacion funcional #
#1.Descripcion general CLI
La aplicacion es una herramienta de linea de comando (CLI) escrita en lenguaje python que permite gestinonar una agenda de contactos almacenada en una base de datos MySQL. Ofreciendo operaciommes propias de CRUD.

## 2. Funcionalidades
-Crear, listar , actualizar y eliminar contactos.
-Buscar coontacto por nombre, por telefono y por email
-Listar todos los contactos 
-Crear un menu de opciones
-CLI sea interactiva
-Almacene informacion en una base de datos MySQL

## 3. Modelo de datos
| Campo | tipo | Obligatorio | Descripcion |
|-------|------|-------------|-------------|
|"id"   |INT AUTOINCREMENT| SI | Identificador unico |
| name  |VACHAR(100) | Si | Nombre contacto |   
| surname  |VACHAR(100) | Si | Apellido contacto | 
| TEL1  |INTEGER | Si | Telefono 1 contacto | 
| TEL2  |INTEGER | No | Telefono 2 contacto | 
| Email  | VARCHAR(50)| No | Email  contacto | 
| Notes | TEXT(100) | No | Informacion del contacto|

## 4. Casos de uso
###CU-01: Añadir un contacto
1. El usuario selecciona "Añadir contacto"
2. Sistema pide:  nombre (name) surname ,numero (tel1), tel2 , notes
3. El usuario introduce los datos
4. El sistema valida los datos 
5. El sistema cmprueba si existe un contacto con el mismo telefono.
6. El sistema inserta el contacto en la base de datos y te muestra el id con los datos del contacto

**Flujo alternativo A Validadcion
  - El sistema muestra un mesaje de error y solicita corregir el error
**Flujo alternatico B validacion correcta
  - El sistema inserta los datos en la base de datos
**Flujo alternatico C contacto duplicado
  - El sistema nos advierte de que existe el contacto y pide confirmacion de guardado

###CU-02: Ver Contacto
1. El usuario selecciona "Ver contacto"
2. Sistema pide:  nombre (name) , Apellido (surname) o telefono (tel1)
3. El usuario introduce los datos
4. El sistema comprueba si existe coincidencias con un LIKE en name , surname , tel1
5. El sistema muestra todos los resultados coincidentes con ese nombre.

###CU-03: Eliminar Contacto
1. El usuario selecciona "El contacto"

###CU-04: Editar contacto
###CU-05: Listar Contacto
