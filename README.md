# 🚀 Insertar IDs específicos en una tabla con `AUTO_INCREMENT` o `IDENTITY` y mantener la secuencia

```sql
-- 🔹 Crear la tabla con AUTO_INCREMENT en MySQL
CREATE TABLE mi_tabla (
    id INT AUTO_INCREMENT PRIMARY KEY,
    nombre VARCHAR(100) NOT NULL
);

-- 🔹 Crear la tabla con IDENTITY en SQL Server
CREATE TABLE mi_tabla (
    id INT IDENTITY(1,1) PRIMARY KEY,
    nombre NVARCHAR(100) NOT NULL
);

-- 🔹 Desactivar AUTO_INCREMENT en MySQL
SET SESSION sql_mode='NO_AUTO_VALUE_ON_ZERO';

-- 🔹 Desactivar IDENTITY en SQL Server
SET IDENTITY_INSERT mi_tabla ON;

-- 🔹 Insertar registros con IDs específicos
INSERT INTO mi_tabla (id, nombre) VALUES 
(1, 'Registro 1'),
(3, 'Registro 2'),
(5, 'Registro 3'),
(6, 'Registro 4'),
(24, 'Registro 5');

-- 🔹 Reactivar AUTO_INCREMENT en MySQL
ALTER TABLE mi_tabla AUTO_INCREMENT = 25;

-- 🔹 Reactivar IDENTITY en SQL Server
SET IDENTITY_INSERT mi_tabla OFF;

-- 🔹 Insertar nuevos registros sin especificar ID
INSERT INTO mi_tabla (nombre) VALUES ('Nuevo Registro');  -- El nuevo ID será 25 automáticamente 🚀
