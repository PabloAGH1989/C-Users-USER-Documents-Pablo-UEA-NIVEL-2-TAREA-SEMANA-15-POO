# Restaurante App - Semana 15

Aplicación modular desarrollada con Python y Tkinter para gestionar usuarios, productos y ventas de un restaurante. Esta versión conserva la estructura base del proyecto y evoluciona la funcionalidad para incorporar la nueva sección de ventas, siguiendo el flujo de eventos del sistema: usuario, botón, callback, servicio, persistencia y respuesta visual.

## Objetivo de la semana

La Semana 15 incorpora la gestión de ventas como evolución del proyecto anterior. Se mantiene el inicio de sesión, la navegación por secciones y la gestión de productos, y además se añade la capacidad de registrar una venta relacionando un usuario con un producto mediante una interfaz intuitiva y una validación centralizada en `RestauranteServicio`.

## Estructura del proyecto

restaurante_app/
├── datos/
│   ├── productos.json
│   ├── usuarios.json
│   └── ventas.json
├── modelos/
│   ├── __init__.py
│   ├── producto.py
│   ├── usuario.py
│   └── venta.py
├── servicios/
│   ├── __init__.py
│   ├── archivo_servicio.py
│   └── restaurante_servicio.py
├── ui/
│   ├── __init__.py
│   ├── login_view.py
│   └── main_view.py
├── assets/
│   ├── login.png
│   ├── products.png
│   ├── users.png
│   ├── save.png
│   └── delete.png
├── main.py
├── README.md

## Funcionalidades implementadas

- Inicio de sesión con validación de credenciales.
- Vista principal con navegación por secciones.
- Consulta de usuarios registrados.
- Gestión de productos:
  - Registrar
  - Consultar por código
  - Actualizar
  - Eliminar
- Nueva sección de ventas en la interfaz principal.
- Selección de usuario y producto mediante `ttk.Combobox`.
- Botón `Registrar venta` con `command=self.registrar_venta` para ejecutar el callback desde la interfaz.
- Validación y persistencia de ventas en `RestauranteServicio`.
- Almacenamiento en `datos/ventas.json`.
- Actualización inmediata de la tabla de ventas en la vista.

## Flujo funcional

El flujo sigue la lógica de eventos del proyecto:

1. Usuario acciona un botón o selector de la interfaz.
2. El callback de la vista coordina la operación.
3. `RestauranteServicio` valida la información.
4. Se persiste la venta en `ventas.json`.
5. La vista actualiza la tabla de ventas y muestra la respuesta al usuario.

## Persistencia

La capa de datos se mantiene separada de la interfaz. El acceso a JSON se realiza desde `ArchivoServicio`, mientras que las validaciones y reglas del negocio quedan centralizadas en `RestauranteServicio`.

## Ejecución

Desde la carpeta del proyecto ejecuta:

```bash
python main.py
```

## Credenciales de prueba

- Usuario: admin
- Contraseña: 1234

## Observación

El proyecto conserva la arquitectura modular desarrollada en semanas anteriores y evoluciona con una nueva sección de ventas, manteniendo una experiencia visual clara, ordenada y coherente con el dominio del restaurante.
