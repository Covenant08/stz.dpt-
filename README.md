# stz.dpt-

# Define project folder structure
project_name = "stz_dpt_website"
base_path = f"/mnt/data/{stz.dpt}"

folders = [
    base_path,
    f"{base_path}/css",
    f"{base_path}/js",
    f"{base_path}/images"
]

# Create directories
for folder in folders:
    os.makedirs(folder, exist_ok=True)

# HTML Content
index_html = """<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>stz.dpt - Coming Soon</title>
    <link rel="stylesheet" href="css/styles.css">
    <script defer src="js/scripts.js"></script>
</head>
<body>
    <div class="container">
        <h1 class="glitch">stz.dpt</h1>
        <p class="tagline">The Future of Streetwear is Coming</p>
        <form id="signup-form">
            <input type="email" placeholder="Enter your email" required>
            <button type="submit">Stay Updated</button>
        </form>
        <div class="socials">
            <a href="#">Instagram</a> | <a href="#">TikTok</a>
        </div>
    </div>
</body>
</html>
"""

# CSS Content
styles_css = """body {
    font-family: 'Arial', sans-serif;
    background: linear-gradient(45deg, #0f0f0f, #1a1a1a);
    color: #fff;
    text-align: center;
    display: flex;
    align-items: center;
    justify-content: center;
    height: 100vh;
    margin: 0;
}

.container {
    animation: fadeIn 2s ease-in-out;
}

.glitch {
    font-size: 4rem;
    text-transform: uppercase;
    font-weight: bold;
    color: #ff00ff;
    animation: glitch 1s infinite alternate;
}

@keyframes glitch {
    0% { text-shadow: 2px 2px #00ffff, -2px -2px #ff00ff; }
    100% { text-shadow: -2px -2px #00ffff, 2px 2px #ff00ff; }
}

.tagline {
    font-size: 1.5rem;
    margin: 10px 0;
}

input, button {
    padding: 10px;
    margin: 5px;
    border: none;
    font-size: 1rem;
}

input {
    width: 200px;
}

button {
    background: #ff00ff;
    color: #fff;
    cursor: pointer;
}

.socials a {
    color: #00ffff;
    text-decoration: none;
    margin: 0 10px;
}"""

# JavaScript Content
scripts_js = """document.getElementById('signup-form').addEventListener('submit', function(event) {
    event.preventDefault();
    alert('Thank you for signing up! Stay tuned.');
});"""

# Write files
with open(f"{base_path}/index.html", "w") as f:
    f.write(index_html)

with open(f"{base_path}/css/styles.css", "w") as f:
    f.write(styles_css)

with open(f"{base_path}/js/scripts.js", "w") as f:
    f.write(scripts_js)

# Zip the project folder
zip_path = f"/mnt/data/{project_name}.zip"
shutil.make_archive(zip_path.replace(".zip", ""), 'zip', base_path)