# Consigna

## Desafío complementario

### Sistema de Recuperación de Contraseña

- Implementar un sistema de recuperación de contraseña que envíe un correo con un enlace para restablecerla.
  - El enlace del correo debe expirar después de 1 hora de enviado.
  - Evitar que el usuario pueda restablecer la contraseña con la misma contraseña anterior.
  - Si el enlace expira, redirigir a una vista para generar nuevamente el correo de restablecimiento con una nueva duración de 1 hora.

### Nuevo Rol "Premium"

- Crear un nuevo rol llamado "premium" en el esquema de usuario, con permisos para crear productos.

### Modificación del Esquema de Producto

- Añadir un campo "owner" al esquema de producto, que haga referencia al usuario que creó el producto.
  - Si un producto se crea sin owner, establecer "admin" como owner por defecto.
  - El campo owner debe almacenar solo el correo electrónico o _id del usuario que lo creó (restringido a usuarios premium).

### Modificación de Permisos en Productos

- Un usuario premium solo puede borrar los productos que le pertenecen.
- El administrador puede borrar cualquier producto, incluso si tiene un owner.

### Lógica de Carrito

- Modificar la lógica del carrito para que un usuario premium no pueda agregar a su carrito un producto que le pertenece.

### Nueva Ruta en el Router de API

- Implementar una nueva ruta en el router de api/users:
  - /api/users/premium/:uid para cambiar el rol de un usuario entre "user" y "premium".
