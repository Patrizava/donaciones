#donaciones
#código de formulario donantes

<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <title>Agregar Donante</title>
    <script>
        function validarDonante() {
            let nombre = document.forms["formulario_donante"]["nombre"].value;
            let email = document.forms["formulario_donante"]["email"].value;
            let direccion = document.forms["formulario_donante"]["direccion"].value;
            let telefono = document.forms["formulario_donante"]["telefono"].value;
            if (nombre.trim() === "") {
                alert("El nombre es obligatorio");
                return false;
            }
            let reEmail = /\S+@\S+\.\S+/;
            if (!reEmail.test(email)) {
                alert("Email no válido");
                return false;
            }
            return true;
        }
    </script>
</head>
<body>
    <h2>Agregar Donante</h2>
    <form name="formulario_donante" action="insertar_donante.php" method="POST" onsubmit="return validarDonante()">
        <label>Nombre:</label><br>
        <input type="text" name="nombre" required><br><br>
        <label>Email:</label><br>
        <input type="email" name="email" required><br><br>
        <label>Dirección:</label><br>
        <input type="text" name="direccion"><br><br>
        <label>Teléfono:</label><br>
        <input type="text" name="telefono"><br><br>
        <input type="submit" value="Agregar Donante">
    </form>
</body>
</html>
