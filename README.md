# Software de Escritorio para Consultorio Médico

Este proyecto es un software de escritorio desarrollado en Python, diseñado específicamente para gestionar las operaciones de un consultorio médico. El sistema permite realizar operaciones CRUD sobre pacientes, comunicarse con una base de datos MySQL y generar tarjetas de pacientes con un código QR que puede ser escaneado con cualquier dispositivo compatible.

## Características Principales

- **Gestión de Pacientes:**
  - Crear, leer, actualizar y eliminar registros de pacientes.
  - Almacenar información detallada como nombre, fecha de nacimiento, contacto, ocupación y más.

- **Base de Datos MySQL:**
  - Comunicación fluida con una base de datos MySQL para almacenar y gestionar los datos de forma eficiente.

- **Generación de Tarjetas con QR:**
  - Cada paciente registrado obtiene un código único.
  - Se genera una tarjeta personalizada con un código QR que contiene la información básica del paciente.
  - El QR puede ser escaneado con dispositivos móviles para acceder rápidamente a los datos del paciente.

- **Interfaz Amigable:**
  - Interfaz gráfica diseñada para facilitar el uso a personal administrativo.

## Requisitos del Sistema

### Software
- **Python 3.8+**
- Librerías necesarias:
  - `tkinter` (para la interfaz gráfica)
  - `mysql-connector-python` (para comunicación con MySQL)
  - `qrcode` (para generación de códigos QR)
  - `pillow` (para manipulación de imágenes)

### Hardware
- PC con sistema operativo Windows, macOS o Linux.
- Conexión a internet para acceder a la base de datos MySQL si está alojada en la nube.

### Base de Datos
Estructura de la tabla `pacientes` en MySQL:

```sql
CREATE TABLE IF NOT EXISTS pacientes (
    id INT AUTO_INCREMENT PRIMARY KEY,
    full_name VARCHAR(255) NOT NULL,
    birth_date DATE NOT NULL,
    age INT NOT NULL,
    gender ENUM('Masculino', 'Femenino', 'Otro') NOT NULL,
    occupation VARCHAR(255) NOT NULL,
    contact_number VARCHAR(15) NOT NULL,
    email VARCHAR(255) NOT NULL,
    codigo_unico VARCHAR(50) NOT NULL UNIQUE,
    created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP
);
```

## Instalación

1. **Clonar el Repositorio:**
   ```bash
   git clone <URL_DEL_REPOSITORIO>
   cd <NOMBRE_DEL_REPOSITORIO>
   ```

2. **Configurar la Base de Datos:**
   - Crear una base de datos en MySQL.
   - Importar el script SQL proporcionado en el directorio `BD` para crear las tablas necesarias.

3. **Instalar Dependencias:**
   ```bash
   pip install mysql-connector-python qrcode pillow
   ```

4. **Configurar Conexión a la Base de Datos:**
   - Editar el archivo de configuración `config/database.py` con las credenciales de tu base de datos.

5. **Ejecutar la Aplicación:**
   ```bash
   python main.py
   ```

## Uso

- Navegar por la interfaz para realizar operaciones CRUD.
- Generar tarjetas de pacientes y escanear los códigos QR generados para acceder a los datos del paciente.

## Contribuciones

Si deseas contribuir al proyecto, por favor abre un *pull request* o crea un *issue* para discutir tus propuestas.

## Licencia

Este proyecto está licenciado bajo la [MIT License](LICENSE).

## Capturas de Pantalla

1. **Pantalla Principal**
   ![Pantalla Principal](screenshots/main_screen.png)

2. **Formulario de Registro de Pacientes**
   ![Formulario de Registro](screenshots/register_form.png)

3. **Tarjeta con Código QR**
   ![Tarjeta QR](screenshots/qr_card.png)

---

¡Gracias por usar nuestro software de gestión para consultorios médicos! Si tienes dudas o comentarios, no dudes en contactarnos.
