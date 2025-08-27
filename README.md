<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>PracticaEjercicios.com - Plataforma educativa con ejercicios interactivos</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <!-- Google Sign-In SDK -->
    <script src="https://accounts.google.com/gsi/client" async defer></script>
    <!-- Facebook SDK -->
    <script async defer crossorigin="anonymous" src="https://connect.facebook.net/es_ES/sdk.js#xfbml=1&version=v12.0"></script>
    <!-- Google AdSense Script -->
    <script async src="https://pagead2.googlesyndication.com/pagead/js/adsbygoogle.js?client=ca-pub-3235252091502864" crossorigin="anonymous"></script>
    <style>
        :root {
            --primary-color: #4a6fa5;
            --secondary-color: #166088;
            --accent-color: #4cb5f5;
            --light-color: #f8f9fa;
            --dark-color: #343a40;
            --success-color: #28a745;
            --warning-color: #ffc107;
            --danger-color: #dc3545;
            --math-color: #ff0000;
            --language-color: #0000ff;
            --science-color: #800080;
            --social-color: #008000;
        }
        
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
        }
        
        body {
            background-color: #f5f7fa;
            color: #333;
            line-height: 1.6;
        }
        
        .container {
            width: 100%;
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 15px;
        }
        
        header {
            background: linear-gradient(135deg, var(--primary-color), var(--secondary-color));
            color: white;
            padding: 1rem 0;
            box-shadow: 0 2px 10px rgba(0, 0, 0, 0.1);
            position: sticky;
            top: 0;
            z-index: 100;
        }
        
        .header-content {
            display: flex;
            justify-content: space-between;
            align-items: center;
        }
        
        .logo {
            font-size: 1.8rem;
            font-weight: 700;
            display: flex;
            align-items: center;
        }
        
        .logo span {
            color: var(--accent-color);
        }
        
        nav ul {
            display: flex;
            list-style: none;
        }
        
        nav ul li {
            margin-left: 1.5rem;
        }
        
        nav ul li a {
            color: white;
            text-decoration: none;
            font-weight: 500;
            transition: color 0.3s;
        }
        
        nav ul li a:hover {
            color: var(--accent-color);
        }
        
        .hero {
            background: linear-gradient(rgba(74, 111, 165, 0.8), rgba(22, 96, 136, 0.9)), url('data:image/svg+xml;utf8,<svg xmlns="http://www.w3.org/2000/svg" width="100" height="100" viewBox="0 0 100 100"><rect fill="%234a6fa5" width="100" height="100"/><path fill="%23166088" d="M0 0L100 100" stroke-width="0"/></svg>');
            background-size: cover;
            color: white;
            padding: 4rem 0;
            text-align: center;
        }
        
        .hero h1 {
            font-size: 2.5rem;
            margin-bottom: 1rem;
        }
        
        .hero p {
            font-size: 1.2rem;
            max-width: 700px;
            margin: 0 auto 2rem;
        }
        
        .btn {
            display: inline-block;
            background-color: var(--accent-color);
            color: white;
            padding: 0.8rem 1.5rem;
            border-radius: 50px;
            text-decoration: none;
            font-weight: 600;
            transition: all 0.3s;
            border: none;
            cursor: pointer;
        }
        
        .btn:hover {
            background-color: #3a9bd5;
            transform: translateY(-3px);
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.1);
        }
        
        .btn-outline {
            background: transparent;
            border: 2px solid white;
        }
        
        .btn-outline:hover {
            background: white;
            color: var(--primary-color);
        }
        
        .categories {
            padding: 4rem 0;
        }
        
        .section-title {
            text-align: center;
            margin-bottom: 3rem;
            color: var(--dark-color);
        }
        
        .section-title h2 {
            font-size: 2.2rem;
            margin-bottom: 0.5rem;
        }
        
        .section-title p {
            color: #6c757d;
        }
        
        .category-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(250px, 1fr));
            gap: 2rem;
        }
        
        .category-card {
            background-color: white;
            border-radius: 10px;
            overflow: hidden;
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.05);
            transition: transform 0.3s;
        }
        
        .category-card:hover {
            transform: translateY(-5px);
        }
        
        .category-icon.math {
            background: var(--math-color);
        }
        
        .category-icon.language {
            background: var(--language-color);
        }
        
        .category-icon.science {
            background: var(--science-color);
        }
        
        .category-icon.social {
            background: var(--social-color);
        }
        
        .category-content {
            padding: 1.5rem;
        }
        
        .category-content h3 {
            margin-bottom: 0.5rem;
            color: var(--dark-color);
        }
        
        .category-content p {
            color: #6c757d;
            margin-bottom: 1rem;
        }
        
        .features {
            background-color: white;
            padding: 4rem 0;
        }
        
        .features-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(300px, 1fr));
            gap: 2rem;
        }
        
        .feature-card {
            text-align: center;
            padding: 2rem;
        }
        
        .feature-icon {
            font-size: 2.5rem;
            color: var(--primary-color);
            margin-bottom: 1rem;
        }
        
        .feature-card h3 {
            margin-bottom: 1rem;
            color: var(--dark-color);
        }
        
        .modal {
            display: none;
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background-color: rgba(0, 0, 0, 0.5);
            z-index: 1000;
            align-items: center;
            justify-content: center;
        }
        
        .modal-content {
            background-color: white;
            border-radius: 10px;
            width: 100%;
            max-width: 400px;
            padding: 2rem;
            box-shadow: 0 5px 25px rgba(0, 0, 0, 0.2);
        }
        
        .modal-header {
            display: flex;
            justify-content: space-between;
            align-items: center;
            margin-bottom: 1.5rem;
        }
        
        .close-modal {
            font-size: 1.5rem;
            cursor: pointer;
            color: #6c757d;
        }
        
        .social-login {
            display: flex;
            flex-direction: column;
            gap: 1rem;
            margin-bottom: 1.5rem;
        }
        
        .social-login button {
            width: 100%;
            padding: 0.8rem;
            border-radius: 4px;
            font-size: 1rem;
            display: flex;
            align-items: center;
            justify-content: center;
            gap: 0.5rem;
            cursor: pointer;
        }
        
        .google-btn {
            background-color: #4285F4;
            color: white;
            border: none;
        }
        
        .facebook-btn {
            background-color: #3b5998;
            color: white;
            border: none;
        }
        
        .form-footer {
            text-align: center;
            margin-top: 1.5rem;
        }
        
        .user-menu {
            position: relative;
        }
        
        .user-avatar {
            width: 40px;
            height: 40px;
            border-radius: 50%;
            background: var(--accent-color);
            color: white;
            display: flex;
            align-items: center;
            justify-content: center;
            cursor: pointer;
        }
        
        .user-dropdown {
            position: absolute;
            top: 100%;
            right: 0;
            background-color: white;
            border-radius: 8px;
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.1);
            width: 200px;
            padding: 1rem;
            margin-top: 0.5rem;
            display: none;
        }
        
        .user-dropdown.active {
            display: block;
        }
        
        .user-info {
            display: flex;
            align-items: center;
            margin-bottom: 1rem;
            padding-bottom: 1rem;
            border-bottom: 1px solid #eee;
        }
        
        .user-details {
            margin-left: 0.5rem;
        }
        
        .user-name {
            font-weight: 600;
            color: var(--dark-color);
        }
        
        .user-email {
            font-size: 0.8rem;
            color: #6c757d;
        }
        
        .user-stats {
            display: flex;
            justify-content: space-between;
            margin-bottom: 1rem;
        }
        
        .stat {
            text-align: center;
        }
        
        .stat-value {
            font-size: 1.2rem;
            font-weight: 600;
            color: var(--primary-color);
        }
        
        .stat-label {
            font-size: 0.8rem;
            color: #6c757d;
        }
        
        footer {
            background-color: var(--dark-color);
            color: white;
            padding: 3rem 0 1rem;
        }
        
        .footer-content {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(250px, 1fr));
            gap: 2rem;
            margin-bottom: 2rem;
        }
        
        .footer-column h3 {
            margin-bottom: 1.5rem;
            font-size: 1.2rem;
        }
        
        .footer-column ul {
            list-style: none;
        }
        
        .footer-column ul li {
            margin-bottom: 0.8rem;
        }
        
        .footer-column ul li a {
            color: #adb5bd;
            text-decoration: none;
            transition: color 0.3s;
        }
        
        .footer-column ul li a:hover {
            color: white;
        }
        
        .copyright {
            text-align: center;
            padding-top: 1.5rem;
            border-top: 1px solid #495057;
            color: #adb5bd;
            font-size: 0.9rem;
        }
        
        .ad-container {
            margin: 2rem auto;
            text-align: center;
        }
        
        @media (max-width: 768px) {
            .header-content {
                flex-direction: column;
                text-align: center;
            }
            
            nav ul {
                margin-top: 1rem;
                justify-content: center;
                flex-wrap: wrap;
            }
            
            nav ul li {
                margin: 0.5rem;
            }
            
            .hero h1 {
                font-size: 2rem;
            }
            
            .hero p {
                font-size: 1rem;
            }
            
            .category-grid, .features-grid {
                grid-template-columns: 1fr;
            }
            
            .ad-container {
                margin: 1rem auto;
            }
        }
    </style>
