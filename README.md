<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Beyond | Premium Portfolios</title>
    <link href="https://fonts.googleapis.com/css2?family=Playfair+Display:wght@500;700&family=Inter:wght@300;400&display=swap" rel="stylesheet">
    <style>
        :root {
            --accent: #b59b6d; /* Gold accent like premium photography sites */
            --bg: #ffffff;
            --text: #1a1a1a;
        }

        * { margin: 0; padding: 0; box-sizing: border-box; }
        body { font-family: 'Inter', sans-serif; background: var(--bg); color: var(--text); line-height: 1.6; }

        /* Header */
        header {
            padding: 30px 5%;
            display: flex;
            justify-content: space-between;
            align-items: center;
            position: sticky;
            top: 0;
            background: rgba(255,255,255,0.95);
            backdrop-filter: blur(10px);
            z-index: 100;
        }
        .brand { font-family: 'Playfair Display', serif; font-size: 1.8rem; letter-spacing: 5px; text-transform: uppercase; }
        
        /* Navigation */
        nav a { text-decoration: none; color: var(--text); margin-left: 30px; font-size: 0.8rem; letter-spacing: 2px; text-transform: uppercase; transition: 0.3s; }
        nav a:hover { color: var(--accent); }

        /* Filter Menu */
        .filters { text-align: center; padding: 40px 0; }
        .filter-btn {
            background: none; border: none; padding: 10px 20px; cursor: pointer;
            font-size: 0.75rem; text-transform: uppercase; letter-spacing: 2px;
            color: #999; transition: 0.3s;
        }
        .filter-btn.active { color: var(--text); font-weight: 700; border-bottom: 2px solid var(--accent); }

        /* Masonry Grid */
        .portfolio-container { padding: 0 5% 100px; }
        .masonry {
            column-count: 3;
            column-gap: 20px;
        }
        .item {
            break-inside: avoid;
            margin-bottom: 20px;
            position: relative;
            overflow: hidden;
            background: #f9f9f9;
        }
        .item img {
            width: 100%;
            display: block;
            transition: transform 0.6s cubic-bezier(0.25, 1, 0.5, 1);
        }
        .item:hover img { transform: scale(1.08); }

        /* Hover Overlay */
        .overlay {
            position: absolute; inset: 0;
            background: rgba(0,0,0,0.5);
            display: flex; flex-direction: column; justify-content: center; align-items: center;
            opacity: 0; transition: 0.4s; color: white;
        }
        .item:hover .overlay { opacity: 1; }
        .overlay h3 { font-family: 'Playfair Display', serif; font-size: 1.5rem; margin-bottom: 10px; }
        .overlay p { font-size: 0.7rem; letter-spacing: 2px; text-transform: uppercase; }

        /* Responsive */
        @media (max-width: 1000px) { .masonry { column-count: 2; } }
        @media (max-width: 600px) { .masonry { column-count: 1; } }
    </style>
</head>
<body>

    <header>
        <div class="brand">Beyond</div>
        <nav>
            <a href="#">Portfolio</a>
            <a href="#">About</a>
            <a href="#">Contact</a>
        </nav>
    </header>

    <div class="filters">
        <button class="filter-btn active" onclick="filterSelection('all')">View All</button>
        <button class="filter-btn" onclick="filterSelection('wedding')">Weddings</button>
        <button class="filter-btn" onclick="filterSelection('films')">Films</button>
        <button class="filter-btn" onclick="filterSelection('portrait')">Portraits</button>
    </div>

    <main class="portfolio-container">
        <div class="masonry">
            <div class="item wedding">
                <img src="https://images.unsplash.com/photo-1519741497674-611481863552?q=80&w=1000" alt="Wedding">
                <div class="overlay">
                    <h3>The Mumbai Gala</h3>
                    <p>Wedding Photography</p>
                </div>
            </div>
            <div class="item films">
                <img src="https://images.unsplash.com/photo-1511795409834-ef04bbd61622?q=80&w=1000" alt="Film">
                <div class="overlay">
                    <h3>Eternal Motion</h3>
                    <p>Cinematic Film</p>
                </div>
            </div>
            <div class="item portrait">
                <img src="https://images.unsplash.com/photo-1520854221256-17451cc331bf?q=80&w=1000&h=1500" alt="Portrait">
                <div class="overlay">
                    <h3>Soulful Gaze</h3>
                    <p>Portraiture</p>
                </div>
            </div>
        </div>
    </main>

    <script>
        function filterSelection(c) {
            var x, i;
            x = document.getElementsByClassName("item");
            if (c == "all") c = "";
            for (i = 0; i < x.length; i++) {
                x[i].style.display = "none";
                if (x[i].className.indexOf(c) > -1) {
                    x[i].style.display = "block";
                }
            }
        }
    </script>
</body>
</html># beyond..
