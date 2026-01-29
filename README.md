Link de la página: https://camiloarci.github.io/capstone_app1/

# Integrantes del equipo:
Camilo Arciniegas
Andrés Sánchez
Juan José Forero
Juan José Rodriguez
Felipe Abella

# FourSight Group Builder

Aplicación web para la **creación automática de grupos de trabajo equilibrados** a partir de los perfiles cognitivos **FourSight** (Clarificador, Ideador, Desarrollador e Implementador).

Está diseñada para contextos educativos y académicos, facilitando la conformación de equipos diversos y funcionales a partir de datos cuantitativos.

---

## 🧠 ¿Qué hace esta aplicación?

- Lee un archivo **Excel (.xlsx / .xls)** con los puntajes FourSight de los estudiantes.
- Identifica **perfil primario, secundario y terciario** por estudiante.
- Detecta **integradores** (empates en el puntaje más alto).
- Excluye automáticamente estudiantes con datos incompletos.
- Forma grupos balanceados priorizando la **diversidad cognitiva**.
- Presenta resultados visuales y tabulados de forma clara.

---

## 📋 Requisitos del archivo de entrada

El archivo Excel debe cumplir con lo siguiente:

- Formato: `.xlsx` o `.xls`
- Hoja: se utiliza **la primera hoja** del archivo
- Columnas obligatorias (respetar nombres):

| Columna | Descripción |
|------|-----------|
| Nombre | Nombre del estudiante |
| Clarificador | Puntaje FourSight |
| Ideador | Puntaje FourSight |
| Desarrollador | Puntaje FourSight |
| Implementador | Puntaje FourSight |

📌 **Nota:**  
Los estudiantes que tengan **datos faltantes** en cualquiera de los cuatro puntajes serán excluidos del análisis.

---

## 👥 Número de estudiantes esperado

- Ideal: **22 estudiantes con datos completos**
- Distribución esperada:
  - 4 grupos de 4 personas
  - 2 grupos de 5 personas

Si el número de estudiantes válidos **no es exactamente 22**, la aplicación:
- Muestra una advertencia
- Permite continuar bajo confirmación
- Ajusta dinámicamente el tamaño de los grupos

---

## ⚙️ Lógica de conformación de grupos

La asignación de estudiantes se realiza en **cuatro fases**:

### 1️⃣ Prioridad por perfil primario
- Se asignan primero los estudiantes con mayor **diferencia (delta)** entre perfil primario y secundario.
- Cada grupo intenta cubrir todos los perfiles.

### 2️⃣ Asignación por perfil secundario
- Si el perfil primario ya está cubierto, se utiliza el perfil secundario.

### 3️⃣ Integradores y perfiles terciarios
- Los estudiantes integradores o restantes se asignan al grupo con espacio disponible.
- Se prioriza: **Primario → Secundario → Terciario**.

### 4️⃣ Cierre de grupos
- Se asegura que todos los grupos queden completos según el tamaño definido.

---

## 📊 Resultados que muestra la aplicación

### Resumen de datos
- Total de estudiantes cargados
- Estudiantes con datos completos
- Estudiantes excluidos
- Distribución de perfiles primarios

### Visualización de grupos
- Número de grupo
- Tamaño del grupo
- Perfiles representados
- Estudiantes asignados
- Rol asignado (P / S / T)
- Identificación de integradores

### Tabla detallada de estudiantes
Incluye:
- Puntajes individuales
- Perfil primario y secundario
- Grupo asignado
- Rol dentro del grupo
- Estado (Incluido / Excluido)

---

## 🧪 Datos de ejemplo

La aplicación incluye una opción para cargar **datos de ejemplo**, lo que permite:

- Probar la funcionalidad sin necesidad de un archivo externo
- Simular estudiantes con datos completos e incompletos

---

## 🛠️ Tecnologías utilizadas

- **HTML5**
- **CSS3**
- **JavaScript**
- **SheetJS (xlsx)** para lectura de archivos Excel

---

## 🚀 Ejecución

No requiere instalación ni servidor.

1. Descarga o clona el repositorio
2. Abre el archivo `index.html` en un navegador moderno
3. Carga el archivo Excel
4. Procesa y visualiza los grupos

---

## 📌 Consideraciones

- Todo el procesamiento se realiza **del lado del cliente**
- No se almacenan datos
- Compatible con navegadores modernos (Chrome, Edge, Firefox)

---

## 📄 Contexto académico

Desarrollado como parte del **Capstone Design Project**, aplicando una lógica multicapa basada en:

- Preferencias primarias
- Gestión de saturación de perfiles
- Análisis de brechas cognitivas
