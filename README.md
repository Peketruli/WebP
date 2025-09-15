<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Rebeldía IN.AR</title>
    <script src="https://cdnjs.cloudflare.com/ajax/libs/jspdf/2.5.1/jspdf.umd.min.js"></script> <!-- Librería jsPDF -->
    <style>
        body {
            background: linear-gradient(45deg, #FF5733, #FF8D1A, #FFC300, #FF5733);
            background-size: 400% 400%;
            animation: gradientBG 10s ease infinite;
            color: white;
            font-family: Arial, sans-serif;
            text-align: center;
            padding: 50px;
            position: relative;
            margin-bottom: 100px; /* Espacio para los botones inferiores */
        }

        @keyframes gradientBG {
            0% { background-position: 0% 50%; }
            50% { background-position: 100% 50%; }
            100% { background-position: 0% 50%; }
        }

        .auth-container, .user-info {
            position: absolute;
            top: 20px;
            right: 20px;
            display: flex;
            align-items: center;
            gap: 10px;
        }

        .auth-button {
            padding: 10px 20px;
            font-size: 1em;
            color: white;
            background-color: #333;
            border: none;
            cursor: pointer;
            border-radius: 5px;
            text-decoration: none;
            margin: 5px;
        }

        .user-info {
            display: none;
            cursor: pointer;
        }

        #userLogo {
            width: 40px;
            height: 40px;
            border-radius: 50%;
        }

        #userName {
            font-size: 1em;
            font-weight: bold;
        }

        /* Menú desplegable */
        .dropdown-menu {
            display: none;
            position: absolute;
            top: 60px;
            right: 20px;
            background-color: white;
            color: black;
            border-radius: 5px;
            box-shadow: 0 4px 8px rgba(0, 0, 0, 0.2);
            width: 150px;
            text-align: left;
        }

        .dropdown-menu td {
            padding: 10px;
            cursor: pointer;
        }

        .dropdown-menu td:hover {
            background-color: #ddd;
        }

        /* Contenedor de los botones de navegación */
        .nav-container {
            position: fixed;
            bottom: 20px;
            left: 0;
            width: 100%;
            background-color: rgba(0, 0, 0, 0.7);
            padding: 15px 0;
            display: flex;
            justify-content: space-around;
            align-items: center;
        }

        .nav-button {
            background-color: #007BFF;
            color: white;
            padding: 12px;
            font-size: 16px;
            border: none;
            border-radius: 8px;
            cursor: pointer;
            width: 18%;
            transition: background-color 0.3s;
        }

        .nav-button:hover {
            background-color: #0056b3;
        }

        /* Botón de descarga de PDF */
        #pdfButtonContainer {
            margin-top: 20px;
        }

        #downloadButton {
            background-color: #dc3545;
            padding: 12px;
            border: none;
            border-radius: 8px;
            color: white;
            font-size: 16px;
            cursor: pointer;
            display: none;
        }

        #downloadButton:hover {
            background-color: #c82333;
        }
    </style>
</head>
<body>
    <h1>Bienvenidos a Rebeldía IN.AR</h1>

    <!-- Contenedor del botón de registro o info del usuario -->
    <div class="auth-container" id="authContainer">
        <button class="auth-button" onclick="window.location.href='login.html'">Iniciar sesión o registrarse</button>
    </div>

    <!-- Sección con el nombre y el logo del usuario -->
    <div class="user-info" id="userInfo">
        <h3 id="userName"></h3>
        <img id="userLogo" src="logoDefault.png" alt="Logo del usuario">
    </div>

    <!-- Menú desplegable -->
    <div class="dropdown-menu" id="dropdownMenu">
        <table>
            <tr><td onclick="goToSettings()">⚙ Ajustes</td></tr>
            <tr><td onclick="logout()">🚪 Cerrar sesión</td></tr>
        </table>
    </div>

    <!-- Botón para descargar el PDF de registros -->
    <div id="pdfButtonContainer">
        <button id="downloadButton" onclick="downloadPDF()">Descargar PDF de Registros</button>
    </div>

    <!-- Contenedor de los botones de navegación -->
    <div class="nav-container">
        <button class="nav-button" onclick="window.location.href='blog.html'">Blog</button>
        <button class="nav-button" onclick="window.location.href='clubs.html'">Clubs</button>
        <button class="nav-button" onclick="window.location.href='calendario.html'">Calendario</button>
        <button class="nav-button" onclick="window.location.href='Juegos.html'">Juegos</button>
        <button class="nav-button" onclick="window.open('https://youtube.com/@peketruli?si=M0dmkMnWkWuJJn_e', '_blank')">YouTube</button>
        <button class="nav-button" onclick="window.location.href='Encuesta.html'">Encuesta mejoras</button>
    </div>

    <h2>Bienvenidos a una página web que en mi opinión debería haber hecho el instituto hace mucho. Podéis hacer lo que queráis, podéis hacer un blog insultando a profesores, debatir, hacer grupos de trabajo, clubs… Si alguien informa a algún profesor o a alguien de dirección sobre la web, tendrá serios problemas. Aparte, la intención de la web es un sitio donde los alumnos se sientan libres de la cárcel del instituto de Arrigorriaga. Espero que disfrutéis.</h2>
    
    <h1>Motivo</h1> 
    <h2>Como el instituto solo piensa para sus beneficios, he pensado en hacer una web para los alumnos, donde el límite no existe y podéis sentiros libres de criticar a profesores o hacer todo lo que se puede hacer en la web. Gracias.</h2>

    <!-- Botón para descargar el PDF de registros -->
