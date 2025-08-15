<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Kristyn Creations</title>
<link href="https://fonts.googleapis.com/css2?family=Playfair+Display:wght@400;700&family=Roboto:wght@400;500&display=swap" rel="stylesheet">
<style>
    * { margin:0; padding:0; box-sizing:border-box; }
    body { font-family: 'Roboto', sans-serif; background:#f9f9f9; color:#333; }
    a { text-decoration:none; color:inherit; }

    header { background:#008080; color:#fff; text-align:center; padding:2rem 1rem; position:sticky; top:0; z-index:100; }
    header h1 { font-family:'Playfair Display', serif; font-size:3rem; margin-bottom:0.5rem; }
    header p { font-size:1.2rem; }
    nav { display:flex; justify-content:center; gap:2rem; background:#006666; padding:1rem 0; position:sticky; top:80px; z-index:100; }
    nav a { color:#fff; font-weight:500; transition:0.3s; }
    nav a:hover { color:#ffd700; }

    .hero { background-image: url('https://images.unsplash.com/photo-1604908177522-d92d25b756fc?auto=format&fit=crop&w=1500&q=80');
            background-size: cover; background-position: center; height:70vh; display:flex; align-items:center; justify-content:center; color:#fff; text-shadow:2px 2px 8px rgba(0,0,0,0.6); }
    .hero h2 { font-size:3rem; background: rgba(0,128,128,0.5); padding:1rem 2rem; border-radius:10px; }

    section { padding:4rem 2rem; max-width:1200px; margin:0 auto; }
    section h2 { text-align:center; margin-bottom:2rem; font-family:'Playfair Display', serif; font-size:2.5rem; color:#008080; }

    .slider-container { position:relative; overflow:hidden; }
    .slider { display:flex; transition:transform 0.5s ease; gap:1rem; }
    .slider img { width:300px; height:200px; object-fit:cover; border-radius:10px; cursor:pointer; }
    .slider-btn { position:absolute; top:50%; transform:translateY(-50%); background:rgba(0,0,0,0.5); color:#fff; border:none; padding:0.5rem 1rem; cursor:pointer; border-radius:5px; font-size:1.5rem; }
    .prev { left:10px; }
    .next { right:10px; }

    .products { display:grid; grid-template-columns: repeat(auto-fit, minmax(250px,1fr)); gap:2rem; }
    .product { background:#fff; border-radius:10px; overflow:hidden; box-shadow:0 4px 10px rgba(0,0,0,0.1); cursor:pointer; transition: transform 0.3s; }
    .product img { width:100%; display:block; }
    .product h3 { padding:1rem; font-size:1.5rem; color:#006666; }
    .product p { padding:0 1rem 1rem; color:#555; }
    .product:hover { transform: translateY(-5px); }

    .instagram-feed { display:grid; grid-template-columns: repeat(auto-fit, minmax(150px,1fr)); gap:1rem; }
    .instagram-feed img { width:100%; border-radius:10px; transition: transform 0.3s; cursor:pointer; }
    .instagram-feed img:hover { transform:scale(1.05); }

    .modal { display:none; position:fixed; top:0; left:0; width:100%; height:100%; background:rgba(0,0,0,0.7); align-items:center; justify-content:center; z-index:1000; }
    .modal-content { background:#fff; padding:2rem; border-radius:10px; max-width:600px; width:90%; position:relative; animation:fadeIn 0.3s ease; }
    .close { position:absolute; top:10px; right:15px; font-size:1.5rem; cursor:pointer; color:#008080; }
    @keyframes fadeIn { from {opacity:0} to {opacity:1} }

    .contact-form { max-width:600px; margin:0 auto; display:flex; flex-direction:column; gap:1rem; }
    .contact-form input, .contact-form textarea { padding:1rem; border:2px solid #008080; border-radius:8px; font-size:1rem; }
    .contact-form button { background:#008080; color:#fff; padding:1rem; border:none; border-radius:8px; font-size:1rem; cursor:pointer; transition:0.3s; }
    .contact-form button:hover { background:#006666; }

    footer { text-align:center; padding:2rem 1rem; background:#006666; color:#fff; margin-top:4rem; }

    @media (max-width:768px){ .hero h2 { font-size:2rem; padding:0.5rem 1rem; } }
</style>
</head>
<body>

<header>
    <h1>Kristyn Creations</h1>
    <p>Delicious Artistry for Your Celebrations</p>
</header>

<nav>
    <a href="#about">About</a>
    <a href="#gallery">Gallery</a>
    <a href="#products">Products</a>
    <a href="#instagram">Instagram</a>
    <a href="#contact">Contact</a>
</nav>

<div class="hero">
    <h2>Sweet Treats, Custom Designs</h2>
</div>

<section id="about">
    <h2>About Kristyn</h2>
    <p style="max-width:800px;margin:0 auto;text-align:center;">
        Kristyn is a passionate baker and artist, specializing in custom cakes, cookies, and personalized merchandise. From elegant flower wedding cakes to fun, themed party treats, Kristyn turns every idea into a delicious masterpiece. She also creates custom cups, t-shirts, and more to match your celebrations.
    </p>
</section>

<section id="gallery">
    <h2>Gallery</h2>
    <div class="slider-container">
        <button class="slider-btn prev" onclick="slide(-1)">&#10094;</button>
        <div class="slider" id="slider">
            <img src="https://images.unsplash.com/photo-1604335399103-1f850e5c7b71?auto=format&fit=crop&w=800&q=80" alt="Wedding Cake" onclick="openModal(this)">
            <img src="https://images.unsplash.com/photo-1599785209790-ffda44e5d22c?auto=format&fit=crop&w=800&q=80" alt="Cookies" onclick="openModal(this)">
            <img src="https://images.unsplash.com/photo-1606755962770-948bdfbc5093?auto=format&fit=crop&w=800&q=80" alt="Custom T-Shirt" onclick="openModal(this)">
            <img src="https://images.unsplash.com/photo-1617196031891-104e64c29d53?auto=format&fit=crop&w=800&q=80" alt="Birthday Cake" onclick="openModal(this)">
        </div>
        <button class="slider-btn next" onclick="slide(1)">&#10095;</button>
    </div>
</section>

<section id="products">
    <h2>Our Creations</h2>
    <div class="products">
        <div class="product" onclick="openModal(this)">
            <img src="https://images.unsplash.com/photo-1604335399103-1f850e5c7b71?auto=format&fit=crop&w=800&q=80" alt="Wedding Cake">
            <h3>Custom Wedding Cake</h3>
            <p>Elegant floral designs for your special day, fully customizable.</p>
        </div>
        <div class="product" onclick="openModal(this)">
            <img src="https://images.unsplash.com/photo-1599785209790-ffda44e5d22c?auto=format&fit=crop&w=800&q=80" alt="Cookies">
            <h3>Custom Cookies</h3>
            <p>Delicious, hand-decorated cookies to match your party theme.</p>
        </div>
        <div class="product" onclick="openModal(this)">
            <img src="https://images.unsplash.com/photo-1606755962770-948bdfbc5093?auto=format&fit=crop&w=800&q=80" alt="Custom T-Shirt">
            <h3>Custom Merchandise</h3>
            <p>Personalized cups, t-shirts, and more for your celebrations.</p>
        </div>
    </div>
</section>

<section id="instagram">
    <h2>Instagram Feed</h2>
    <div class="instagram-feed">
        <img src="https://images.unsplash.com/photo-1599785209790-ffda44e5d22c?auto=format&fit=crop&w=400&q=80" alt="Insta1" onclick="openModal(this)">
        <img src="https://images.unsplash.com/photo-1604335399103-1f850e5c7b71?auto=format&fit=crop&w=400&q=80" alt="Insta2" onclick="openModal(this)">
        <img src="https://images.unsplash.com/photo-1606755962770-948bdfbc5093?auto=format&fit=crop&w=400&q=80" alt="Insta3" onclick="openModal(this)">
        <img src="https://images.unsplash.com/photo-1617196031891-104e64c29d53?auto=format&fit=crop&w=400&q=80" alt="Insta4" onclick="openModal(this)">
    </div>
</section>

<section id="contact">
    <h2>Contact Kristyn</h2>
    <form class="contact-form">
        <input type="text" placeholder="Your Name" required>
        <input type="email" placeholder="Your Email" required>
        <textarea rows="5" placeholder="Your Message" required></textarea>
        <button type="submit">Send Message</button>
    </form>
</section>

<div class="modal" id="modal">
    <div class="modal-content">
        <span class="close" onclick="closeModal()">&times;</span>
        <img id="modal-img" src="" alt="" style="width:100%; border-radius:10px; margin-bottom:1rem;">
        <p id="modal-text"></p>
    </div>
</div>

<footer>
    &copy; 2025 Kristyn Creations. All Rights Reserved.
</footer>

<script>
    function openModal(element){
        document.getElementById('modal').style.display='flex';
        document.getElementById('modal-img').src = element.querySelector('img') ? element.querySelector('img').src : element.src;
        document.getElementById('modal-text').innerText = element.querySelector('h3') ? element.querySelector('h3').innerText : element.alt;
    }
    function closeModal(){ document.getElementById('modal').style.display='none'; }
    window.onclick = function(e){ if(e.target==document.getElementById('modal')) closeModal(); }

    let slider = document.getElementById('slider');
    let scrollAmount = 0;
    function slide(direction){
        let slideWidth = slider.querySelector('img').clientWidth + 16;
        scrollAmount += direction * slideWidth;
        if(scrollAmount < 0) scrollAmount = 0;
        if(scrollAmount > slider.scrollWidth - slider.clientWidth) scrollAmount = slider.scrollWidth - slider.clientWidth;
        slider.style.transform = `translateX(-${scrollAmount}px)`;
    }
</script>

</body>
</html>
