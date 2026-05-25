<style>
    :root {
        --bg-main: #0b0c10;
        --bg-card: #141923;
        --gold: #d4af37;
        --gold-glow: rgba(212, 175, 55, 0.35);
        --red: #a30000;
        --red-glow: rgba(163, 0, 0, 0.5);
        --text-muted: #a0aec0;
        --text-white: #ffffff;
    }

    * {
        margin: 0;
        padding: 0;
        box-sizing: border-box;
        font-family: 'Inter', sans-serif;
        scroll-behavior: smooth;
    }

    body {
        background-color: var(--bg-main);
        color: var(--text-white);
        line-height: 1.6;
        overflow-x: hidden;
    }

    /* Navigation Bar */
    header {
        position: fixed;
        top: 0;
        width: 100%;
        background: rgba(11, 12, 16, 0.95);
        border-bottom: 1px solid rgba(212, 175, 55, 0.15);
        z-index: 1000;
        backdrop-filter: blur(10px);
    }

    .nav-container {
        max-width: 1200px;
        margin: 0 auto;
        display: flex;
        justify-content: space-between;
        align-items: center;
        padding: 18px 20px;
    }

    .logo {
        font-size: 1.4rem;
        font-weight: 700;
        color: var(--gold);
        text-shadow: 0 0 10px var(--gold-glow);
        text-decoration: none;
        letter-spacing: 1px;
    }

    nav a {
        color: var(--text-white);
        text-decoration: none;
        margin-left: 22px;
        font-size: 0.9rem;
        font-weight: 600;
        transition: 0.3s;
    }

    nav a:hover {
        color: var(--gold);
        text-shadow: 0 0 8px var(--gold-glow);
    }

    /* Hero / Welcome Section */
    .hero {
        height: 75vh;
        display: flex;
        flex-direction: column;
        justify-content: center;
        align-items: center;
        text-align: center;
        padding: 20px;
        background: radial-gradient(circle at center, rgba(163, 0, 0, 0.15) 0%, rgba(11, 12, 16, 1) 75%);
    }

    .hero h1 {
        font-size: 3.5rem;
        margin-bottom: 15px;
        letter-spacing: 1px;
        font-weight: 700;
    }

    .hero h1 span {
        color: var(--gold);
        text-shadow: 0 0 15px var(--gold-glow);
    }

    .hero p {
        font-size: 1.15rem;
        max-width: 650px;
        margin-bottom: 35px;
        color: var(--text-muted);
    }

    .btn-live {
        background: linear-gradient(45deg, var(--red), #bd1b1b);
        color: white;
        padding: 14px 35px;
        text-decoration: none;
        border-radius: 30px;
        font-weight: 600;
        box-shadow: 0 0 15px var(--red-glow);
        transition: 0.3s;
    }

    .btn-live:hover {
        transform: scale(1.03);
        box-shadow: 0 0 25px var(--red-glow);
    }

    /* Moving Photo Slider (Carousel) CSS */
    .slider-section {
        padding: 20px 0 60px 0;
        max-width: 1000px;
        margin: 0 auto;
    }

    .slider-container {
        position: relative;
        width: 90%;
        margin: 0 auto;
        aspect-ratio: 16/9;
        overflow: hidden;
        border-radius: 14px;
        border: 2px solid var(--red);
        box-shadow: 0 0 20px var(--red-glow);
    }

    .slides {
        display: flex;
        width: 100%;
        height: 100%;
        transition: transform 0.5s ease-in-out;
    }

    .slide {
        min-width: 100%;
        height: 100%;
        position: relative;
        background: #111;
    }

    .slide img {
        width: 100%;
        height: 100%;
        object-fit: cover;
    }

    .slide-caption {
        position: absolute;
        bottom: 0;
        background: linear-gradient(transparent, rgba(0,0,0,0.85));
        width: 100%;
        padding: 20px;
        text-align: center;
        color: var(--gold);
        font-weight: 600;
        font-size: 1.1rem;
        text-shadow: 0 2px 4px rgba(0,0,0,0.8);
    }

    /* Slider Controls */
    .slider-btn {
        position: absolute;
        top: 50%;
        transform: translateY(-50%);
        background: rgba(20, 25, 35, 0.8);
        border: 1px solid var(--gold);
        color: var(--gold);
        padding: 12px 16px;
        cursor: pointer;
        border-radius: 50%;
        font-size: 1.2rem;
        transition: 0.3s;
        z-index: 10;
    }

    .slider-btn:hover {
        background: var(--red);
        color: white;
        box-shadow: 0 0 10px var(--red-glow);
    }

    .prev-btn { left: 15px; }
    .next-btn { right: 15px; }

    /* Section Global Settings */
    section {
        padding: max(80px, 6%) 20px;
        max-width: 1200px;
        margin: 0 auto;
    }

    .section-title {
        text-align: center;
        font-size: 2.2rem;
        margin-bottom: 50px;
        color: var(--gold);
        text-shadow: 0 0 10px var(--gold-glow);
        letter-spacing: 1px;
    }

    /* Custom Grids */
    .grid-cards {
        display: grid;
        grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
        gap: 25px;
    }

    /* Card Designs */
    .card {
        background-color: var(--bg-card);
        border: 1px solid rgba(212, 175, 55, 0.08);
        border-radius: 12px;
        padding: 35px 25px;
        text-align: center;
        transition: 0.3s ease;
    }

    .card:hover {
        transform: translateY(-5px);
        border-color: var(--red);
        box-shadow: 0 6px 22px var(--red-glow);
    }

    .card i {
        font-size: 2.4rem;
        color: var(--gold);
        margin-bottom: 22px;
        text-shadow: 0 0 10px var(--gold-glow);
    }

    .card h3 {
        margin-bottom: 12px;
        font-size: 1.35rem;
        letter-spacing: 0.5px;
    }

    .card p {
        color: var(--text-muted);
        font-size: 0.95rem;
    }

    /* Locations Map Embed Container */
    .map-box {
        width: 100%;
        height: 250px;
        background: #08090c;
        margin-top: 15px;
        border-radius: 8px;
        border: 1px solid rgba(212, 175, 55, 0.1);
        display: flex;
        align-items: center;
        justify-content: center;
        color: #555;
    }

    /* Media Dynamic Screen Placeholder */
    .media-container {
        max-width: 850px;
        margin: 0 auto;
        background: #050508;
        aspect-ratio: 16/9;
        border-radius: 14px;
        border: 1px solid rgba(212, 175, 55, 0.15);
        display: flex;
        justify-content: center;
        align-items: center;
        transition: 0.3s;
    }

    .media-container:hover {
        border-color: var(--red);
        box-shadow: 0 0 25px var(--red-glow);
    }

    /* Input Form Elements */
    .form-box {
        max-width: 650px;
        margin: 0 auto;
        background: var(--bg-card);
        padding: 45px 35px;
        border-radius: 14px;
        border: 1px solid rgba(212, 175, 55, 0.08);
    }

    .form-element {
        margin-bottom: 22px;
    }

    .form-element label {
        display: block;
        margin-bottom: 9px;
        color: var(--gold);
        font-size: 0.9rem;
        font-weight: 600;
    }

    .form-element input, .form-element textarea {
        width: 100%;
        padding: 13px;
        background: #08090c;
        border: 1px solid rgba(212, 175, 55, 0.15);
        color: white;
        border-radius: 8px;
        outline: none;
        font-size: 0.95rem;
        transition: 0.3s;
    }

    .form-element input:focus, .form-element textarea:focus {
        border-color: var(--red);
        box-shadow: 0 0 12px var(--red-glow);
    }

    .btn-action {
        background: var(--gold);
        color: var(--bg-main);
        border: none;
        width: 100%;
        padding: 15px;
        font-size: 1rem;
        font-weight: 700;
        border-radius: 8px;
        cursor: pointer;
        transition: 0.3s;
        text-transform: uppercase;
        letter-spacing: 0.5px;
    }

    .btn-action:hover {
        background: #ffffff;
        box-shadow: 0 0 18px var(--gold-glow);
    }

    /* Media Gallery Grid Layout */
    .gallery-box {
        display: grid;
        grid-template-columns: repeat(auto-fit, minmax(240px, 1fr));
        gap: 15px;
    }

    .gallery-photo {
        aspect-ratio: 4/3;
        background: #111622;
        border-radius: 10px;
        border: 1px solid rgba(212, 175, 55, 0.08);
        display: flex;
        align-items: center;
        justify-content: center;
        transition: 0.3s;
    }

    .gallery-photo:hover {
        border-color: var(--gold);
        transform: scale(1.02);
    }

    /* Footer Layer */
    footer {
        background: #040507;
        text-align: center;
        padding: 45px 20px;
        border-top: 1px solid rgba(212, 175, 55, 0.1);
        font-size: 0.85rem;
        color: #666;
    }

    /* Simple Responsive Breakpoint Menu Reset */
    @media (max-width: 768px) {
        nav {
            display: none;
        }
        .hero h1 {
            font-size: 2.3rem;
        }
        .form-box {
            padding: 30px 20px;
        }
    }
</style>
