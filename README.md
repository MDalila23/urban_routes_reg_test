**Descripción**
- **Qué es:** Este archivo contiene la documentación del Excel utilizado para las pruebas de QA de la aplicación Urban Route.
- **Estructura:** El Excel tiene dos hojas principales: una llamada "Casos de prueba" (contiene los casos que los testers ejecutan) y otra llamada "Informes de errores" (contiene los defectos encontrados y su seguimiento).

**Hoja: Casos de prueba**
- **ID:** Identificador único del caso de prueba.
  - Ejemplo: "TC-001" o "001"
  - Recomendado: usar un prefijo consistente para diferenciar tipos (TC- para casos de prueba, ST- para smoke tests, etc.).
- **Titulo del caso de prueba:** Título breve y descriptivo que resume qué se prueba.
  - Debería ser corto y claro, por ejemplo: "Inicio de sesión con credenciales válidas".
- **Condición previa:** Estado o configuraciones que deben cumplirse antes de ejecutar el caso (por ejemplo, usuario con cuenta activa, datos en la base, permisos, versión de la app).
  - Si no hay condiciones especiales, indicar "Ninguna".
- **Paso:** Lista de pasos (secuenciales) necesarios para ejecutar el caso. Pueden estar en una sola celda separados por número o saltos de línea.
  - Ejemplo: "1) Abrir la app. 2) Ingresar usuario. 3) Pulsar iniciar sesión."
- **Descripción de los datos:** Valores de entrada, credenciales o datos específicos a utilizar durante la ejecución del caso.
  - Ejemplo: "Email: test@example.com, Contraseña: Test1234"
- **Resultado esperado:** Resultado que, de ocurrir, hará que el caso se considere como aprobado.
  - Debe ser lo más concreto posible: "Usuario redirigido a la pantalla de inicio con token válido".
- **Estado:** Indica el resultado o estado actual de la ejecución del caso.
  - Valores sugeridos: "No Ejecutado", "En Progreso", "Pasado", "Fallido", "Bloqueado".
  - Si se registra un fallo, añadir el identificador del error en la columna `ID del error`.
- **ID del error:** Referencia al informe de error en la hoja "Informes de errores".
  - Si el caso ha fallado y se creó un informe, poner aquí el ID del informe (por ejemplo, "BUG-001").
  - Si no aplica, dejar en blanco o usar "-".

**Hoja: Informes de errores**
- Esta hoja contiene los defectos/bugs reportados durante la ejecución de los casos de prueba. Aunque los nombres y columnas pueden variar, típicamente debe incluir:
  - **ID:** Identificador único para el defect (ej: "BUG-001").
  - **Título:** Resumen breve del problema (ej: "Error en inicio de sesión con credenciales válidas").
  - **Pasos para reproducir:** Pasos exactos para reproducir el bug (pueden provenir del caso de prueba asociado).
  - **Resultado esperado:** Qué debería pasar si la app funcionar correctamente.
  - **Resultado actual:** Qué pasó en la ejecución (incluyendo mensajes de error, códigos HTTP, capturas de pantalla si aplica).
  - **Severidad/Prioridad:** Cómo impacta el bug (crítico, alto, medio, bajo) y prioridad para arreglarlo.
  - **Estado del bug:** Por ejemplo "Abierto", "Asignado", "En progreso", "Resuelto", "Cerrado".
  - **Asignado a:** Persona o equipo responsable de la corrección.
  - **Referencias / Notas:** Logs, capturas de pantalla y enlace a tickets externos si aplica.

**Convenciones y buenas prácticas**
- **IDs únicos:** Mantener un esquema coherente para ID de casos y bugs (prefijo + número secuencial).
- **Referencias cruzadas:** Siempre que un caso falle, crear un informe de error y pegar su ID en `ID del error` del caso de prueba correspondiente.
- **Estado consistente:** Usar el conjunto de valores de `Estado` definido arriba para poder filtrar y reportar fácilmente.
- **Formato de pasos:** Usar un formato numerado o con viñetas dentro de una celda para preservar el orden y la claridad.
- **Datos sensibles:** No incluir datos personales reales (PII). Para credenciales, usar cuentas de prueba sancionadas.

**Ejemplo de fila (Casos de prueba)**
- **ID:** TC-005
- **Titulo del caso de prueba:** Ingresar ubicación y calcular ruta en Urban Route
- **Condición previa:** Usuario logueado; GPS simulado habilitado
- **Paso:** 1) Abrir Urban Route; 2) Ingresar punto A y B; 3) Pulsar calcular ruta
- **Descripción de los datos:** Origen: "Calle 50 #10-20"; Destino: "Av. Principal #200"
- **Resultado esperado:** Muestra la ruta más rápida con tiempo y distancia calculados
- **Estado:** Pasado
- **ID del error:** -

**Notas finales**


---

**¿Cómo descargar este proyecto desde GitHub? (Guía para principiantes)**

1. Ingresa a la página del repositorio en GitHub: https://github.com/MDalila23/urban_routes_reg_test
2. Busca el botón verde que dice **Code** y haz clic en él.
3. Selecciona la opción **Download ZIP** para descargar el proyecto como un archivo comprimido.
4. Una vez descargado, descomprime el archivo ZIP en la carpeta de tu preferencia.
5. Ahora puedes abrir la carpeta del proyecto en tu computadora y ver los archivos, incluyendo este README y el Excel de pruebas.

**Opcional:** Si tienes conocimientos de Git, puedes clonar el repositorio usando el siguiente comando en la terminal:
```bash
git clone https://github.com/MDalila23/urban_routes_reg_test.git
```

¡Listo! Así tendrás una copia local del proyecto para revisarlo o trabajar en él.

---

**¿Cómo descargar el proyecto usando PowerShell?**

1. Abre PowerShell en tu computadora (puedes buscar "PowerShell" en el menú de inicio de Windows).
2. Navega a la carpeta donde quieres guardar el proyecto. Por ejemplo, para ir a la carpeta Documentos:
  ```powershell
  cd "$HOME\Documents"
  ```
3. Escribe el siguiente comando para clonar el repositorio:
  ```powershell
  git clone https://github.com/MDalila23/urban_routes_reg_test.git
  ```
  (Si no tienes Git instalado, descárgalo de https://git-scm.com/ e instálalo antes de ejecutar este comando).
4. Cuando termine, entra a la carpeta del proyecto:
  ```powershell
  cd urban_routes_reg_test
  ```
5. Ahora verás todos los archivos del proyecto listos para usar.

¡Eso es todo! Así puedes descargar el proyecto directamente usando PowerShell.

