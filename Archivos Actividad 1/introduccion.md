# ✒️ Introducción al Diseño Orientado a Objetos

El **Paradigma Orientado a Objetos (POO)** es una forma de programacion en el cual los programas se pueden construir a partir de "objetos". Un objeto puede ser pensado como una entidad que tiene un **estado** y un **comportamiento**.

El POO es imporante ya que te permitirá expandir el codigo a medida que el proyecto crezca y construir de manera mas organizada y eficiente.

---

## 🚩 Los cuatro fundamentos de POO

Los cuatros fundamentos del Paradigma Orientado a Objetos son:

1. **Abstracción**
2. **Polimorfismo**
3. **Encapsulación**
4. **Herencia**

### 📝 Abracción

Implica abstraer los detalles innecesarios para centrarse en lo que es relevante para la aplicación en particular.

#### 🔖Ejemplo del mundo real:

Con una impresora, solo necesitas saber como cargar el papel, llenar el cartucho de tinta y enviar el documento a la impresora para que imprima. En el POO, se podría modelar una impresora como un objeto con metodos como `imprimir()`, `cargarPapel()`, y `llenarTinta()` sin exponer los detalles del mecanismo interno de la impresora.

### 📝 Polimorfismo

Es el concepto de que un solo método, puede comportarse de manera diferente según el tipo de objeto que lo llame.

#### 🔖Ejemplo del mundo real:

En un vehiculo, puede referirse a varios metodos de transporte, como autos, bicicletas, autobuses, motocicletas y camiones. A pesar de que son diferentes tipos de transporte, todos compartes algunos atributos comunes como mover personas. En el POO, podemos considerar el **vehículo** como una **clase base**, mientras que **auto**, **bicicleta**, etc., serían **subclases**.

### 📝 Encapsulación

La encapsulación es una forma de ocultar o encapsular los datos y los detalles de implementación dentro de una clase, ocultando así la complejidad.

#### 🔖Ejemplo del mundo real:

Con un reloj, solo interactuas con los elementos visibles y controlables, como el mecanismo para ajustar la hora (agujas). El mecanismo interno del reloj, que incluye los engranajes, resortes y piezas movibles, está **encapsulado** y oculto y no son accesibles directamente desde fuera del objeto.

### 📝 Herencia

Permite la definición de múltiples clases usando las propiedades de otras clases. Creamos clases heredando las funciones y variables de una **clase base**. Luego agregamos nuevas funciones para mejorar su desempeño.

#### 🔖Ejemplo del mundo real:

Todos los seres humanos son **mamíferos**, pero tambien tenemos caracteristicas especificas que nos diferencian de otros mamiferos. En el POO, podríamos tener una **clase Mamífero**, con propiedades de `respirar()` y `alimentarse()`, y una **clase Humano** que hereda de **Mamífero** con propiedades especificas como `hablar()`.

---

## 🚩 Requisitos iniciales del sistema

Los requisitos funcionales del sistema de gestión de turnos son:

### 🔵 Registro y gestión de pacientes y profesionales 
- Dentro del sistema se tendría que poder registrar a todos los **profesionales** y **pacientes** almacenando su información y contacto.

### 🔵 Asignación de turnos:
- El sistema deberá poder asignar turnos a los medicos disponibles y a su vez evitar asignar a **dos pacientes al mismo horario**.

### 🔵 Estado de los turnos:
- El sistema debe permitir cambiar el estado del turno entre:
  - "Pendiente"
  - "Confirmado"
  - "Cancelado"
  - "Realizado"

### 🔵 Notificaciones:
- Se enviarán **notificaciones automáticas** ya sea a pacientes o medicos cuando un turno sea **confirmado, cancelado o modificado** mediante via email o mensaje de texto.

### 🔵 Seguridad:
- Dentro del sistema solo podrá ser accesible para el **personal autorizado** con referencia a las informaciones de los pacientes.

---

## 🚩 Casos de Uso

### 📌 1. Nombre del caso de uso: Registrar un Nuevo Medico.

**▫️Actor(es) involucrado(s):** Administrador del Centro de Salud.

**▫️Descripción breve:** El administrador ingresa los datos de un nuevo medico al sistema.

