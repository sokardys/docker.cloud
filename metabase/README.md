# Insights

Para permitir el acceso de insights a la BBDD de producción para extraer datos,
se habilita un tunel ssh contra el contenedor de mongo. Para eso hay que incluir
un directorio ssh_keys en esta misma ruta con las claves autorizadas para hacer
login via ssh.

Hay que asegurar que los permisos sean 600 para que el cliente de ssh permita
hacer la conexión.
