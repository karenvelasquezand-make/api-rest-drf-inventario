# API REST de gestión de productos e inventario

Proyecto académico desarrollado con Python, Django y Django REST Framework (DRF). Permite administrar categorías y productos mediante operaciones CRUD.

## 1. Requisitos
- Python 3.10 o superior.
- pip.
- Visual Studio Code (recomendado).

## 2. Instalación en Windows
Abre la carpeta del proyecto en Visual Studio Code. En Terminal > New Terminal ejecuta:

```bash
py -m venv venv
venv\Scripts\activate
py -m pip install -r requirements.txt
py manage.py makemigrations inventario
py manage.py migrate
py manage.py runserver
```

Si el comando `py` no funciona, prueba reemplazarlo por `python`.

Abre en el navegador: http://127.0.0.1:8000/api/

## 3. Endpoints disponibles

| Método | URL | Acción |
|---|---|---|
| GET | /api/categorias/ | Listar categorías |
| POST | /api/categorias/ | Crear categoría |
| GET | /api/categorias/1/ | Consultar una categoría |
| PUT/PATCH | /api/categorias/1/ | Actualizar categoría |
| DELETE | /api/categorias/1/ | Eliminar categoría |
| GET | /api/productos/ | Listar productos |
| POST | /api/productos/ | Crear producto |
| GET | /api/productos/1/ | Consultar un producto |
| PUT/PATCH | /api/productos/1/ | Actualizar producto |
| DELETE | /api/productos/1/ | Eliminar producto |

El número `1` es un identificador de ejemplo. Debe reemplazarse por el ID real del registro.

## 4. Orden recomendado para probar
1. Entra a `/api/categorias/` y registra una categoría con POST.
2. Entra a `/api/productos/` y registra un producto. Usa el ID de categoría creado.
3. Actualiza el stock o el precio desde el detalle del producto.
4. Elimina un producto de prueba.
5. Comprueba que GET muestre los cambios.

Ejemplo de producto en formato JSON:
```json
{
  "nombre": "Bolso clásico",
  "descripcion": "Bolso de uso diario",
  "precio": "79.90",
  "stock": 10,
  "categoria": 1
}
```

## 5. Pruebas automáticas
Con el entorno virtual activado, ejecuta:
```bash
py manage.py test
```
El proyecto incluye pruebas para listar, crear, actualizar y eliminar productos.

## 6. GitHub
Crea un repositorio público llamado `api-rest-drf-inventario`. Sube el contenido de esta carpeta, pero NO subas `venv/` ni `db.sqlite3`. El archivo `.gitignore` ya excluye esos elementos.

## Nota académica
Este proyecto está configurado para prácticas locales. Antes de publicarlo en producción se deben configurar una clave secreta segura, `DEBUG=False`, permisos y autenticación.
