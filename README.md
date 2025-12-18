<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>INKA COFFEE - Alexander Altamirano Huamán</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0/dist/css/all.min.css">
    <style>
        @import url('https://fonts.googleapis.com/css2?family=Crimson+Pro:ital,wght@0,400;0,700;1,400&family=Playfair+Display:ital,wght@0,700;0,900;1,700&display=swap');

        body { 
            font-family: 'Crimson Pro', serif; 
            background-color: #fdfbf7; 
            background-image: url('https://www.transparenttextures.com/patterns/p6.png');
            scroll-behavior: smooth;
        }

        h1, h2, h3, h4 { font-family: 'Playfair Display', serif; }

        .rustico-card {
            background: #fff;
            border: 1px solid #e2d1c3;
            box-shadow: 8px 8px 0px #e2d1c3;
            transition: all 0.4s ease;
        }

        .rustico-card:hover {
            transform: translate(-4px, -4px);
            box-shadow: 14px 14px 0px #c5b4a5;
        }

        .cart-badge {
            position: absolute;
            top: -5px;
            right: -5px;
            background: #a0522d;
            color: #fff;
            border-radius: 50%;
            padding: 2px 7px;
            font-size: 11px;
            font-weight: bold;
        }

        .wood-header {
            background-color: #1a1412;
            background-image: url('https://www.transparenttextures.com/patterns/black-linen.png');
        }

        .image-container {
            position: relative;
            height: 250px;
            overflow: hidden;
            background: #f3f4f6;
            display: flex;
            align-items: center;
            justify-content: center;
        }

        .btn-rustico {
            background: #2d1e17;
            color: #f3e5f5;
            border-bottom: 4px solid #000;
        }

        .btn-rustico:active {
            border-bottom: 0px;
            transform: translateY(4px);
        }

        /* Floating WhatsApp Button */
        .whatsapp-float {
            position: fixed;
            bottom: 20px;
            left: 20px;
            background-color: #25d366;
            color: white;
            width: 60px;
            height: 60px;
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 30px;
            box-shadow: 2px 2px 10px rgba(0,0,0,0.2);
            z-index: 1000;
            transition: transform 0.3s;
        }
        .whatsapp-float:hover {
            transform: scale(1.1);
        }
    </style>