<div id="pdfButtonContainer">
    <button id="downloadButton" onclick="downloadPDF()">Descargar PDF de Registros</button>
</div>

<div id="creator-container" style="margin-top: 30px; text-align: center;">
    <a href="https://www.youtube.com/channel/UCp-DamhtfzOyV9wKrL873iQ" target="_blank" style="text-decoration: none; color: white;">
        <h3 style="margin-bottom: 10px; color: black;">Creado por Peketruli</h3>
    </a>
    <a href="https://www.youtube.com/channel/UCp-DamhtfzOyV9wKrL873iQ" target="_blank">
        <img id="creator-logo" src="logo.png" alt="Logo de Peketruli" style="width: 120px; height: 120px; border-radius: 50%;">
    </a>
</div>

<script>
    document.addEventListener("DOMContentLoaded", function () {
        loadUserInfo();

        const userInfo = document.getElementById("userInfo");
        const dropdownMenu = document.getElementById("dropdownMenu");

        userInfo.addEventListener("click", function () {
            // Alternar visibilidad del menú
            if (dropdownMenu.style.display === "block") {
                dropdownMenu.style.display = "none";
            } else {
                dropdownMenu.style.display = "block";
            }
        });

        // Cerrar el menú si se hace clic fuera de él
        document.addEventListener("click", function (event) {
            if (!userInfo.contains(event.target) && !dropdownMenu.contains(event.target)) {
                dropdownMenu.style.display = "none";
            }
        });
    });

    // Redirige a los ajustes
    function goToSettings() {
        window.location.href = 'ajustes.html';
    }

    // Cierra sesión
    function logout() {
    localStorage.removeItem("currentUser"); // Solo elimina el usuario actual
    window.location.href = 'login.html';
}

    // Carga los datos del usuario
    function loadUserInfo() {
        const user = JSON.parse(localStorage.getItem("currentUser"));
        const authContainer = document.getElementById("authContainer");
        const userInfo = document.getElementById("userInfo");

        if (user) {
            userInfo.style.display = "flex";
            authContainer.style.display = "none";
            document.getElementById("userName").textContent = user.username || "Usuario";
            document.getElementById("userLogo").src = user.logo || "logoDefault.png";

            if (user.email === "thunderfoll.ai@gmail.com") {
                document.getElementById("downloadButton").style.display = "block";
            }
        } else {
            userInfo.style.display = "none";
            authContainer.style.display = "flex";
        }
    }

    // Función para descargar el PDF
    function downloadPDF() {
        const { jsPDF } = window.jspdf;
        const doc = new jsPDF();
        let users = JSON.parse(localStorage.getItem("users")) || [];
        let content = "Datos de los registros:\n\n";

        users.forEach(user => {
            content += `Nombre de usuario: ${user.username}\nCorreo electrónico: ${user.email}\nLogo: ${user.logo ? "Sí" : "No"}\n\n`;
        });

        doc.text(content, 10, 10);
        doc.save("registros.pdf");
    }
</script>
</body>
</html>
