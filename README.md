# Practicaejercicios
<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>PracticaEjercicios.com - Plataforma de ejercicios educativos</title>
    <style>
        :root {
            --primary-color: #4a6fa5;
            --secondary-color: #166088;
            --accent-color: #4cb5f5;
            --light-color: #f8f9fa;
            --dark-color: #343a40;
            --success-color: #28a745;
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
        
        /* Header Styles */
        header {
            background: linear-gradient(135deg, var(--primary-color), var(--secondary-color));
            color: white;
            padding: 1rem 0;
            box-shadow: 0 2px 10px rgba(0, 0, 0, 0.1);
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
        
        /* Hero Section */
        .hero {
            background: url('data:image/svg+xml;utf8,<svg xmlns="http://www.w3.org/2000/svg" width="100" height="100" viewBox="0 0 100 100"><rect fill="%234a6fa5" width="100" height="100"/><path fill="%23166088" d="M0 0L100 100" stroke-width="0"/></svg>');
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
        
        /* Categories Section */
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
        
        .category-icon {
            background: linear-gradient(135deg, var(--primary-color), var(--secondary-color));
            height: 120px;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 2.5rem;
            color: white;
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
        
        /* Features Section */
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
        
        /* Testimonials */
        .testimonials {
            padding: 4rem 0;
            background-color: #f8f9fa;
        }
        
        .testimonial-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(300px, 1fr));
            gap: 2rem;
        }
        
        .testimonial-card {
            background-color: white;
            padding: 2rem;
            border-radius: 10px;
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.05);
        }
        
        .testimonial-text {
            font-style: italic;
            margin-bottom: 1.5rem;
            color: #495057;
        }
        
        .testimonial-author {
            display: flex;
            align-items: center;
        }
        
        .author-avatar {
            width: 50px;
            height: 50px;
            border-radius: 50%;
            background-color: var(--primary-color);
            display: flex;
            align-items: center;
            justify-content: center;
            color: white;
            font-weight: bold;
            margin-right: 1rem;
        }
        
        .author-info h4 {
            color: var(--dark-color);
        }
        
        .author-info p {
            color: #6c757d;
            font-size: 0.9rem;
        }
        
        /* Footer */
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
        
        /* Responsive Design */
        @media (max-width: 768px) {
            .header-content {
                flex-direction: column;
                text-align: center;
            }
            
            nav ul {
                margin-top: 1rem;
                justify-content: center;
            }
            
            nav ul li {
                margin: 0 0.5rem;
            }
            
            .hero h1 {
                font-size: 2rem;
            }
            
            .hero p {
                font-size: 1rem;
            }
        }
    </style>
</head>
<body>
    <!-- Header -->
    <header>
        <div class="container header-content">
            <div class="logo">Practica<span>Ejercicios</span></div>
            <nav>
                <ul>
                    <li><a href="#">Inicio</a></li>
                    <li><a href="#">Ejercicios</a></li>
                    <li><a href="#">Recursos</a></li>
                    <li><a href="#">Blog</a></li>
                    <li><a href="#">Contacto</a></li>
                </ul>
            </nav>
        </div>
    </header>

    <!-- Hero Section -->
    <section class="hero">
        <div class="container">
            <h1>Mejora tus habilidades con ejercicios prácticos</h1>
            <p>Miles de ejercicios gratuitos para estudiantes de todas las edades y niveles educativos. Matemáticas, lenguaje, ciencias y mucho más.</p>
            <a href="#" class="btn">Comenzar ahora</a>
        </div>
    </section>

    <!-- Categories Section -->
    <section class="categories">
        <div class="container">
            <div class="section-title">
                <h2>Materias Disponibles</h2>
                <p>Explora nuestros ejercicios por categoría</p>
            </div>
            <div class="category-grid">
                <div class="category-card">
                    <div class="category-icon">∑</div>
                    <div class="category-content">
                        <h3>Matemáticas</h3>
                        <p>Álgebra, geometría, cálculo y más. Ejercicios para todos los niveles.</p>
                        <a href="#" class="btn">Practicar</a>
                    </div>
                </div>
                <div class="category-card">
                    <div class="category-icon">📚</div>
                    <div class="category-content">
                        <h3>Lenguaje</h3>
                        <p>Gramática, ortografía, comprensión lectora y ejercicios de escritura.</p>
                        <a href="#" class="btn">Practicar</a>
                    </div>
                </div>
                <div class="category-card">
                    <div class="category-icon">🔬</div>
                    <div class="category-content">
                        <h3>Ciencias</h3>
                        <p>Biología, física, química y ciencias de la tierra. Aprende experimentando.</p>
                        <a href="#" class="btn">Practicar</a>
                    </div>
                </div>
                <div class="category-card">
                    <div class="category-icon">🌎</div>
                    <div class="category-content">
                        <h3>Sociales</h3>
                        <p>Historia, geografía, economía y cultura general. Explora el mundo.</p>
                        <a href="#" class="btn">Practicar</a>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Features Section -->
    <section class="features">
        <div class="container">
            <div class="section-title">
                <h2>¿Por qué elegirnos?</h2>
                <p>Ventajas de nuestra plataforma educativa</p>
            </div>
            <div class="features-grid">
                <div class="feature-card">
                    <div class="feature-icon">✓</div>
                    <h3>Contenido de Calidad</h3>
                    <p>Ejercicios creados por educadores profesionales y revisados pedagógicamente.</p>
                </div>
                <div class="feature-card">
                    <div class="feature-icon">🔄</div>
                    <h3>Retroalimentación Inmediata</h3>
                    <p>Corrección automática con explicaciones detalladas para cada ejercicio.</p>
                </div>
                <div class="feature-card">
                    <div class="feature-icon">📊</div>
                    <h3>Seguimiento de Progreso</h3>
                    <p>Monitoriza tu evolución con estadísticas detalladas y recomendaciones personalizadas.</p>
                </div>
            </div>
        </div>
    </section>

    <!-- Testimonials Section -->
    <section class="testimonials">
        <div class="container">
            <div class="section-title">
                <h2>Opiniones de usuarios</h2>
                <p>Lo que dicen nuestros estudiantes</p>
            </div>
            <div class="testimonial-grid">
                <div class="testimonial-card">
                    <div class="testimonial-text">
                        "Esta plataforma me ayudó a mejorar mis calificaciones en matemáticas. Los ejercicios son muy prácticos y las explicaciones son claras."
                    </div>
                    <div class="testimonial-author">
                        <div class="author-avatar">M</div>
                        <div class="author-info">
                            <h4>María López</h4>
                            <p>Estudiante de Bachillerato</p>
                        </div>
                    </div>
                </div>
                <div class="testimonial-card">
                    <div class="testimonial-text">
                        "Como docente, recomiendo esta web a mis alumnos. El material es de calidad y se adapta a diferentes niveles de aprendizaje."
                    </div>
                    <div class="testimonial-author">
                        <div class="author-avatar">C</div>
                        <div class="author-info">
                            <h4>Carlos Rodríguez</h4>
                            <p>Profesor de Secundaria</p>
                        </div>
                    </div>
                </div>
                <div class="testimonial-card">
                    <div class="testimonial-text">
                        "Gracias a los ejercicios de práctica, mi hijo ha ganado confianza en la escuela. La interfaz es amigable y fácil de usar."
                    </div>
                    <div class="testimonial-author">
                        <div class="author-avatar">A</div>
                        <div class="author-info">
                            <h4>Ana Martínez</h4>
                            <p>Madre de estudiante</p>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Footer -->
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
                        <li><a href="#">Inicio</a></li>
                        <li><a href="#">Ejercicios</a></li>
                        <li><a href="#">Recursos</a></li>
                        <li><a href="#">Blog</a></li>
                        <li><a href="#">Contacto</a></li>
                    </ul>
                </div>
                <div class="footer-column">
                    <h3>Materias</h3>
                    <ul>
                        <li><a href="#">Matemáticas</a></li>
                        <li><a href="#">Lenguaje</a></li>
                        <li><a href="#">Ciencias</a></li>
                        <li><a href="#">Sociales</a></li>
                        <li><a href="#">Inglés</a></li>
                    </ul>
                </div>
                <div class="footer-column">
                    <h3>Contacto</h3>
                    <ul>
                        <li>Email: info@practicaejercicios.com</li>
                        <li>Teléfono: +34 912 345 678</li>
                    </ul>
                </div>
            </div>
            <div class="copyright">
                <p>&copy; 2023 PracticaEjercicios.com - Todos los derechos reservados</p>
            </div>
        </div>
    </footer>

    <script>
        // Simple JavaScript for interactive elements
        document.addEventListener('DOMContentLoaded', function() {
            const buttons = document.querySelectorAll('.btn');
            
            buttons.forEach(button => {
                button.addEventListener('click', function(e) {
                    e.preventDefault();
                    alert('¡Funcionalidad de ejemplo! En una implementación real, esto llevaría a los ejercicios.');
                });
            });
        });
    </script>
</body>
</html>