</head>
<body class="text-stone-800">

    <!-- Floating WhatsApp -->
    <a href="https://wa.me/51982976901" class="whatsapp-float" target="_blank" title="Escríbenos directamente">
        <i class="fab fa-whatsapp"></i>
    </a>

    <!-- Header -->
    <header class="wood-header text-stone-100 p-6 sticky top-0 z-50 border-b border-amber-900/30 shadow-xl">
        <div class="container mx-auto flex justify-between items-center">
            <div class="flex flex-col">
                <h1 class="text-3xl font-black tracking-tighter italic leading-none">INKA <span class="text-amber-500">COFFEE</span></h1>
                <span class="text-[10px] uppercase tracking-[0.2em] text-amber-200/80 mt-1">Prop. Alexander Altamirano Huamán</span>
            </div>
            
            <nav class="hidden lg:flex space-x-8 uppercase text-xs font-bold tracking-widest text-stone-400">
                <a href="#calientes" class="hover:text-amber-500 transition">Calientes</a>
                <a href="#frias" class="hover:text-amber-500 transition">Frías</a>
                <a href="#pasteles" class="hover:text-amber-500 transition">Complementos</a>
                <a href="#contacto" class="hover:text-amber-500 transition">Contacto</a>
            </nav>

            <button onclick="toggleCart()" class="relative p-3 bg-white/5 rounded-full hover:bg-white/10 transition border border-white/20">
                <i class="fas fa-shopping-cart text-xl text-amber-500"></i>
                <span id="cart-count" class="cart-badge">0</span>
            </button>
        </div>
    </header>

    <!-- Hero Section -->
    <section class="relative h-[400px] flex items-center justify-center text-center text-white overflow-hidden">
        <div class="absolute inset-0 bg-black/60 z-10"></div>
        <img src="https://images.unsplash.com/photo-1495474472287-4d71bcdd2085?q=80&w=2000&auto=format&fit=crop" class="absolute inset-0 w-full h-full object-cover" alt="Banner Inka Coffee">
        <div class="relative z-20 px-6">
            <h2 class="text-5xl md:text-7xl font-black mb-2 italic uppercase tracking-tighter">CARTA PREMIUM</h2>
            <p class="text-lg md:text-xl font-light italic mb-8 text-amber-200">Selección exclusiva de Alexander Altamirano Huamán</p>
            <div class="h-1 w-24 bg-amber-600 mx-auto mb-8"></div>
        </div>
    </section>

    <main class="container mx-auto py-16 px-4 max-w-7xl">

        <!-- CALIENTES -->
        <section id="calientes" class="mb-24">
            <div class="text-center mb-12">
                <h3 class="text-4xl font-bold italic text-stone-900">1. Cafés Calientes</h3>
                <p class="text-stone-500 italic">Tradición y aroma en cada taza</p>
                <div class="w-16 h-1 bg-amber-800 mx-auto mt-4"></div>
            </div>
            <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 xl:grid-cols-4 gap-8" id="lista-calientes"></div>
        </section>

        <!-- FRÍAS -->
        <section id="frias" class="mb-24">
            <div class="text-center mb-12">
                <h3 class="text-4xl font-bold italic text-stone-900">2. Especialidades Frías</h3>
                <p class="text-stone-500 italic">Refrescantes y llenas de sabor</p>
                <div class="w-16 h-1 bg-amber-800 mx-auto mt-4"></div>
            </div>
            <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 xl:grid-cols-4 gap-8" id="lista-frias"></div>
        </section>

        <!-- PASTELES -->
        <section id="pasteles" class="mb-24">
            <div class="text-center mb-12">
                <h3 class="text-4xl font-bold italic text-stone-900">3. Pastelería y Salados</h3>
                <p class="text-stone-500 italic">Hechos con amor en nuestra cocina</p>
                <div class="w-16 h-1 bg-amber-800 mx-auto mt-4"></div>
            </div>
            <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 xl:grid-cols-4 gap-8" id="lista-pasteles"></div>
        </section>

        <!-- CONTACTO -->
        <section id="contacto" class="mb-24 rustico-card p-10 border-2 border-stone-800 bg-white">
            <div class="grid grid-cols-1 md:grid-cols-2 gap-12 items-center">
                <div>
                    <h3 class="text-3xl font-black italic text-stone-900 mb-6 uppercase tracking-tighter">Alexander Altamirano Huamán</h3>
                    <p class="text-stone-600 mb-8 italic">"En INKA COFFEE, cada grano cuenta una historia de nuestra tierra Apurímac. Te espero en mi casa para disfrutar del mejor café."</p>
                    
                    <div class="space-y-6">
                        <div class="flex items-center space-x-4">
                            <i class="fas fa-map-marker-alt text-amber-900 text-xl w-8"></i>
                            <span class="font-bold">Jr. Bolognesi N°111 - San Jerónimo, Andahuaylas</span>
                        </div>
                        <div class="flex items-center space-x-4">
                            <i class="fab fa-whatsapp text-green-600 text-2xl w-8"></i>
                            <span class="font-black text-xl">982 976 901</span>
                        </div>
                        <div class="flex items-center space-x-4">
                            <i class="fas fa-phone-alt text-blue-600 text-xl w-8"></i>
                            <span class="font-bold">Llamadas: 982 976 901</span>
                        </div>
                    </div>
                    
                    <a href="https://wa.me/51982976901" target="_blank" class="mt-8 inline-flex items-center space-x-3 bg-green-600 text-white px-8 py-4 rounded-lg font-bold hover:bg-green-700 transition shadow-lg">
                        <i class="fab fa-whatsapp text-2xl"></i>
                        <span>Contactar por WhatsApp</span>
                    </a>
                </div>
                <div class="h-64 bg-stone-100 border border-stone-200 overflow-hidden">
                    <img src="https://images.unsplash.com/photo-1507133750040-4a8f57021571?q=80&w=1000&auto=format&fit=crop" class="w-full h-full object-cover" alt="Coffee Cup">
                </div>
            </div>
        </section>
    </main>

    <!-- Sidebar Carrito -->
    <div id="cart-sidebar" class="fixed top-0 right-0 w-full md:w-[420px] h-full bg-white shadow-[-10px_0_40px_rgba(0,0,0,0.1)] z-[100] transform translate-x-full transition-transform duration-500 ease-in-out flex flex-col border-l-4 border-amber-900">
        <div class="p-8 wood-header text-white flex justify-between items-center">
            <h3 class="text-xl font-bold uppercase italic tracking-widest text-amber-400">Tu Pedido</h3>
            <button onclick="toggleCart()" class="text-3xl hover:text-amber-500">&times;</button>
        </div>
        <div id="cart-items" class="flex-1 overflow-y-auto p-6 space-y-4 bg-stone-50"></div>
        <div class="p-8 bg-white border-t border-stone-200">
            <div class="flex justify-between text-3xl font-black mb-6 italic text-stone-900">
                <span>Total:</span>
                <span id="cart-total">S/ 0.00</span>
            </div>
            <button onclick="finalizarPedido()" class="w-full btn-rustico py-5 font-bold uppercase tracking-widest transition-all flex items-center justify-center space-x-3">
                <i class="fab fa-whatsapp text-xl"></i>
                <span>Enviar Pedido</span>
            </button>
        </div>
    </div>

    <!-- Footer -->
    <footer class="wood-header text-stone-500 py-12 text-center">
        <p class="text-white font-bold italic">INKA COFFEE © 2024</p>
        <p class="text-xs uppercase tracking-widest mt-2">Alexander Altamirano Huamán - Propietario</p>
        <p class="text-[10px] mt-4 opacity-30">San Jerónimo - Andahuaylas - Apurímac</p>
    </footer>

    <script>
        const productos = [
            // CALIENTES (10)
            { id: 1, categoria: 'calientes', nombre: 'Espresso Inka', precio: 7.00, desc: 'Shot concentrado de energía pura.', img: 'https://images.unsplash.com/photo-1510591509098-f4fdc6d0ff04?q=80&w=800&auto=format&fit=crop' },
            { id: 2, categoria: 'calientes', nombre: 'Capuccino Andino', precio: 12.00, desc: 'Espuma cremosa con canela del valle.', img: 'https://images.unsplash.com/photo-1572442388796-11668a67e13d?q=80&w=800&auto=format&fit=crop' },
            { id: 3, categoria: 'calientes', nombre: 'Moka Alexander', precio: 13.50, desc: 'Fusión perfecta de café y cacao de la selva.', img: 'https://images.unsplash.com/photo-1544787210-2213d84ad960?q=80&w=800&auto=format&fit=crop' },
            { id: 4, categoria: 'calientes', nombre: 'Latte Vainilla', precio: 11.50, desc: 'Suavidad con un toque aromático.', img: 'https://images.unsplash.com/photo-1461023058943-07fcbe16d735?q=80&w=800&auto=format&fit=crop' },
            { id: 5, categoria: 'calientes', nombre: 'Americano Clásico', precio: 8.00, desc: 'Café balanceado para cualquier hora.', img: 'https://images.unsplash.com/photo-1495474472287-4d71bcdd2085?q=80&w=800&auto=format&fit=crop' },
            { id: 6, categoria: 'calientes', nombre: 'Flat White Premium', precio: 12.50, desc: 'Doble espresso con microespuma sedosa.', img: 'https://images.unsplash.com/photo-1551887139-147b67069325?q=80&w=800&auto=format&fit=crop' },
            { id: 7, categoria: 'calientes', nombre: 'Caramel Macchiato', precio: 14.00, desc: 'Capas de leche, espresso y caramelo.', img: 'https://images.unsplash.com/photo-1485808191679-5f86510681a2?q=80&w=800&auto=format&fit=crop' },
            { id: 8, categoria: 'calientes', nombre: 'Café Irlandés Inka', precio: 15.00, desc: 'Café con un toque de crema especial.', img: 'https://images.unsplash.com/photo-1576092768241-dec231879fc3?q=80&w=800&auto=format&fit=crop' },
            { id: 9, categoria: 'calientes', nombre: 'Chocolate Caliente', precio: 10.00, desc: 'Cacao 100% puro de la región.', img: 'https://images.unsplash.com/photo-1544787210-2213d84ad960?q=80&w=800&auto=format&fit=crop' },
            { id: 10, categoria: 'calientes', nombre: 'Té de Hierbas Especial', precio: 6.00, desc: 'Infusión de muña y hierba buena.', img: 'https://images.unsplash.com/photo-1576092762791-dd9e2220abd1?q=80&w=800&auto=format&fit=crop' },
            
            // FRÍAS (10)
            { id: 11, categoria: 'frias', nombre: 'Frappuccino Caramelo', precio: 16.00, desc: 'Granizado frío con dulce de leche.', img: 'https://images.unsplash.com/photo-1572490122747-3968b75cc699?q=80&w=800&auto=format&fit=crop' },
            { id: 12, categoria: 'frias', nombre: 'Iced Latte Vainilla', precio: 13.00, desc: 'El clásico con hielo y mucha frescura.', img: 'https://images.unsplash.com/photo-1517701604599-bb29b565090c?q=80&w=800&auto=format&fit=crop' },
            { id: 13, categoria: 'frias', nombre: 'Limonada Frozen', precio: 10.00, desc: 'Limones frescos batidos con hielo.', img: 'https://images.unsplash.com/photo-1513558161293-cdaf765ed2fd?q=80&w=800&auto=format&fit=crop' },
            { id: 14, categoria: 'frias', nombre: 'Frappé de Oreo', precio: 17.00, desc: 'Indulgencia pura con galletas trituradas.', img: 'https://images.unsplash.com/photo-1461023058943-07fcbe16d735?q=80&w=800&auto=format&fit=crop' },
            { id: 15, categoria: 'frias', nombre: 'Cold Brew Añejado', precio: 12.00, desc: 'Extracción en frío por 12 horas.', img: 'https://images.unsplash.com/photo-1499961024600-ad094db305cc?q=80&w=800&auto=format&fit=crop' },
            { id: 16, categoria: 'frias', nombre: 'Affogato Inka', precio: 14.50, desc: 'Helado de vainilla bañado en espresso.', img: 'https://images.unsplash.com/photo-1594631252845-29fc4586c552?q=80&w=800&auto=format&fit=crop' },
            { id: 17, categoria: 'frias', nombre: 'Batido de Fresas', precio: 15.00, desc: 'Frutas frescas de estación.', img: 'https://images.unsplash.com/photo-1543644006-03c035667e80?q=80&w=800&auto=format&fit=crop' },
            { id: 18, categoria: 'frias', nombre: 'Té Helado de Limón', precio: 9.00, desc: 'Refrescante infusión negra con cítricos.', img: 'https://images.unsplash.com/photo-1556679343-c7306c1976bc?q=80&w=800&auto=format&fit=crop' },
            { id: 19, categoria: 'frias', nombre: 'Mocha Frozen', precio: 16.50, desc: 'Chocolate y café en versión bajo cero.', img: 'https://images.unsplash.com/photo-1572490122747-3968b75cc699?q=80&w=800&auto=format&fit=crop' },
            { id: 20, categoria: 'frias', nombre: 'Jugó de Naranja Real', precio: 11.00, desc: 'Recién exprimido frente a ti.', img: 'https://images.unsplash.com/photo-1613478223719-2ab802602423?q=80&w=800&auto=format&fit=crop' },

            // PASTELES Y SALADOS (11)
            { id: 21, categoria: 'pasteles', nombre: 'Tamal Especial Inka', precio: 8.50, desc: 'Tradicional con pollo o carne, servido con salsa criolla.', img: 'https://images.unsplash.com/photo-1581440051182-359f42813580?q=80&w=800&auto=format&fit=crop' },
            { id: 22, categoria: 'pasteles', nombre: 'Budín Alexander', precio: 14.50, desc: 'Nuestra firma. Receta secreta de la casa.', img: 'https://images.unsplash.com/photo-1534432127763-78ef1f128368?q=80&w=800&auto=format&fit=crop' },
            { id: 23, categoria: 'pasteles', nombre: 'Tarta de Manzana', precio: 12.00, desc: 'Masa quebrada con manzanas del valle.', img: 'https://images.unsplash.com/photo-1568571780765-9276ac8b75a2?q=80&w=800&auto=format&fit=crop' },
            { id: 24, categoria: 'pasteles', nombre: 'Sándwich de Pollo', precio: 13.00, desc: 'Con palta y mayonesa artesanal.', img: 'https://images.unsplash.com/photo-1525351484163-7529414344d8?q=80&w=800&auto=format&fit=crop' },
            { id: 25, categoria: 'pasteles', nombre: 'Empanada de Carne', precio: 8.50, desc: 'Horneada, jugosa y tradicional.', img: 'https://images.unsplash.com/photo-1552332386-f8dd00dc2f85?q=80&w=800&auto=format&fit=crop' },
            { id: 26, categoria: 'pasteles', nombre: 'Cheesecake Maracuyá', precio: 15.00, desc: 'Toque ácido y base de galleta.', img: 'https://images.unsplash.com/photo-1533134242443-d4fd215305ad?q=80&w=800&auto=format&fit=crop' },
            { id: 27, categoria: 'pasteles', nombre: 'Muffin de Chocolate', precio: 9.00, desc: 'Con chispas de cacao puro.', img: 'https://images.unsplash.com/photo-1559620192-032c4bc4674e?q=80&w=800&auto=format&fit=crop' },
            { id: 28, categoria: 'pasteles', nombre: 'Croissant Jamón/Queso', precio: 11.50, desc: 'Hojaldre crujiente y mantequilloso.', img: 'https://images.unsplash.com/photo-1555507036-ab1f4038808a?q=80&w=800&auto=format&fit=crop' },
            { id: 29, categoria: 'pasteles', nombre: 'Alfajor Tradicional', precio: 5.00, desc: 'Relleno de abundante manjar blanco.', img: 'https://images.unsplash.com/photo-1590089415225-401ed6f9db8e?q=80&w=800&auto=format&fit=crop' },
            { id: 30, categoria: 'pasteles', nombre: 'Brownie con Nueces', precio: 10.50, desc: 'Húmedo y con trozos de frutos secos.', img: 'https://images.unsplash.com/photo-1461023058943-07fcbe16d735?q=80&w=800&auto=format&fit=crop' },
            { id: 31, categoria: 'pasteles', nombre: 'Toast de Palta', precio: 14.00, desc: 'Pan integral con palta y huevo.', img: 'https://images.unsplash.com/photo-1525351484163-7529414344d8?q=80&w=800&auto=format&fit=crop' }
        ];

        let carrito = [];

        function renderProductos() {
            productos.forEach(p => {
                const container = document.getElementById(`lista-${p.categoria}`);
                if(!container) return;
                const card = `
                    <div class="rustico-card overflow-hidden flex flex-col h-full">
                        <div class="image-container">
                            <i class="fas fa-mug-hot text-stone-200 text-4xl absolute"></i>
                            <img src="${p.img}" alt="${p.nombre}" class="w-full h-full object-cover z-10 relative transition-transform duration-700 hover:scale-110" onerror="this.style.opacity='0'">
                            <div class="absolute bottom-2 left-0 bg-amber-900 text-white px-4 py-1 font-black italic shadow-lg z-20 text-sm">
                                S/ ${p.precio.toFixed(2)}
                            </div>
                        </div>
                        <div class="p-6 flex flex-col flex-1">
                            <h4 class="font-black text-xl uppercase italic tracking-tighter mb-2 text-stone-900 leading-none">${p.nombre}</h4>
                            <p class="text-stone-500 text-xs mb-4 flex-1 italic leading-tight">"${p.desc}"</p>
                            <button onclick="agregarAlCarrito(${p.id})" class="w-full btn-rustico py-3 text-sm font-bold uppercase tracking-widest active:scale-95 flex items-center justify-center space-x-2">
                                <i class="fas fa-cart-plus"></i>
                                <span>Añadir</span>
                            </button>
                        </div>
                    </div>
                `;
                container.innerHTML += card;
            });
        }

        function agregarAlCarrito(id) {
            const prod = productos.find(p => p.id === id);
            const existe = carrito.find(item => item.id === id);
            if(existe) {
                existe.cantidad++;
            } else {
                carrito.push({...prod, cantidad: 1});
            }
            actualizarUI();
            abrirCart();
        }

        function actualizarUI() {
            const count = carrito.reduce((sum, item) => sum + item.cantidad, 0);
            document.getElementById('cart-count').innerText = count;
            const cartItems = document.getElementById('cart-items');
            if(carrito.length === 0) {
                cartItems.innerHTML = `<p class="text-center text-stone-400 italic py-20">El carrito está vacío.</p>`;
                document.getElementById('cart-total').innerText = 'S/ 0.00';
                return;
            }
            let html = '';
            let total = 0;
            carrito.forEach(item => {
                total += item.precio * item.cantidad;
                html += `
                    <div class="flex justify-between items-center bg-white p-4 border border-stone-200 shadow-sm">
                        <div class="flex-1">
                            <h5 class="font-bold text-stone-900 uppercase text-xs">${item.nombre}</h5>
                            <p class="text-amber-800 font-bold">S/ ${item.precio.toFixed(2)}</p>
                        </div>
                        <div class="flex items-center space-x-3">
                            <button onclick="modificarCantidad(${item.id}, -1)" class="w-7 h-7 bg-stone-100 border hover:bg-stone-200 font-bold">-</button>
                            <span class="font-black">${item.cantidad}</span>
                            <button onclick="modificarCantidad(${item.id}, 1)" class="w-7 h-7 bg-stone-100 border hover:bg-stone-200 font-bold">+</button>
                        </div>
                    </div>
                `;
            });
            cartItems.innerHTML = html;
            document.getElementById('cart-total').innerText = `S/ ${total.toFixed(2)}`;
        }

        function modificarCantidad(id, delta) {
            const item = carrito.find(i => i.id === id);
            item.cantidad += delta;
            if(item.cantidad <= 0) carrito = carrito.filter(i => i.id !== id);
            actualizarUI();
        }

        function toggleCart() {
            document.getElementById('cart-sidebar').classList.toggle('translate-x-full');
        }

        function abrirCart() {
            document.getElementById('cart-sidebar').classList.remove('translate-x-full');
        }

        function finalizarPedido() {
            if(carrito.length === 0) return;
            let mensaje = "☕ *INKA COFFEE - NUEVO PEDIDO* ☕\n";
            mensaje += "Prop: Alexander Altamirano Huamán\n\n";
            mensaje += "Hola, deseo ordenar lo siguiente:\n";
            carrito.forEach(item => {
                mensaje += `🔸 *${item.cantidad}x* ${item.nombre} (S/ ${(item.precio * item.cantidad).toFixed(2)})\n`;
            });
            mensaje += `\n*TOTAL: ${document.getElementById('cart-total').innerText}*`;
            mensaje += "\n\n📍 Ubicación: Jr. Bolognesi N°111 - San Jerónimo, Andahuaylas";
            
            // Link to WhatsApp with the correct number
            window.open(`https://wa.me/51982976901?text=${encodeURIComponent(mensaje)}`, '_blank');
        }

        window.onload = renderProductos;
    </script>
</body>
</html>
