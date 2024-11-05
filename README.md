# REDON
PERSONAL AUTORIZADO 
<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Formulario de Registro</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            margin: 20px;
            padding: 20px;
        }
        label {
            display: block;
            margin: 10px 0 5px;
        }
        input {
            width: 100%;
            padding: 8px;
            margin: 5px 0;
            border: 1px solid #ddd;
            border-radius: 4px;
        }
        button {
            padding: 10px 20px;
            background-color: #4CAF50;
            color: white;
            border: none;
            border-radius: 4px;
            cursor: pointer;
        }
        button:hover {
            background-color: #45a049;
        }
    </style>
</head>
<body>
    <h1>Formulario de Registro</h1>
    <form id="formulario">
        <label for="nombre">Nombre Completo:</label>
        <input type="text" id="nombre" name="nombre" required>

        <label for="correo">Correo Electrónico:</label>
        <input type="email" id="correo" name="correo" required>

        <label for="clave">Contraseña:</label>
        <input type="password" id="clave" name="clave" required>

        <button type="button" onclick="guardarDatos()">Registrar</button>
    </form>

    <script>
        // Función para guardar los datos en el LocalStorage
        function guardarDatos() {
            const nombre = document.getElementById('nombre').value;
            const correo = document.getElementById('correo').value;
            const clave = document.getElementById('clave').value;

            // Verificar que los campos no estén vacíos
            if (nombre === '' || correo === '' || clave === '') {
                alert('Por favor, completa todos los campos.');
                return;
            }

            // Crear un objeto con los datos
            const datosUsuario = {
                nombre: nombre,
                correo: correo,
                clave: clave
            };

            // Guardar los datos en el LocalStorage
            let usuariosGuardados = JSON.parse(localStorage.getItem('usuarios')) || [];
            usuariosGuardados.push(datosUsuario);
            localStorage.setItem('usuarios', JSON.stringify(usuariosGuardados));

            alert('¡Datos registrados correctamente!');

            // Limpiar el formulario
            document.getElementById('formulario').reset();
        }
    </script>
</body>
</html>
