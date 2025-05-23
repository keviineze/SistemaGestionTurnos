# ✒️ Introducción al Diseño Orientado a Objetos

La **Paradigma Orientada a Objetos (POO)** es un enfoque de desarrollo de software que se basa en la creación de objetos, los cuales representan entidades con características (atributos) y acciones (métodos). Estos objetos interactúan entre sí para construir programas más ordenados, modulares y similares a cómo entendemos el mundo real.

Cada objeto es una instancia de una clase, que actúa como un molde o plantilla. Este paradigma promueve la organización del código en unidades independientes, lo que ayuda a gestionar la complejidad de sistemas grandes.

El **Paradigma Orientado a Objetos es importante ya que:**
1. Modela problemas reales: Permite representar elementos reales o conceptuales de forma natural.
2. Favorece la modularidad: Cada clase u objeto puede desarrollarse, probarse y modificarse por separado.
3. Facilita la colaboración: En proyectos grandes, cada desarrollador puede trabajar sobre una parte del sistema sin afectar otras.
4. Promueve buenas prácticas: Fomenta el uso de principios sólidos como responsabilidad única y separación de preocupaciones.

---

## 🚩 Los cuatro fundamentos de POO

Los cuatros fundamentos del Paradigma Orientado a Objetos son:

1. **Abstracción**
2. **Polimorfismo**
3. **Encapsulación**
4. **Herencia**

### 📝 Abstracción

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
  3. El sistema muestra una interfaz para buscar al paciente.
  4. El administrador ingresa un criterio de búsqueda (ej. DNI o nombre del paciente).
  5. El sistema muestra los datos actuales del paciente.
  6. El administrador edita la información necesaria en el formulario:
     - Nombre completo del paciente.
     - Número de documento (DNI).
     - Fecha de nacimiento.
     - Número de teléfono.
     - Dirección.
     - Otro dato relevante (ej. grupo sanguíneo, antecedentes, etc.).
  7. El sistema valida los datos ingresados (formato correcto, campos obligatorios, etc.).
  8. Si hay errores, se muestran mensajes para que el administrador los corrija.
  9. Una vez validado, el administrador confirma la operación haciendo clic en **"Guardar"**.
  10. El sistema actualiza los datos del paciente en la base de datos.
  11. Se muestra un mensaje de confirmación indicando que la modificación fue exitosa.

**▫️Precondiciones:** 
- El administrador debe estar autenticado en el sistema y el paciente debe estar registrado.

**▫️Postcondiciones:** 
- Los datos del paciente están actualizados en el sistema.

---

### 📌 3. Nombre del caso de uso: Ver Disponibilidad de Turnos de un Médico

**▫️Actor(es) involucrado(s):** Administrador del Centro de Salud
   
**▫️Descripción breve:** El administrador consulta la disponibilidad de turnos de un médico.
   
**▫️Flujo principal de eventos:**
  1. El administrador inicia sesión en el sistema.
  2. Selecciona la opción **"Ver Disponibilidad de Turnos"** en el menú principal.
  3. El sistema muestra un campo de búsqueda para localizar al médico.
  4. El administrador ingresa el nombre, especialidad o matrícula del médico.
  5. El sistema lista los médicos que coinciden con los criterios ingresados.
  6. El administrador selecciona al médico deseado de la lista.
  7. El sistema muestra la agenda del médico seleccionado con:
     - Días de atención.
     - Horarios disponibles.
     - Turnos ya reservados.
     - Estado general de disponibilidad.
  8. El administrador puede aplicar filtros por fecha o turno (mañana/tarde).
  9. El sistema actualiza la vista según los filtros aplicados.
  10. Si hay algún error (por ejemplo, médico no registrado), se muestra un mensaje de advertencia.
  11. El administrador revisa la disponibilidad y cierra la consulta o procede con otra acción (ej. asignar turno).

**▫️Precondiciones:**
- El administrador debe estar autenticado en el sistema y el médico debe estar registrado.

**▫️Postcondiciones:** 
- El administrador tiene acceso a la disponibilidad de turnos del médico.

---

### 📌 4. Nombre del caso de uso: Enviar Notificaciones Masivas a Pacientes.

**▫️Actor(es) involucrado(s):** Administrador del Centro de Salud
   
**▫️Descripción breve:** El administrador envía una notificación a varios pacientes sobre un evento o cambio general.
   
**▫️Flujo principal de eventos:**
  1. El administrador inicia sesión en el sistema.
  2. Selecciona la opción **"Enviar Notificaciones Masivas"**.
  3. El sistema muestra un formulario para configurar el envío de notificaciones.
  4. El administrador elige el grupo de pacientes al que desea enviar la notificación:
     - Todos los pacientes.
     - Por rango etario.
     - Por historial médico.
     - Por fecha de turno.
     - Por localidad o zona geográfica.
  5. El administrador redacta el mensaje de la notificación (título y cuerpo del mensaje).
  6. Selecciona el canal de envío:
     - SMS.
     - Correo electrónico.
     - Ambos.
  7. Confirma el envío haciendo clic en **"Enviar Notificación"**.
  8. Se muestra una notificación de éxito si el envío fue realizado correctamente.

**▫️Precondiciones:** 
- El administrador debe estar autenticado en el sistema y los pacientes en sí.

**▫️Postcondiciones:** 
- Los pacientes del grupo reciben la notificación.

---

### 📌 5. Nombre del caso de uso: Solicitar Turno.

**▫️Actor(es) involucrado(s):** Paciente
   
**▫️Descripción breve:** El paciente accede al sistema y solicita un turno médico seleccionando especialidad, profesional, fecha y horario disponibles.
   
**▫️Flujo principal de eventos:**
  1. El paciente inicia sesión en el sistema.
  2. Selecciona la opción **"Solicitar Turno"**.
  3. El sistema muestra las especialidades médicas disponibles.
  4. El paciente selecciona una especialidad.
  5. El sistema muestra los profesionales asociados a la especialidad.
  6. El paciente selecciona un profesional.
  7. El sistema muestra las fechas y horarios disponibles.
  8. El paciente elige una fecha y hora.
  9. Confirma la solicitud del turno.
  10. El sistema registra el turno y muestra la confirmación.
  11. Se envía una notificación al paciente con los detalles del turno.

**▫️Precondiciones:** 
- El paciente debe estar registrado y autenticado en el sistema. Debe haber profesionales y horarios disponibles.

**▫️Postcondiciones:** 
- El turno queda registrado en el sistema con estado "Asignado" y es visible en el perfil del paciente.

---

## 🚩 Boceto

![Boceto_KevinSosa](Boceto_Incial_Diseño_Clases.png)

[Click para verlo en Línea](https://app.diagrams.net/#G1avrHwCQiVETKfxUOJ0o0nA5yJIxv9EZQ#%7B%22pageId%22%3A%22dd472eb7-4b8b-5cd9-a60b-b15522922e76%22%7D)