**▫️Flujo principal de eventos:**
1. El administrador inicia sesión en el sistema.
2. Selecciona la opción **"Registrar Nuevo Médico"**.
3. El sistema muestra un formulario para registrar un nuevo médico.
4. El administrador ingresa la siguiente información en el formulario:
   - Nombre completo del médico.
   - Número de documento (DNI).
   - Especialidad médica.
   - Número de matrícula profesional.
   - Correo electrónico y teléfono de contacto.
   - Horarios de atención disponibles.
5. El sistema valida los datos ingresados (formato correcto, campos obligatorios, etc.).
6. Si hay errores, se muestran mensajes para que el administrador los corrija.
7. Una vez validado, el administrador confirma la operación haciendo clic en “Guardar”.
8. El sistema guarda los datos del nuevo médico en la base de datos.
9. Se muestra un mensaje de confirmación indicando que el médico fue registrado correctamente..

**▫️Precondiciones:** 
- El administrador debe estar autenticado en el sistema.
   
**▫️Postcondiciones:**
- El medico está registrado en el sistema y puede comenzar a recibir turnos y atender a clientes.

---

### 📌 2. Nombre del caso de uso: Modificar Datos de un Paciente.
   
**▫️Actor(es) involucrado(s):** Administrador del Centro de Salud.
  
**▫️Descripción breve:** El administrador actualiza los datos de un paciente en el sistema.
   
**▫️Flujo principal de eventos:**
1. El administrador inicia sesión en el sistema.
2. Selecciona la opción **"Modificar Datos de Paciente"**.
3. Edita los datos del paciente (nombre, DNI, fecha de nacimiento, teléfono).
4. Confirma la información y se guarda en el sistema.

**▫️Precondiciones:** 
- El administrador debe estar autenticado en el sistema y el paciente debe estar registrado.

**▫️Postcondiciones:** 
- Los datos del paciente están actualizados en el sistema.

---

### 📌 3. Nombre del caso de uso: Ver Disponibilidad de Turnos de un Médico

**▫️Actor(es) involucrado(s):** Administrador del Centro de Salud
   
**▫️Descripción breve:** El administrador consulta la disponibilidad de turnos de un médico.
   
**▫️Flujo principal de eventos:**
1. Inicia sesión en el sistema.
2. Selecciona **"Ver Disponibilidad de Turnos"**.
3. Busca al médico por nombre.
4. El sistema muestra la agenda del médico seleccionado.

**▫️Precondiciones:**
- El administrador debe estar autenticado en el sistema y el médico debe estar registrado.

**▫️Postcondiciones:** 
- El administrador tiene acceso a la disponibilidad de turnos del médico.

---

### 📌 4. Nombre del caso de uso: Enviar Notificaciones Masivas a Pacientes.

**▫️Actor(es) involucrado(s):** Administrador del Centro de Salud
   
**▫️Descripción breve:** El administrador envía una notificación a varios pacientes sobre un evento o cambio general.
   
**▫️Flujo principal de eventos:**
1. Inicia sesión en el sistema.
2. Selecciona **"Enviar Notificaciones Masivas"**.
3. Elige el grupo de pacientes.
4. Escribe el mensaje y confirma el envío.
5. El sistema envía automáticamente por **SMS o Email**.

**▫️Precondiciones:** 
- El administrador debe estar autenticado en el sistema y los pacientes en sí.

**▫️Postcondiciones:** 
- Los pacientes del grupo reciben la notificación.

---

### 📌 5. Nombre del caso de uso: Generar Informe de Turnos por Período.

**▫️Actor(es) involucrado(s):** Administrador del Centro de Salud
   
**▫️Descripción breve:** El administrador genera un informe de los turnos realizados en un período específico.
   
**▫️Flujo principal de eventos:**
1. El administrador inicia sesión en el sistema.
2. Selecciona **Generar Informe de Turnos**.
3. Elige el periodo de tiempo del informe.
4. El sistema generará un informe de todos los turnos que estén relacionados a la fecha elegida.
5. Descargar en formato PDF.

**▫️Precondiciones:** 
- El administrador debe estar autenticado en el sistema y debe haber turnos registrados anteriormente.

**▫️Postcondiciones:** 
- El administrador tiene acceso al informe de turnos por período.

---

## 🚩 Boceto
[![Boceto_KevinSosa](https://github.com/user-attachments/assets/f6e4b781-7cf9-4c56-9433-ea91935e9fd0)](https://app.diagrams.net/#G1avrHwCQiVETKfxUOJ0o0nA5yJIxv9EZQ#%7B%22pageId%22%3A%22dd472eb7-4b8b-5cd9-a60b-b15522922e76%22%7D)

