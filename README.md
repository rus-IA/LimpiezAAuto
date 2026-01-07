# LimpiezAAuto
<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>AutoLimpio - Limpieza de Interiores de Autos</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Arial', sans-serif;
            line-height: 1.6;
            color: #333;
        }

        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 20px;
        }

        /* Header */
        header {
            background: linear-gradient(135deg, #2c3e50, #3498db);
            color: white;
            padding: 1rem 0;
            position: fixed;
            width: 100%;
            top: 0;
            z-index: 1000;
            box-shadow: 0 2px 10px rgba(0,0,0,0.1);
        }

        nav {
            display: flex;
            justify-content: space-between;
            align-items: center;
        }

        .logo {
            font-size: 1.8rem;
            font-weight: bold;
        }

        .nav-links {
            display: flex;
            list-style: none;
            gap: 2rem;
        }

        .nav-links a {
            color: white;
            text-decoration: none;
            transition: color 0.3s;
        }

        .nav-links a:hover {
            color: #f39c12;
        }

        /* Hero Section */
        .hero {
            background: linear-gradient(rgba(44, 62, 80, 0.8), rgba(52, 152, 219, 0.8)), url('data:image/svg+xml,<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 1200 600"><rect fill="%23f8f9fa" width="1200" height="600"/><path fill="%23dee2e6" d="M0 400h1200v200H0z"/></svg>');
            background-size: cover;
            background-position: center;
            height: 100vh;
            display: flex;
            align-items: center;
            color: white;
            text-align: center;
        }

        .hero-content h1 {
            font-size: 3.5rem;
            margin-bottom: 1rem;
            animation: fadeInUp 1s;
        }

        .hero-content p {
            font-size: 1.2rem;
            margin-bottom: 2rem;
            animation: fadeInUp 1s 0.3s both;
        }

        .btn {
            display: inline-block;
            padding: 12px 30px;
            background: #f39c12;
            color: white;
            text-decoration: none;
            border-radius: 30px;
            font-weight: bold;
            transition: all 0.3s;
            animation: fadeInUp 1s 0.6s both;
        }

        .btn:hover {
            background: #e67e22;
            transform: translateY(-2px);
        }

        /* Services Section */
        .services {
            padding: 80px 0;
            background: #f8f9fa;
        }

        .section-title {
            text-align: center;
            font-size: 2.5rem;
            margin-bottom: 3rem;
            color: #2c3e50;
        }

        .services-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 2rem;
            margin-top: 3rem;
        }

        .service-card {
            background: white;
            padding: 2rem;
            border-radius: 10px;
            box-shadow: 0 5px 15px rgba(0,0,0,0.1);
            text-align: center;
            transition: transform 0.3s;
        }

        .service-card:hover {
            transform: translateY(-5px);
        }

        .service-icon {
            font-size: 3rem;
            color: #3498db;
            margin-bottom: 1rem;
        }

        .service-card h3 {
            font-size: 1.5rem;
            margin-bottom: 1rem;
            color: #2c3e50;
        }

        .price {
            font-size: 1.8rem;
            font-weight: bold;
            color: #f39c12;
            margin-top: 1rem;
        }

        /* About Section */
        .about {
            padding: 80px 0;
            background: white;
        }

        .about-content {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 3rem;
            align-items: center;
        }

        .about-text h2 {
            font-size: 2.5rem;
            margin-bottom: 2rem;
            color: #2c3e50;
        }

        .about-text p {
            font-size: 1.1rem;
            margin-bottom: 1.5rem;
            color: #666;
        }

        .features {
            list-style: none;
            margin-top: 2rem;
        }

        .features li {
            padding: 0.5rem 0;
            display: flex;
            align-items: center;
        }

        .features li::before {
            content: "✓";
            color: #27ae60;
            font-weight: bold;
            margin-right: 10px;
        }

        /* Contact Section */
        .contact {
            padding: 80px 0;
            background: linear-gradient(135deg, #2c3e50, #3498db);
            color: white;
        }

        .contact-content {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 3rem;
        }

        .contact-form {
            background: rgba(255,255,255,0.1);
            padding: 2rem;
            border-radius: 10px;
        }

        .form-group {
            margin-bottom: 1.5rem;
        }

        .form-group label {
            display: block;
            margin-bottom: 0.5rem;
            font-weight: bold;
        }

        .form-group input,
        .form-group textarea {
            width: 100%;
            padding: 10px;
            border: none;
            border-radius: 5px;
            font-size: 1rem;
        }

        .contact-info h3 {
            font-size: 1.5rem;
            margin-bottom: 1rem;
        }

        .contact-item {
            display: flex;
            align-items: center;
            margin-bottom: 1rem;
        }

        .contact-item i {
            font-size: 1.2rem;
            margin-right: 10px;
            color: #f39c12;
        }

        /* Footer */
        footer {
            background: #2c3e50;
            color: white;
            text-align: center;
            padding: 2rem 0;
        }

        /* Animations */
        @keyframes fadeInUp {
            from {
                opacity: 0;
                transform: translateY(30px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }

        /* Responsive */
        @media (max-width: 768px) {
            .nav-links {
                display: none;
            }
            
            .hero-content h1 {
                font-size: 2.5rem;
            }
            
            .about-content {
                grid-template-columns: 1fr;
            }
            
            .contact-content {
                grid-template-columns: 1fr;
            }
        }
    </style>
</head>
<body>
    <!-- Header -->
    <header>
        <nav class="container">
            <div class="logo">🚗 AutoLimpio</div>
            <ul class="nav-links">
                <li><a href="#inicio">Inicio</a></li>
                <li><a href="#servicios">Servicios</a></li>
                <li><a href="#nosotros">Nosotros</a></li>
                <li><a href="#contacto">Contacto</a></li>
            </ul>
        </nav>
    </header>

    <!-- Hero Section -->
    <section id="inicio" class="hero">
        <div class="container">
            <div class="hero-content">
                <h1>Limpieza Profesional de Interiores</h1>
                <p>Devolvemos la vida a tu auto con nuestro servicio especializado en limpieza de interiores</p>
                <a href="#contacto" class="btn">Solicitar Servicio</a>
            </div>
        </div>
    </section>

    <!-- Services Section -->
    <section id="servicios" class="services">
        <div class="container">
            <h2 class="section-title">Nuestros Servicios</h2>
            <div class="services-grid">
                <div class="service-card">
                    <div class="service-icon">🧽</div>
                    <h3>Limpieza Básica</h3>
                    <p>Aspirado completo, limpieza de tapicería, tablero y cristales interiores.</p>
                    <div class="price">$25.000</div>
                </div>
                <div class="service-card">
                    <div class="service-icon">✨</div>
                    <h3>Limpieza Premium</h3>
                    <p>Servicio completo + encerado del tablero, acondicionamiento de cuero y aromatización.</p>
                    <div class="price">$45.000</div>
                </div>
                <div class="service-card">
                    <div class="service-icon">💎</div>
                    <h3>Detailing Completo</h3>
                    <p>Máximo nivel de detalle, limpieza profunda, protección UV y desinfección completa.</p>
                    <div class="price">$75.000</div>
                </div>
            </div>
        </div>
    </section>

    <!-- About Section -->
    <section id="nosotros" class="about">
        <div class="container">
            <div class="about-content">
                <div class="about-text">
                    <h2>¿Por qué elegir AutoLimpio?</h2>
                    <p>Con más de 5 años de experiencia en el cuidado automotriz, nos especializamos en devolver el brillo y la limpieza a los interiores de tu vehículo.</p>
                    <p>Utilizamos productos profesionales de alta calidad y técnicas especializadas para garantizar los mejores resultados.</p>
                    <ul class="features">
                        <li>Productos ecológicos y seguros</li>
                        <li>Técnicos certificados</li>
                        <li>Servicio a domicilio</li>
                        <li>Garantía de satisfacción</li>
                        <li>Precios competitivos</li>
                    </ul>
                </div>
                <div class="about-image">
                    <div style="background: #f8f9fa; height: 400px; border-radius: 10px; display: flex; align-items: center; justify-content: center; font-size: 4rem; color: #dee2e6;">
                        🚗💨
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Contact Section -->
    <section id="contacto" class="contact">
        <div class="container">
            <h2 class="section-title">Contáctanos</h2>
            <div class="contact-content">
                <div class="contact-form">
                    <h3>Solicita tu cita</h3>
                    <form>
                        <div class="form-group">
                            <label for="nombre">Nombre:</label>
                            <input type="text" id="nombre" name="nombre" required>
                        </div>
                        <div class="form-group">
                            <label for="telefono">Teléfono:</label>
                            <input type="tel" id="telefono" name="telefono" required>
                        </div>
                        <div class="form-group">
                            <label for="servicio">Servicio:</label>
                            <select id="servicio" name="servicio" style="width: 100%; padding: 10px; border: none; border-radius: 5px;">
                                <option>Limpieza Básica</option>
                                <option>Limpieza Premium</option>
                                <option>Detailing Completo</option>
                            </select>
                        </div>
                        <div class="form-group">
                            <label for="mensaje">Mensaje:</label>
                            <textarea id="mensaje" name="mensaje" rows="4"></textarea>
                        </div>
                        <button type="submit" class="btn">Enviar Solicitud</button>
                    </form>
                </div>
                <div class="contact-info">
                    <h3>Información de Contacto</h3>
                    <div class="contact-item">
                        <span>📱</span>
                        <span>+57 300 123 4567</span>
                    </div>
                    <div class="contact-item">
                        <span>📧</span>
                        <span>info@autolimpio.com</span>
                    </div>
                    <div class="contact-item">
                        <span>📍</span>
                        <span>Servicio a domicilio en toda la ciudad</span>
                    </div>
                    <div class="contact-item">
                        <span>🕒</span>
                        <span>Lun - Sáb: 8:00 AM - 6:00 PM</span>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Footer -->
    <footer>
        <div class="container">
            <p>&copy; 2024 AutoLimpio. Todos los derechos reservados.</p>
        </div>
    </footer>

    <script>
        // Smooth scrolling para los enlaces de navegación
        document.querySelectorAll('a[href^="#"]').forEach(anchor => {
            anchor.addEventListener('click', function (e) {
                e.preventDefault();
                document.querySelector(this.getAttribute('href')).scrollIntoView({
                    behavior: 'smooth'
                });
            });
        });

        // Formulario de contacto
        document.querySelector('form').addEventListener('submit', function(e) {
            e.preventDefault();
            alert('¡Gracias por tu solicitud! Te contactaremos pronto.');
        });

        // Efecto parallax en el hero
        window.addEventListener('scroll', function() {
            const scrolled = window.pageYOffset;
            const hero = document.querySelector('.hero');
            hero.style.transform = `translateY(${scrolled * 0.5}px)`;
        });
    </script>
</body>
</html>
