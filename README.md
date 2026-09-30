# Gestión de restaurante con Django

Aplicación web académica para gestionar la atención de un restaurante: mesas, pedidos, platos, categorías y usuarios. Incluye generación de tickets PDF.

## Funcionalidades implementadas

- Inicio y cierre de sesión y gestión de usuarios.
- Gestión de mesas y estados de atención.
- Registro, consulta, actualización de estado y cancelación de pedidos.
- Administración de platos y categorías del menú.
- Descarga de tickets PDF mediante ReportLab.

## Tecnologías

Python, Django 5.0.7, SQLite, HTML, CSS, JavaScript y ReportLab. Las versiones de dependencias están en [requirements.txt](requirements.txt).

## Organización

| Ruta | Responsabilidad |
| --- | --- |
| [restaurante_app/models.py](restaurante_app/models.py) | Modelos de usuarios, menú, mesas y pedidos |
| [restaurante_app/views.py](restaurante_app/views.py) | Operaciones e interacción con las páginas |
| [restaurante_app/urls.py](restaurante_app/urls.py) | Rutas de la aplicación |
| [restaurante_app/templates](restaurante_app/templates) | Plantillas HTML |
| [restaurante_app/static](restaurante_app/static) | Recursos de la interfaz |
| [restaurante_app/migrations](restaurante_app/migrations) | Evolución del esquema de datos |
| [restaurante_project](restaurante_project) | Configuración del proyecto Django |

## Preparación local

Desde la raíz del repositorio, con Python compatible con Django 5:

```bash
python -m venv .venv
# Linux/macOS
source .venv/bin/activate
# Windows PowerShell: .venv\Scripts\Activate.ps1
python -m pip install -r requirements.txt
python manage.py migrate
python manage.py createsuperuser
python manage.py runserver
```

Abrir http://127.0.0.1:8000/. Para un entorno nuevo, revisar los catálogos de tipos de usuario, estados de mesa y estados de pedido requeridos por los modelos y las vistas. El repositorio conserva su base SQLite histórica; no hay un comando de carga de datos de demostración documentado.

## Recorrido para una demostración

1. Iniciar sesión.
2. Preparar categorías, platos y mesas.
3. Abrir una mesa y registrar un pedido.
4. Consultar o actualizar el estado del pedido.
5. Generar y descargar un ticket.

Este recorrido describe las funciones presentes en el código y debe comprobarse con datos de ejemplo antes de grabar una demo.

## Estado y próximos pasos

Proyecto académico, con configuración orientada al desarrollo local. [tests.py](restaurante_app/tests.py) conserva la plantilla inicial de Django: todavía no documenta una batería de pruebas específica. La instalación y el recorrido completo requieren validación en un entorno limpio.

Como siguientes mejoras: datos de demostración reproducibles, capturas del flujo, pruebas de pedidos y estados, y separación de responsabilidades de las vistas. No se publican métricas de cobertura ni una demo que no hayan sido verificadas.
