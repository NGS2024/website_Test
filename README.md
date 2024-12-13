# website_Test

<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>News Website</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/5.15.4/css/all.min.css">
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: Arial, sans-serif;
            line-height: 1.6;
        }

        header {
            background-color: #333;
            color: white;
            padding: 1rem;
            text-align: center;
        }

        nav {
            background-color: #444;
            padding: 1rem;
        }

        nav ul {
            list-style: none;
            display: flex;
            justify-content: center;
            gap: 2rem;
        }

        nav a {
            color: white;
            text-decoration: none;
        }

        /* Carousel Styles */
        .carousel-container {
            position: relative;
            max-width: 1200px;
            margin: 2rem auto;
            overflow: hidden;
        }

        .carousel {
            display: flex;
            transition: transform 0.5s ease-in-out;
        }

        .carousel-item {
            min-width: 100%;
            position: relative;
        }

        .carousel-item img {
            width: 100%;
            height: 400px;
            object-fit: cover;
        }

        .carousel-caption {
            position: absolute;
            bottom: 0;
            left: 0;
            right: 0;
            background: rgba(0, 0, 0, 0.7);
            color: white;
            padding: 1rem;
        }

        .carousel-buttons {
            position: absolute;
            top: 50%;
            width: 100%;
            display: flex;
            justify-content: space-between;
            transform: translateY(-50%);
        }

        .carousel-button {
            background: rgba(0, 0, 0, 0.5);
            color: white;
            border: none;
            padding: 1rem;
            cursor: pointer;
        }

        /* News Articles Grid */
        .news-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 2rem;
            padding: 2rem;
            max-width: 1200px;
            margin: 0 auto;
        }

        .article-card {
            border: 1px solid #ddd;
            border-radius: 8px;
            overflow: hidden;
        }

        .article-card img {
            width: 100%;
            height: 200px;
            object-fit: cover;
        }

        .article-content {
            padding: 1rem;
        }

        footer {
            background-color: #333;
            color: white;
            text-align: center;
            padding: 1rem;
            margin-top: 2rem;
        }
    </style>
</head>
<body>
    <header>
        <h1>News Website</h1>
    </header>

    <nav>
        <ul>
            <li><a href="#">Home</a></li>
            <li><a href="#">Politics</a></li>
            <li><a href="#">Technology</a></li>
            <li><a href="#">Sports</a></li>
            <li><a href="#">Entertainment</a></li>
        </ul>
    </nav>

    <div class="carousel-container">
        <div class="carousel">
            <div class="carousel-item">
                <img src="https://via.placeholder.com/1200x400" alt="News 1">
                <div class="carousel-caption">
                    <h2>Breaking News 1</h2>
                    <p>Important story of the day...</p>
                </div>
            </div>
            <div class="carousel-item">
                <img src="https://via.placeholder.com/1200x400" alt="News 2">
                <div class="carousel-caption">
                    <h2>Breaking News 2</h2>
                    <p>Another important story...</p>
                </div>
            </div>
            <div class="carousel-item">
                <img src="https://via.placeholder.com/1200x400" alt="News 3">
                <div class="carousel-caption">
                    <h2>Breaking News 3</h2>
                    <p>Yet another important story...</p>
                </div>
            </div>
        </div>
        <div class="carousel-buttons">
            <button class="carousel-button" onclick="moveCarousel(-1)">
                <i class="fas fa-chevron-left"></i>
            </button>
            <button class="carousel-button" onclick="moveCarousel(1)">
                <i class="fas fa-chevron-right"></i>
            </button>
        </div>
    </div>

    <main class="news-grid">
        <article class="article-card">
            <img src="https://via.placeholder.com/300x200" alt="Article 1">
            <div class="article-content">
                <h3>Article Title 1</h3>
                <p>Article preview text goes here...</p>
                <a href="#">Read More</a>
            </div>
        </article>
        <article class="article-card">
            <img src="https://via.placeholder.com/300x200" alt="Article 2">
            <div class="article-content">
                <h3>Article Title 2</h3>
                <p>Article preview text goes here...</p>
                <a href="#">Read More</a>
            </div>
        </article>
        <article class="article-card">
            <img src="https://via.placeholder.com/300x200" alt="Article 3">
            <div class="article-content">
                <h3>Article Title 3</h3>
                <p>Article preview text goes here...</p>
                <a href="#">Read More</a>
            </div>
        </article>
    </main>

    <footer>
        <p>&copy; 2023 News Website. All rights reserved.</p>
    </footer>

    <script>
        let currentSlide = 0;
        const carousel = document.querySelector('.carousel');
        const items = document.querySelectorAll('.carousel-item');
        const totalSlides = items.length;

        function moveCarousel(direction) {
            currentSlide = (currentSlide + direction + totalSlides) % totalSlides;
            carousel.style.transform = `translateX(-${currentSlide * 100}%)`;
        }

        // Auto-rotate carousel
        setInterval(() => moveCarousel(1), 5000);
    </script>
</body>
</html>
