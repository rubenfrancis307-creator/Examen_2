# Examen_2
<!DOCTYPE html>
<html lang="es">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Tienda Online</title>

<style>
*{
    margin:0;
    padding:0;
    box-sizing:border-box;
    font-family:Arial, sans-serif;
}

body{
    background:#f4f4f4;
}

header{
    background:#1e3a8a;
    color:white;
    padding:15px;
    display:flex;
    justify-content:space-between;
    align-items:center;
}

nav ul{
    list-style:none;
    display:flex;
    gap:20px;
}

nav a{
    color:white;
    text-decoration:none;
}

.hero{
    text-align:center;
    padding:50px;
    background:linear-gradient(to right,#2563eb,#60a5fa);
    color:white;
}

.productos{
    display:grid;
    grid-template-columns:repeat(auto-fit,minmax(250px,1fr));
    gap:20px;
    padding:30px;
}

.producto{
    background:white;
    border-radius:10px;
    overflow:hidden;
    box-shadow:0 2px 10px rgba(0,0,0,0.1);
    text-align:center;
    padding-bottom:15px;
}

.producto img{
    width:100%;
    height:200px;
    object-fit:cover;
}

.producto h3{
    margin:10px 0;
}

.precio{
    color:green;
    font-size:20px;
    font-weight:bold;
}

button{
    background:#2563eb;
    color:white;
    border:none;
    padding:10px 20px;
    border-radius:5px;
    cursor:pointer;
    margin-top:10px;
}

button:hover{
    background:#1d4ed8;
}

.carrito{
    position:fixed;
    right:20px;
    top:80px;
    width:300px;
    background:white;
    padding:15px;
    border-radius:10px;
    box-shadow:0 0 10px rgba(0,0,0,.2);
}

.carrito ul{
    list-style:none;
    margin-top:10px;
}

.carrito li{
    margin-bottom:8px;
}

.total{
    margin-top:10px;
    font-weight:bold;
    color:green;
}

footer{
    background:#1e3a8a;
    color:white;
    text-align:center;
    padding:15px;
    margin-top:30px;
}
</style>
</head>
<body>

<header>
    <h1>Mi Tienda Online</h1>

    <nav>
        <ul>
            <li><a href="#">Inicio</a></li>
            <li><a href="#">Productos</a></li>
            <li><a href="#">Ofertas</a></li>
            <li><a href="#">Contacto</a></li>
        </ul>
    </nav>
</header>

<section class="hero">
    <h2>Bienvenido a Nuestra Tienda</h2>
    <p>Los mejores productos al mejor precio</p>
</section>

<section class="productos">

    <div class="producto">
        <img src="https://picsum.photos/300/200?1" alt="Producto">
        <h3>Laptop Gamer</h3>
        <p class="precio">$800</p>
        <button onclick="agregarCarrito('Laptop Gamer',800)">
            Agregar al carrito
        </button>
    </div>

    <div class="producto">
        <img src="https://picsum.photos/300/200?2" alt="Producto">
        <h3>Smartphone</h3>
        <p class="precio">$450</p>
        <button onclick="agregarCarrito('Smartphone',450)">
            Agregar al carrito
        </button>
    </div>

    <div class="producto">
        <img src="https://picsum.photos/300/200?3" alt="Producto">
        <h3>Audífonos</h3>
        <p class="precio">$50</p>
        <button onclick="agregarCarrito('Audífonos',50)">
            Agregar al carrito
        </button>
    </div>

</section>

<div class="carrito">
    <h2>🛒 Carrito</h2>
    <ul id="listaCarrito"></ul>
    <div class="total">
        Total: $<span id="total">0</span>
    </div>
</div>

<footer>
    <p>© 2026 Mi Tienda Online - Todos los derechos reservados</p>
</footer>

<script>
let total = 0;

function agregarCarrito(nombre, precio){

    let lista = document.getElementById("listaCarrito");

    let item = document.createElement("li");
    item.textContent = `${nombre} - $${precio}`;

    lista.appendChild(item);

    total += precio;

    document.getElementById("total").textContent = total;
}
</script>

</body>
</html>