</head>
<body>
    <header>
        <div class="container header-content">
            <div class="logo">Practica<span>Ejercicios</span></div>
            <nav>
                <ul>
                    <li><a href="https://ayoubelouardy.github.io/Practicaejercicios/" target="_blank">Inicio</a></li>
                    <li><a href="https://ayoubelouardy.github.io/Practicaejercicios-Lengua-Castellana/" target="_blank">Lenguaje</a></li>
                    <li><a href="https://ayoubelouardy.github.io/Practicaejercicios-Matem-ticas/" target="_blank">Matemáticas</a></li>
                    <li><a href="https://ayoubelouardy.github.io/Practicaejercicios-Ciencias/" target="_blank">Ciencias</a></li>
                    <li><a href="https://ayoubelouardy.github.io/Practicaejercicios-Ciencias-Sociales/" target="_blank">Sociales</a></li>
                </ul>
            </nav>
            <div class="user-menu">
                <div class="user-avatar" id="userAvatar">
                    <i class="fas fa-user"></i>
                </div>
                <div class="user-dropdown" id="userDropdown">
                    <div class="user-info">
                        <div class="user-avatar">
                            <i class="fas fa-user"></i>
                        </div>
                        <div class="user-details">
                            <div class="user-name" id="userName">Invitado</div>
                            <div class="user-email" id="userEmail">No has iniciado sesión</div>
                        </div>
                    </div>
                    <div class="user-stats">
                        <div class="stat">
                            <div class="stat-value" id="completedExercises">0</div>
                            <div class="stat-label">Completados</div>
                        </div>
                        <div class="stat">
                            <div class="stat-value" id="correctAnswers">0%</div>
                            <div class="stat-label">Precisión</div>
                        </div>
                    </div>
                    <button class="btn" id="loginBtn" style="width: 100%;">Iniciar Sesión</button>
                </div>
            </div>
        </div>
    </header>

    <section class="hero">
        <div class="container">
            <h1>Mejora tus habilidades con ejercicios prácticos</h1>
            <p>Miles de ejercicios gratuitos para estudiantes de todas las edades y niveles educativos. Matemáticas, lenguaje, ciencias y mucho más.</p>
            <a href="#" class="btn" id="startBtn">Comenzar ahora</a>
            <a href="#" class="btn btn-outline" style="margin-left: 10px;">Ver ejemplos</a>
        </div>
    </section>

    <section class="categories">
        <div class="container">
            <div class="section-title">
                <h2>Materias Disponibles</h2>
                <p>Explora nuestros ejercicios por categoría</p>
            </div>
            <div class="category-grid">
                <div class="category-card">
                    <div class="category-icon math">∑</div>
                    <div class="category-content">
                        <h3>Matemáticas</h3>
                        <p>Álgebra, geometría, cálculo y más. Ejercicios para todos los niveles.</p>
                        <a href="https://ayoubelouardy.github.io/Practicaejercicios-Matem-ticas/" target="_blank" class="btn">Practicar</a>
                    </div>
                </div>
                <div class="category-card">
                    <div class="category-icon language"><i class="fas fa-book"></i></div>
                    <div class="category-content">
                        <h3>Lenguaje</h3>
                        <p>Gramática, ortografía, comprensión lectora y ejercicios de escritura.</p>
                        <a href="https://ayoubelouardy.github.io/Practicaejercicios-Lengua-Castellana/" target="_blank" class="btn">Practicar</a>
                    </div>
                </div>
                <div class="category-card">
                    <div class="category-icon science"><i class="fas fa-flask"></i></div>
                    <div class="category-content">
                        <h3>Ciencias</h3>
                        <p>Biología, física, química y ciencias de la tierra. Aprende experimentando.</p>
                        <a href="https://ayoubelouardy.github.io/Practicaejercicios-Ciencias/" target="_blank" class="btn">Practicar</a>
                    </div>
                </div>
                <div class="category-card">
                    <div class="category-icon social"><i class="fas fa-globe-americas"></i></div>
                    <div class="category-content">
                        <h3>Sociales</h3>
                        <p>Historia, geografía, economía y cultura general. Explora el mundo.</p>
                        <a href="https://ayoubelouardy.github.io/Practicaejercicios-Ciencias-Sociales/" target="_blank" class="btn">Practicar</a>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- AdSense Ad Block -->
    <div class="ad-container">
        <ins class="adsbygoogle"
             style="display:block"
             data-ad-client="ca-pub-3235252091502864"
             data-ad-slot="1234567890"
             data-ad-format="auto"
             data-full-width-responsive="true"></ins>
        <script>
            (adsbygoogle = window.adsbygoogle || []).push({});
        </script>
    </div>

    <section class="features">
        <div class="container">
            <div class="section-title">
                <h2>¿Por qué elegirnos?</h2>
                <p>Ventajas de nuestra plataforma educativa</p>
            </div>
            <div class="features-grid">
                <div class="feature-card">
                    <div class="feature-icon"><i class="fas fa-check-circle"></i></div>
                    <h3>Contenido de Calidad</h3>
                    <p>Ejercicios creados por educadores profesionales y revisados pedagógicamente.</p>
                </div>
                <div class="feature-card">
                    <div class="feature-icon"><i class="fas fa-sync-alt"></i></div>
                    <h3>Retroalimentación Inmediata</h3>
                    <p>Corrección automática con explicaciones detalladas para cada ejercicio.</p>
                </div>
                <div class="feature-card">
                    <div class="feature-icon"><i class="fas fa-chart-line"></i></div>
                    <h3>Seguimiento de Progreso</h3>
                    <p>Monitoriza tu evolución con estadísticas detalladas y recomendaciones personalizadas.</p>
                </div>
                <div class="feature-card">
                    <div class="feature-icon"><i class="fas fa-book-open"></i></div>
                    <h3>Amplia Variedad de Temas</h3>
                    <p>Desde álgebra hasta ciencias sociales, cubrimos todas las materias clave para tu aprendizaje.</p>
                </div>
                <div class="feature-card">
                    <div class="feature-icon"><i class="fas fa-mobile-alt"></i></div>
                    <h3>Accesibilidad Multiplataforma</h3>
                    <p>Practica desde cualquier dispositivo, en cualquier momento y lugar.</p>
                </div>
                <div class="feature-card">
                    <div class="feature-icon"><i class="fas fa-users"></i></div>
                    <h3>Comunidad de Aprendizaje</h3>
                    <p>Únete a miles de estudiantes que mejoran sus habilidades diariamente.</p>
                </div>
            </div>
        </div>
    </section>

    <div class="modal" id="loginModal">
        <div class="modal-content">
            <div class="modal-header">
                <h2>Iniciar Sesión</h2>
                <span class="close-modal">&times;</span>
            </div>
            <div class="social-login">
                <button class="google-btn" id="googleLoginBtn">
                    <i class="fab fa-google"></i> Iniciar sesión con Google
                </button>
                <button class="facebook-btn" id="facebookLoginBtn">
                    <i class="fab fa-facebook-f"></i> Iniciar sesión con Facebook
                </button>
            </div>
            <div class="form-footer">
                <p>¿No tienes cuenta? Debes registrarte con Google o Facebook para continuar.</p>
            </div>
        </div>
    </div>

    <footer>
        <div class="container">
            <div class="footer-content">
                <div class="footer-column">
                    <h3>PracticaEjercicios</h3>
                    <p>Plataforma educativa con miles de ejercicios gratuitos para estudiantes de todos los niveles.</p>
                </div>
                <div class="footer-column">
                    <h3>Enlaces rápidos</h3>
                    <ul>
                        <li><a href="https://ayoubelouardy.github.io/Practicaejercicios/" target="_blank">Inicio</a></li>
                        <li><a href="https://ayoubelouardy.github.io/Practicaejercicios-Lengua-Castellana/" target="_blank">Lenguaje</a></li>
                        <li><a href="https://ayoubelouardy.github.io/Practicaejercicios-Matem-ticas/" target="_blank">Matemáticas</a></li>
                        <li><a href="https://ayoubelouardy.github.io/Practicaejercicios-Ciencias/" target="_blank">Ciencias</a></li>
                        <li><a href="https://ayoubelouardy.github.io/Practicaejercicios-Ciencias-Sociales/" target="_blank">Sociales</a></li>
                    </ul>
                </div>
                <div class="footer-column">
                    <h3>Materias</h3>
                    <ul>
                        <li><a href="https://ayoubelouardy.github.io/Practicaejercicios-Matem-ticas/" target="_blank">Matemáticas</a></li>
                        <li><a href="https://ayoubelouardy.github.io/Practicaejercicios-Lengua-Castellana/" target="_blank">Lenguaje</a></li>
                        <li><a href="https://ayoubelouardy.github.io/Practicaejercicios-Ciencias/" target="_blank">Ciencias</a></li>
                        <li><a href="https://ayoubelouardy.github.io/Practicaejercicios-Ciencias-Sociales/" target="_blank">Sociales</a></li>
                    </ul>
                </div>
            </div>
            <div class="copyright">
                <p>&copy; 2023 PracticaEjercicios.com - Todos los derechos reservados</p>
            </div>
        </div>
    </footer>

    <script>
        window.fbAsyncInit = function() {
            FB.init({
                appId: 'YOUR_FACEBOOK_APP_ID',
                cookie: true,
                xfbml: true,
                version: 'v12.0'
            });
        };

        let userData = {
            loggedIn: false,
            name: "Invitado",
            email: "",
            completedExercises: 0,
            correctAnswers: 0,
            totalAnswers: 0
        };

        const userAvatar = document.getElementById('userAvatar');
        const userDropdown = document.getElementById('userDropdown');
        const userName = document.getElementById('userName');
        const userEmail = document.getElementById('userEmail');
        const completedExercises = document.getElementById('completedExercises');
        const correctAnswers = document.getElementById('correctAnswers');
        const loginBtn = document.getElementById('loginBtn');
        const loginModal = document.getElementById('loginModal');
        const closeModal = document.querySelector('.close-modal');
        const googleLoginBtn = document.getElementById('googleLoginBtn');
        const facebookLoginBtn = document.getElementById('facebookLoginBtn');
        const startBtn = document.getElementById('startBtn');

        userAvatar.addEventListener('click', function(e) {
            e.stopPropagation();
            userDropdown.classList.toggle('active');
        });

        document.addEventListener('click', function() {
            userDropdown.classList.remove('active');
        });

        function openLoginModal() {
            loginModal.style.display = 'flex';
        }

        loginBtn.addEventListener('click', openLoginModal);
        startBtn.addEventListener('click', function(e) {
            e.preventDefault();
            openLoginModal();
        });

        closeModal.addEventListener('click', function() {
            loginModal.style.display = 'none';
        });

        window.addEventListener('click', function(e) {
            if (e.target === loginModal) {
                loginModal.style.display = 'none';
            }
        });

        googleLoginBtn.addEventListener('click', function() {
            google.accounts.id.initialize({
                client_id: 'YOUR_GOOGLE_CLIENT_ID',
                callback: handleGoogleSignIn
            });
            google.accounts.id.prompt();
        });

        function handleGoogleSignIn(response) {
            const userObject = JSON.parse(atob(response.credential.split('.')[1]));
            userData.loggedIn = true;
            userData.name = userObject.name;
            userData.email = userObject.email;

            userName.textContent = userData.name;
            userEmail.textContent = userData.email;
            loginBtn.textContent = "Cerrar Sesión";
            loginModal.style.display = 'none';

            loginBtn.removeEventListener('click', openLoginModal);
            loginBtn.addEventListener('click', logout);
        }

        facebookLoginBtn.addEventListener('click', function() {
            FB.login(function(response) {
                if (response.authResponse) {
                    FB.api('/me', { fields: 'name,email' }, function(user) {
                        userData.loggedIn = true;
                        userData.name = user.name;
                        userData.email = user.email;

                        userName.textContent = userData.name;
                        userEmail.textContent = userData.email;
                        loginBtn.textContent = "Cerrar Sesión";
                        loginModal.style.display = 'none';

                        loginBtn.removeEventListener('click', openLoginModal);
                        loginBtn.addEventListener('click', logout);
                    });
                } else {
                    alert('Inicio de sesión con Facebook cancelado o fallido.');
                }
            }, { scope: 'public_profile,email' });
        });

        function logout() {
            userData.loggedIn = false;
            userData.name = "Invitado";
            userData.email = "";
            
            userName.textContent = userData.name;
            userEmail.textContent = "No has iniciado sesión";
            loginBtn.textContent = "Iniciar Sesión";
            
            loginBtn.removeEventListener('click', logout);
            loginBtn.addEventListener('click', openLoginModal);

            google.accounts.id.disableAutoSelect();

            FB.getLoginStatus(function(response) {
                if (response.status === 'connected') {
                    FB.logout();
                }
            });
        }

        function updateUserStats() {
            completedExercises.textContent = userData.completedExercises;
            const accuracy = userData.totalAnswers > 0 ? 
                Math.round((userData.correctAnswers / userData.totalAnswers) * 100) : 0;
            correctAnswers.textContent = `${accuracy}%`;
        }
    </script>
</body>
</html>
