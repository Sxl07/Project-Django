# MiniProject-Django | MicroBilling

[Español](#español) | [English](#english)

---

## Español

## Descripción

**MiniProject-Django** es una práctica académica desarrollada con Django. El proyecto implementa una aplicación web llamada **MicroBilling**, orientada a la gestión básica de insumos, proveedores y pedidos.

La aplicación permite registrar usuarios, iniciar sesión y acceder a módulos protegidos donde se pueden administrar proveedores, insumos y pedidos mediante operaciones CRUD. También calcula información útil de los pedidos, como el monto total a partir de la cantidad solicitada y el precio del insumo.

Este proyecto fue desarrollado como ejercicio práctico para fortalecer conocimientos en desarrollo web con Django, manejo de modelos, formularios, vistas, plantillas, autenticación y persistencia con SQLite.

## Objetivo del proyecto

El objetivo principal fue construir una aplicación web funcional usando Django, aplicando conceptos como:

- Estructura de proyectos Django
- Aplicaciones internas separadas por responsabilidad
- Modelos y relaciones entre entidades
- Formularios basados en modelos
- Vistas protegidas con autenticación
- Plantillas HTML
- Operaciones CRUD
- Persistencia de datos con SQLite

## Funcionalidades principales

### Autenticación

El proyecto incluye un módulo de cuentas con las siguientes funcionalidades:

- Página de inicio
- Registro de usuario
- Inicio de sesión
- Cierre de sesión
- Página protegida para usuarios autenticados

### Gestión de proveedores

Permite administrar proveedores con información básica:

- Nombre
- Dirección
- Teléfono

Operaciones disponibles:

- Listar proveedores
- Crear proveedor
- Editar proveedor
- Eliminar proveedor

### Gestión de insumos

Permite administrar los insumos asociados a proveedores.

Campos principales:

- Nombre
- Descripción
- Unidad de medida
- Precio
- Proveedor relacionado

Operaciones disponibles:

- Listar insumos
- Ver detalle de un insumo
- Crear insumo
- Editar insumo
- Eliminar insumo

### Gestión de pedidos

Permite crear pedidos asociados a un insumo.

Campos principales:

- Insumo
- Cantidad
- Fecha automática del pedido
- Estado del pedido

Estados disponibles:

- Pagado
- Pendiente
- Cancelado

La vista de pedidos muestra información calculada, como:

- Proveedor
- Insumo
- Monto total
- Fecha
- Estado

## Tecnologías utilizadas

- Python
- Django
- SQLite
- HTML
- CSS
- Django Templates
- Django Authentication

## Estructura general del proyecto

```text
MiniProject-Django/
└── MicroBilling/
    ├── manage.py
    ├── db.sqlite3
    ├── MicroBilling/
    │   ├── settings.py
    │   ├── urls.py
    │   ├── asgi.py
    │   └── wsgi.py
    ├── accounts/
    │   ├── views.py
    │   ├── urls.py
    │   └── templates/accounts/
    ├── insumos_app/
    │   ├── models.py
    │   ├── forms.py
    │   ├── views.py
    │   ├── migrations/
    │   └── templates/
    ├── static/
    │   └── styles.css
    └── media/
        └── logo.png
```

## Modelos principales

### Proveedor

Representa a un proveedor de insumos.

Campos:

- `nombre`
- `direccion`
- `telefono`

### Insumo

Representa un insumo registrado en el sistema.

Campos:

- `nombre`
- `descripcion`
- `unidad_medida`
- `precio`
- `proveedor`

### Pedido

Representa una solicitud o pedido de insumos.

Campos:

- `insumo`
- `cantidad`
- `fecha_pedido`
- `estado`

## Rutas principales

### Cuentas

| Ruta | Descripción |
|---|---|
| `/` | Página de inicio |
| `/accounts/register/` | Registro de usuario |
| `/accounts/login/` | Inicio de sesión |
| `/accounts/logout/` | Cierre de sesión |
| `/accounts/protected/` | Página protegida |

### Insumos

| Ruta | Descripción |
|---|---|
| `/insumos/` | Lista de insumos |
| `/insumos/<id>/` | Detalle de insumo |
| `/insumos/crear/` | Crear insumo |
| `/insumos/<id>/editar/` | Editar insumo |
| `/insumos/<id>/eliminar/` | Eliminar insumo |

### Proveedores

| Ruta | Descripción |
|---|---|
| `/proveedores/` | Lista de proveedores |
| `/proveedores/crear/` | Crear proveedor |
| `/proveedores/<id>/editar/` | Editar proveedor |
| `/proveedores/<id>/eliminar/` | Eliminar proveedor |

### Pedidos

| Ruta | Descripción |
|---|---|
| `/pedidos/` | Lista de pedidos |
| `/pedidos/crear/` | Crear pedido |
| `/pedidos/<id>/editar/` | Editar pedido |
| `/pedidos/<id>/eliminar/` | Eliminar pedido |

## Cómo ejecutar el proyecto localmente

### 1. Clonar el repositorio

```bash
git clone https://github.com/Sxl07/MiniProject-Django.git
cd MiniProject-Django/MicroBilling
```

### 2. Crear un entorno virtual

```bash
python -m venv venv
```

Activar el entorno virtual:

En Windows:

```bash
venv\Scripts\activate
```

En Linux o macOS:

```bash
source venv/bin/activate
```

### 3. Instalar Django

Si el proyecto no incluye un archivo `requirements.txt`, instala Django manualmente:

```bash
pip install django
```

### 4. Aplicar migraciones

```bash
python manage.py migrate
```

### 5. Ejecutar el servidor de desarrollo

```bash
python manage.py runserver
```

### 6. Abrir la aplicación

En el navegador:

```text
http://127.0.0.1:8000/
```

## Notas del proyecto

- La base de datos configurada es SQLite.
- El proyecto usa el sistema de autenticación integrado de Django.
- Las vistas de insumos, proveedores y pedidos requieren que el usuario haya iniciado sesión.
- El proyecto incluye archivos estáticos y una carpeta de medios.
- Este repositorio representa una práctica académica y puede mejorarse agregando validaciones, pruebas, separación de configuración y documentación técnica adicional.

## Posibles mejoras futuras

- Agregar archivo `requirements.txt`
- Mejorar el diseño visual de las plantillas
- Agregar pruebas unitarias
- Implementar mensajes de éxito y error
- Agregar paginación y búsqueda
- Mejorar validaciones de formularios
- Separar configuración de desarrollo y producción
- Ocultar información sensible usando variables de entorno

---

## English

## Description

**MiniProject-Django** is an academic practice project developed with Django. The project implements a web application called **MicroBilling**, focused on the basic management of supplies, suppliers, and orders.

The application allows users to register, log in, and access protected modules where suppliers, supplies, and orders can be managed through CRUD operations. It also calculates useful order information, such as the total amount based on the requested quantity and the supply price.

This project was developed as a practical exercise to strengthen knowledge in Django web development, models, forms, views, templates, authentication, and data persistence with SQLite.

## Project goal

The main goal was to build a functional web application using Django while applying concepts such as:

- Django project structure
- Internal apps separated by responsibility
- Models and entity relationships
- Model-based forms
- Authentication-protected views
- HTML templates
- CRUD operations
- Data persistence with SQLite

## Main features

### Authentication

The project includes an accounts module with the following features:

- Home page
- User registration
- Login
- Logout
- Protected page for authenticated users

### Supplier management

Allows users to manage suppliers with basic information:

- Name
- Address
- Phone number

Available operations:

- List suppliers
- Create supplier
- Edit supplier
- Delete supplier

### Supply management

Allows users to manage supplies associated with suppliers.

Main fields:

- Name
- Description
- Unit of measure
- Price
- Related supplier

Available operations:

- List supplies
- View supply details
- Create supply
- Edit supply
- Delete supply

### Order management

Allows users to create orders associated with a supply.

Main fields:

- Supply
- Quantity
- Automatic order date
- Order status

Available statuses:

- Paid
- Pending
- Canceled

The order list view displays calculated information such as:

- Supplier
- Supply
- Total amount
- Date
- Status

## Technologies used

- Python
- Django
- SQLite
- HTML
- CSS
- Django Templates
- Django Authentication

## General project structure

```text
MiniProject-Django/
└── MicroBilling/
    ├── manage.py
    ├── db.sqlite3
    ├── MicroBilling/
    │   ├── settings.py
    │   ├── urls.py
    │   ├── asgi.py
    │   └── wsgi.py
    ├── accounts/
    │   ├── views.py
    │   ├── urls.py
    │   └── templates/accounts/
    ├── insumos_app/
    │   ├── models.py
    │   ├── forms.py
    │   ├── views.py
    │   ├── migrations/
    │   └── templates/
    ├── static/
    │   └── styles.css
    └── media/
        └── logo.png
```

## Main models

### Supplier

Represents a supply provider.

Fields:

- `nombre`
- `direccion`
- `telefono`

### Supply

Represents a supply registered in the system.

Fields:

- `nombre`
- `descripcion`
- `unidad_medida`
- `precio`
- `proveedor`

### Order

Represents a supply request or order.

Fields:

- `insumo`
- `cantidad`
- `fecha_pedido`
- `estado`

## Main routes

### Accounts

| Route | Description |
|---|---|
| `/` | Home page |
| `/accounts/register/` | User registration |
| `/accounts/login/` | Login |
| `/accounts/logout/` | Logout |
| `/accounts/protected/` | Protected page |

### Supplies

| Route | Description |
|---|---|
| `/insumos/` | Supply list |
| `/insumos/<id>/` | Supply detail |
| `/insumos/crear/` | Create supply |
| `/insumos/<id>/editar/` | Edit supply |
| `/insumos/<id>/eliminar/` | Delete supply |

### Suppliers

| Route | Description |
|---|---|
| `/proveedores/` | Supplier list |
| `/proveedores/crear/` | Create supplier |
| `/proveedores/<id>/editar/` | Edit supplier |
| `/proveedores/<id>/eliminar/` | Delete supplier |

### Orders

| Route | Description |
|---|---|
| `/pedidos/` | Order list |
| `/pedidos/crear/` | Create order |
| `/pedidos/<id>/editar/` | Edit order |
| `/pedidos/<id>/eliminar/` | Delete order |

## How to run the project locally

### 1. Clone the repository

```bash
git clone https://github.com/Sxl07/MiniProject-Django.git
cd MiniProject-Django/MicroBilling
```

### 2. Create a virtual environment

```bash
python -m venv venv
```

Activate the virtual environment:

On Windows:

```bash
venv\Scripts\activate
```

On Linux or macOS:

```bash
source venv/bin/activate
```

### 3. Install Django

If the project does not include a `requirements.txt` file, install Django manually:

```bash
pip install django
```

### 4. Apply migrations

```bash
python manage.py migrate
```

### 5. Run the development server

```bash
python manage.py runserver
```

### 6. Open the application

In the browser:

```text
http://127.0.0.1:8000/
```

## Project notes

- The configured database is SQLite.
- The project uses Django's built-in authentication system.
- The supplies, suppliers, and orders views require the user to be logged in.
- The project includes static files and a media folder.
- This repository represents an academic practice project and can be improved with validations, tests, configuration separation, and additional technical documentation.

## Possible future improvements

- Add a `requirements.txt` file
- Improve the visual design of the templates
- Add unit tests
- Implement success and error messages
- Add pagination and search
- Improve form validations
- Separate development and production settings
- Hide sensitive information using environment variables
