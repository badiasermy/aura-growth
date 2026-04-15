document.addEventListener('DOMContentLoaded', () => {
    
    // --- 1. Animaciones al hacer scroll (Intersection Observer) ---
    const observerOptions = {
        root: null,
        rootMargin: '0px',
        threshold: 0.15
    };

    const observer = new IntersectionObserver((entries, observer) => {
        entries.forEach(entry => {
            if (entry.isIntersecting) {
                entry.target.classList.add('visible');
                // Opcional: dejar de observar una vez que ya apareció
                observer.unobserve(entry.target);
            }
        });
    }, observerOptions);

    // Seleccionamos todos los elementos con la clase fade-in
    const fadeElements = document.querySelectorAll('.fade-in');
    fadeElements.forEach(el => observer.observe(el));

    // --- 2. Sombra en el navbar al hacer scroll ---
    const navbar = document.querySelector('.navbar');
    
    window.addEventListener('scroll', () => {
        if (window.scrollY > 50) {
            navbar.style.boxShadow = '0 4px 20px rgba(0, 0, 0, 0.05)';
        } else {
            navbar.style.boxShadow = 'none';
        }
    });

    // --- 3. Menú móvil (funcionalidad básica) ---
    const menuToggle = document.getElementById('mobile-menu');
    const navLinks = document.querySelector('.nav-links');

    menuToggle.addEventListener('click', () => {
        // En una versión más compleja podrías alternar una clase 'active' 
        // para desplegar un menú de pantalla completa.
        const isHidden = window.getComputedStyle(navLinks).display === 'none';
        if (isHidden) {
            navLinks.style.display = 'flex';
            navLinks.style.flexDirection = 'column';
            navLinks.style.position = 'absolute';
            navLinks.style.top = '100%';
            navLinks.style.left = '0';
            navLinks.style.width = '100%';
            navLinks.style.backgroundColor = 'var(--bg-color)';
            navLinks.style.padding = '20px';
            navLinks.style.boxShadow = '0 10px 10px rgba(0,0,0,0.05)';
        } else {
            navLinks.style.display = 'none';
            // Limpiar estilos en línea si se oculta para no romper el responsive al girar el móvil
            setTimeout(() => navLinks.removeAttribute('style'), 100);
        }
    });
});
