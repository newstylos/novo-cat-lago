i[index.html](https://github.com/user-attachments/files/22100831/index.html)
<!DOCTYPE html>
<html lang="pt-BR">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>New Stylos Camisetas - Catálogo Online</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Arial', sans-serif;
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            min-height: 100vh;
            padding: 20px;
        }

        .header {
            background: linear-gradient(135deg, #2c3e50 0%, #34495e 100%);
            color: white;
            padding: 30px;
            text-align: center;
            border-radius: 15px;
            margin-bottom: 30px;
            box-shadow: 0 10px 30px rgba(0,0,0,0.2);
        }

        .header h1 {
            font-size: 2.5rem;
            margin-bottom: 10px;
            font-weight: 700;
        }

        .header p {
            font-size: 1.1rem;
            opacity: 0.9;
        }

        .controls {
            display: flex;
            justify-content: space-between;
            align-items: center;
            margin-bottom: 30px;
            flex-wrap: wrap;
            gap: 15px;
        }

        .admin-controls {
            display: flex;
            gap: 10px;
            flex-wrap: wrap;
        }

        .cart-controls {
            display: flex;
            gap: 10px;
            align-items: center;
        }

        .btn {
            background: #007bff;
            color: white;
            border: none;
            padding: 12px 20px;
            border-radius: 25px;
            font-weight: 600;
            cursor: pointer;
            transition: all 0.3s ease;
            font-size: 0.9rem;
            display: flex;
            align-items: center;
            gap: 8px;
        }

        .btn:hover {
            transform: scale(1.05);
        }

        .btn-success {
            background: #28a745;
        }

        .btn-success:hover {
            background: #218838;
        }

        .btn-warning {
            background: #ffc107;
            color: #212529;
        }

        .btn-warning:hover {
            background: #e0a800;
        }

        .btn-danger {
            background: #dc3545;
        }

        .btn-danger:hover {
            background: #c82333;
        }

        .cart-badge {
            background: #dc3545;
            color: white;
            border-radius: 50%;
            padding: 4px 8px;
            font-size: 0.8rem;
            font-weight: bold;
            min-width: 20px;
            text-align: center;
        }

        .products-container {
            max-width: 1200px;
            margin: 0 auto;
        }

        .products-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(350px, 1fr));
            gap: 25px;
            margin-bottom: 30px;
        }

        .product-card {
            background: white;
            border-radius: 15px;
            padding: 25px;
            box-shadow: 0 10px 30px rgba(0,0,0,0.1);
            transition: all 0.3s ease;
            position: relative;
        }

        .product-card:hover {
            transform: translateY(-5px);
            box-shadow: 0 15px 40px rgba(0,0,0,0.15);
        }

        .product-image-container {
            width: 100%;
            margin-bottom: 20px;
            position: relative;
        }

        .main-image {
            width: 100%;
            height: 250px;
            background: linear-gradient(135deg, #f8f9fa 0%, #e9ecef 100%);
            border: 2px solid #dee2e6;
            border-radius: 15px;
            display: flex;
            align-items: center;
            justify-content: center;
            color: #6c757d;
            font-size: 1rem;
            text-align: center;
            margin-bottom: 10px;
            transition: all 0.3s ease;
            cursor: pointer;
            position: relative;
            overflow: hidden;
        }

        .main-image:hover {
            border-color: #007bff;
            transform: scale(1.02);
        }

        .main-image.has-image {
            background: #fff;
            border-color: #28a745;
        }

        .image-thumbnails {
            display: flex;
            gap: 8px;
            justify-content: center;
        }

        .thumbnail {
            width: 60px;
            height: 60px;
            background: #f8f9fa;
            border: 2px solid #dee2e6;
            border-radius: 8px;
            display: flex;
            align-items: center;
            justify-content: center;
            cursor: pointer;
            transition: all 0.3s ease;
            font-size: 0.7rem;
            color: #6c757d;
            text-align: center;
        }

        .thumbnail:hover {
            border-color: #007bff;
            transform: scale(1.1);
        }

        .thumbnail.active {
            border-color: #007bff;
            background: #e3f2fd;
        }

        .thumbnail.has-image {
            border-color: #28a745;
            background: #e8f5e8;
        }

        .image-upload-btn {
            position: absolute;
            top: 10px;
            right: 10px;
            background: rgba(0, 123, 255, 0.9);
            color: white;
            border: none;
            padding: 8px 12px;
            border-radius: 20px;
            font-size: 0.8rem;
            cursor: pointer;
            transition: all 0.3s ease;
            opacity: 0;
        }

        .product-image-container:hover .image-upload-btn {
            opacity: 1;
        }

        .image-upload-btn:hover {
            background: rgba(0, 123, 255, 1);
            transform: scale(1.05);
        }

        .product-title {
            font-size: 1.4rem;
            font-weight: 600;
            color: #2c3e50;
            margin-bottom: 10px;
        }

        .product-description {
            color: #6c757d;
            line-height: 1.5;
            margin-bottom: 15px;
            font-size: 0.9rem;
        }

        .product-price {
            font-size: 1.6rem;
            font-weight: 700;
            color: #28a745;
            margin-bottom: 20px;
        }

        .product-options {
            margin-bottom: 20px;
        }

        .option-group {
            margin-bottom: 15px;
        }

        .option-label {
            font-weight: 600;
            color: #2c3e50;
            margin-bottom: 8px;
            display: block;
        }

        .size-options, .color-options {
            display: flex;
            gap: 8px;
            flex-wrap: wrap;
        }

        .size-btn, .color-btn {
            padding: 8px 12px;
            border: 2px solid #dee2e6;
            background: white;
            border-radius: 20px;
            cursor: pointer;
            transition: all 0.3s ease;
            font-size: 0.85rem;
            font-weight: 600;
        }

        .size-btn:hover, .color-btn:hover {
            border-color: #007bff;
            background: #e3f2fd;
        }

        .size-btn.selected, .color-btn.selected {
            background: #007bff;
            color: white;
            border-color: #007bff;
        }

        .quantity-control {
            display: flex;
            align-items: center;
            gap: 10px;
            margin-bottom: 15px;
        }

        .quantity-btn {
            background: #6c757d;
            color: white;
            border: none;
            width: 35px;
            height: 35px;
            border-radius: 50%;
            cursor: pointer;
            font-weight: bold;
            transition: all 0.3s ease;
        }

        .quantity-btn:hover {
            background: #495057;
        }

        .quantity-display {
            background: #f8f9fa;
            padding: 8px 15px;
            border-radius: 20px;
            font-weight: 600;
            min-width: 50px;
            text-align: center;
        }

        .add-to-cart-btn {
            width: 100%;
            background: #28a745;
            color: white;
            border: none;
            padding: 15px;
            border-radius: 25px;
            font-weight: 600;
            cursor: pointer;
            transition: all 0.3s ease;
            font-size: 1rem;
        }

        .add-to-cart-btn:hover {
            background: #218838;
            transform: scale(1.02);
        }

        .add-to-cart-btn:disabled {
            background: #6c757d;
            cursor: not-allowed;
            transform: none;
        }

        .admin-panel {
            background: white;
            padding: 25px;
            border-radius: 15px;
            margin-bottom: 30px;
            box-shadow: 0 10px 30px rgba(0,0,0,0.1);
            display: none;
        }

        .admin-panel.active {
            display: block;
        }

        .form-group {
            margin-bottom: 20px;
        }

        .form-label {
            display: block;
            font-weight: 600;
            color: #2c3e50;
            margin-bottom: 8px;
        }

        .form-input {
            width: 100%;
            padding: 12px;
            border: 2px solid #dee2e6;
            border-radius: 10px;
            font-size: 1rem;
            transition: border-color 0.3s ease;
        }

        .form-input:focus {
            outline: none;
            border-color: #007bff;
        }

        .cart-sidebar {
            position: fixed;
            right: -400px;
            top: 0;
            width: 400px;
            height: 100vh;
            background: white;
            box-shadow: -5px 0 15px rgba(0,0,0,0.1);
            transition: right 0.3s ease;
            z-index: 1000;
            overflow-y: auto;
        }

        .cart-sidebar.active {
            right: 0;
        }

        .cart-header {
            background: #2c3e50;
            color: white;
            padding: 20px;
            display: flex;
            justify-content: space-between;
            align-items: center;
        }

        .cart-close {
            background: none;
            border: none;
            color: white;
            font-size: 1.5rem;
            cursor: pointer;
        }

        .cart-content {
            padding: 20px;
        }

        .cart-item {
            background: #f8f9fa;
            padding: 15px;
            border-radius: 10px;
            margin-bottom: 15px;
            border-left: 4px solid #007bff;
        }

        .cart-item-title {
            font-weight: 600;
            color: #2c3e50;
            margin-bottom: 5px;
        }

        .cart-item-details {
            font-size: 0.9rem;
            color: #6c757d;
            margin-bottom: 10px;
        }

        .cart-item-price {
            font-weight: 600;
            color: #28a745;
            font-size: 1.1rem;
        }

        .cart-total {
            background: #e9ecef;
            padding: 20px;
            border-radius: 10px;
            margin: 20px 0;
            text-align: center;
        }

        .cart-total-amount {
            font-size: 1.8rem;
            font-weight: 700;
            color: #2c3e50;
        }

        .whatsapp-btn {
            width: 100%;
            background: #25d366;
            color: white;
            border: none;
            padding: 15px;
            border-radius: 25px;
            font-weight: 600;
            cursor: pointer;
            transition: all 0.3s ease;
            font-size: 1rem;
            margin-top: 10px;
        }

        .whatsapp-btn:hover {
            background: #128c7e;
            transform: scale(1.02);
        }

        .empty-cart {
            text-align: center;
            color: #6c757d;
            padding: 40px 20px;
        }

        @media (max-width: 768px) {
            .header h1 {
                font-size: 2rem;
            }
            
            .products-grid {
                grid-template-columns: 1fr;
            }
            
            .controls {
                flex-direction: column;
                align-items: stretch;
            }
            
            .admin-controls, .cart-controls {
                justify-content: center;
            }
            
            .cart-sidebar {
                width: 100%;
                right: -100%;
            }
        }
    </style>
</head>
<body>
    <div class="header">
        <h1>👕 New Stylos Camisetas</h1>
        <p>Catálogo Online - Qualidade Premium com Preços Justos</p>
    </div>

    <div class="controls">
        <div class="admin-controls">
            <button class="btn btn-success" onclick="toggleAdminPanel()">
                ⚙️ Gerenciar Produtos
            </button>
            <button class="btn btn-warning" onclick="addNewProduct()">
                ➕ Novo Produto
            </button>
            <button class="btn" style="background: #25d366;" onclick="toggleWhatsAppConfig()">
                📱 Configurar WhatsApp
            </button>
        </div>
        
        <div class="cart-controls">
            <button class="btn" onclick="toggleCart()" style="font-size: 1.1rem; padding: 15px 25px;">
                🛒 Ver Carrinho
                <span class="cart-badge" id="cartBadge">0</span>
            </button>
        </div>
    </div>

    <div class="admin-panel" id="adminPanel">
        <h3 style="margin-bottom: 20px; color: #2c3e50;">📝 Adicionar/Editar Produto</h3>
        <form id="productForm">
            <div class="form-group">
                <label class="form-label">Nome do Produto</label>
                <input type="text" class="form-input" id="productName" placeholder="Ex: Camiseta Gola O">
            </div>
            
            <div class="form-group">
                <label class="form-label">Descrição</label>
                <input type="text" class="form-input" id="productDescription" placeholder="Descrição do produto">
            </div>
            
            <div class="form-group">
                <label class="form-label">Preço (R$)</label>
                <input type="number" class="form-input" id="productPrice" placeholder="39.90" step="0.01">
            </div>
            
            <div class="form-group">
                <label class="form-label">Tamanhos (separados por vírgula)</label>
                <input type="text" class="form-input" id="productSizes" placeholder="PP,P,M,G,GG">
            </div>
            
            <div class="form-group">
                <label class="form-label">Cores (separadas por vírgula)</label>
                <input type="text" class="form-input" id="productColors" placeholder="Branco,Preto,Azul">
            </div>
            
            <div style="display: flex; gap: 10px;">
                <button type="button" class="btn btn-success" onclick="saveProduct()">
                    💾 Salvar Produto
                </button>
                <button type="button" class="btn btn-danger" onclick="cancelEdit()">
                    ❌ Cancelar
                </button>
            </div>
        </form>
    </div>

    <div class="admin-panel" id="whatsappPanel">
        <h3 style="margin-bottom: 20px; color: #2c3e50;">📱 Configurar WhatsApp</h3>
        <form id="whatsappForm">
            <div class="form-group">
                <label class="form-label">Número do WhatsApp</label>
                <input type="text" class="form-input" id="whatsappNumber" placeholder="5511999999999" value="5511999999999">
                <small style="color: #6c757d; font-size: 0.85rem; margin-top: 5px; display: block;">
                    Formato: Código do país + DDD + número (ex: 5511999999999)
                </small>
            </div>
            
            <div class="form-group">
                <label class="form-label">Chave PIX</label>
                <input type="text" class="form-input" id="pixKey" placeholder="00.000.000/0001-00" value="00.000.000/0001-00">
                <small style="color: #6c757d; font-size: 0.85rem; margin-top: 5px; display: block;">
                    CNPJ, CPF, e-mail ou chave aleatória
                </small>
            </div>
            
            <div class="form-group">
                <label class="form-label">Nome do Favorecido PIX</label>
                <input type="text" class="form-input" id="pixName" placeholder="New Stylos Camisetas" value="New Stylos Camisetas">
            </div>
            
            <div style="display: flex; gap: 10px;">
                <button type="button" class="btn btn-success" onclick="saveWhatsAppConfig()">
                    💾 Salvar Configurações
                </button>
                <button type="button" class="btn btn-danger" onclick="cancelWhatsAppConfig()">
                    ❌ Cancelar
                </button>
            </div>
        </form>
    </div>

    <div class="products-container">
        <div class="products-grid" id="productsGrid">
            <!-- Produtos serão carregados aqui -->
        </div>
    </div>

    <!-- Rodapé -->
    <div style="background: white; border-radius: 15px; padding: 25px; margin-top: 30px; text-align: center; box-shadow: 0 10px 30px rgba(0,0,0,0.1);">
        <div style="color: #6c757d; font-size: 0.9rem;">
            © 2024 New Stylos Camisetas - Todos os direitos reservados
        </div>
    </div>

    <!-- Carrinho Lateral -->
    <div class="cart-sidebar" id="cartSidebar">
        <div class="cart-header">
            <h3>🛒 Seu Carrinho</h3>
            <button class="cart-close" onclick="toggleCart()">✕</button>
        </div>
        <div class="cart-content" id="cartContent">
            <!-- Itens do carrinho serão carregados aqui -->
        </div>
    </div>

    <script>
        // Dados dos produtos (simulando um banco de dados)
        let products = [
            {
                id: 1,
                name: "Camiseta Gola O",
                description: "Malha fria Viscolycra (95% viscose, 5% elastano). Não dá bolinha, não encolhe, não desbota.",
                price: 39.90,
                sizes: ["PP", "P", "M", "G", "GG"],
                colors: ["Branco", "Preto", "Cinza", "Azul Marinho", "Verde"],
                images: [null, null, null] // 3 slots para imagens
            },
            {
                id: 2,
                name: "Camiseta Gola V",
                description: "Malha fria Viscolycra premium com gola V moderna e confortável.",
                price: 42.90,
                sizes: ["PP", "P", "M", "G", "GG"],
                colors: ["Branco", "Preto", "Cinza", "Azul Marinho"],
                images: [null, null, null]
            },
            {
                id: 3,
                name: "Polo Clássica",
                description: "Polo premium em malha fria Viscolycra com acabamento profissional.",
                price: 79.90,
                sizes: ["PP", "P", "M", "G", "GG"],
                colors: ["Branco", "Preto", "Marinho", "Cinza"],
                images: [null, null, null]
            }
        ];

        let cart = [];
        let editingProductId = null;
        
        // Configurações do WhatsApp (podem ser editadas pelo usuário)
        let whatsappConfig = {
            number: '5511999999999',
            pixKey: '00.000.000/0001-00',
            pixName: 'New Stylos Camisetas'
        };

        // Carregar produtos na tela
        function loadProducts() {
            const grid = document.getElementById('productsGrid');
            grid.innerHTML = '';

            products.forEach(product => {
                const productCard = createProductCard(product);
                grid.appendChild(productCard);
            });
        }

        // Criar card do produto
        function createProductCard(product) {
            const card = document.createElement('div');
            card.className = 'product-card';
            
            const mainImageContent = product.images[0] ? 
                `<img src="${product.images[0]}" alt="${product.name}" style="width: 100%; height: 100%; object-fit: cover; border-radius: 13px;">` :
                `<div>📷<br><strong>${product.name}</strong><br>Clique para adicionar foto</div>`;
            
            card.innerHTML = `
                <div class="product-image-container">
                    <div class="main-image ${product.images[0] ? 'has-image' : ''}" onclick="selectMainImage(${product.id}, 0)">
                        ${mainImageContent}
                        <button class="image-upload-btn" onclick="event.stopPropagation(); uploadImage(${product.id}, 0)">
                            📷 Foto
                        </button>
                    </div>
                    <div class="image-thumbnails">
                        ${product.images.map((img, index) => {
                            if (index === 0) return ''; // Pular a primeira (imagem principal)
                            const content = img ? 
                                `<img src="${img}" alt="Foto ${index + 1}" style="width: 100%; height: 100%; object-fit: cover; border-radius: 6px;">` :
                                `Foto<br>${index + 1}`;
                            return `
                                <div class="thumbnail ${img ? 'has-image' : ''}" onclick="selectMainImage(${product.id}, ${index})" title="Foto ${index + 1}">
                                    ${content}
                                    <input type="file" id="upload-${product.id}-${index}" accept="image/*" style="display: none;" onchange="handleImageUpload(${product.id}, ${index}, this)">
                                </div>
                            `;
                        }).join('')}
                    </div>
                </div>
                <div class="product-title">${product.name}</div>
                <div class="product-description">${product.description}</div>
                <div class="product-price">R$ ${product.price.toFixed(2).replace('.', ',')}</div>
                
                <div class="product-options">
                    <div class="option-group">
                        <label class="option-label">Tamanho:</label>
                        <div class="size-options">
                            ${product.sizes.map(size => 
                                `<button class="size-btn" onclick="selectSize(${product.id}, '${size}')">${size}</button>`
                            ).join('')}
                        </div>
                    </div>
                    
                    <div class="option-group">
                        <label class="option-label">Cor:</label>
                        <div class="color-options">
                            ${product.colors.map(color => 
                                `<button class="color-btn" onclick="selectColor(${product.id}, '${color}')">${color}</button>`
                            ).join('')}
                        </div>
                    </div>
                    
                    <div class="option-group">
                        <label class="option-label">Quantidade:</label>
                        <div class="quantity-control">
                            <button class="quantity-btn" onclick="changeQuantity(${product.id}, -1)">-</button>
                            <div class="quantity-display" id="qty-${product.id}">1</div>
                            <button class="quantity-btn" onclick="changeQuantity(${product.id}, 1)">+</button>
                        </div>
                    </div>
                </div>
                
                <button class="add-to-cart-btn" onclick="addToCart(${product.id})">
                    🛒 Adicionar ao Carrinho
                </button>
                
                <div style="margin-top: 15px; display: flex; gap: 10px;">
                    <button class="btn btn-warning" style="flex: 1; padding: 8px;" onclick="editProduct(${product.id})">
                        ✏️ Editar
                    </button>
                    <button class="btn btn-danger" style="flex: 1; padding: 8px;" onclick="deleteProduct(${product.id})">
                        🗑️ Excluir
                    </button>
                </div>
            `;
            return card;
        }

        // Seleção de tamanho
        function selectSize(productId, size) {
            const buttons = document.querySelectorAll(`[onclick="selectSize(${productId}, '${size}')"]`);
            const allSizeButtons = document.querySelectorAll('.size-btn');
            
            // Remove seleção de todos os tamanhos do produto
            allSizeButtons.forEach(btn => {
                if (btn.onclick && btn.onclick.toString().includes(`selectSize(${productId},`)) {
                    btn.classList.remove('selected');
                }
            });
            
            // Adiciona seleção ao tamanho clicado
            buttons.forEach(btn => btn.classList.add('selected'));
        }

        // Seleção de cor
        function selectColor(productId, color) {
            const buttons = document.querySelectorAll(`[onclick="selectColor(${productId}, '${color}')"]`);
            const allColorButtons = document.querySelectorAll('.color-btn');
            
            // Remove seleção de todas as cores do produto
            allColorButtons.forEach(btn => {
                if (btn.onclick && btn.onclick.toString().includes(`selectColor(${productId},`)) {
                    btn.classList.remove('selected');
                }
            });
            
            // Adiciona seleção à cor clicada
            buttons.forEach(btn => btn.classList.add('selected'));
        }

        // Alterar quantidade
        function changeQuantity(productId, change) {
            const qtyElement = document.getElementById(`qty-${productId}`);
            let currentQty = parseInt(qtyElement.textContent);
            currentQty = Math.max(1, currentQty + change);
            qtyElement.textContent = currentQty;
        }

        // Adicionar ao carrinho
        function addToCart(productId) {
            const product = products.find(p => p.id === productId);
            const selectedSize = document.querySelector(`.size-btn.selected[onclick*="selectSize(${productId},"]`);
            const selectedColor = document.querySelector(`.color-btn.selected[onclick*="selectColor(${productId},"]`);
            const quantity = parseInt(document.getElementById(`qty-${productId}`).textContent);

            if (!selectedSize || !selectedColor) {
                alert('⚠️ Por favor, selecione o tamanho e a cor!');
                return;
            }

            const cartItem = {
                id: Date.now(),
                productId: productId,
                name: product.name,
                price: product.price,
                size: selectedSize.textContent,
                color: selectedColor.textContent,
                quantity: quantity,
                total: product.price * quantity
            };

            cart.push(cartItem);
            updateCartBadge();
            updateCartContent();
            
            // Feedback visual
            const btn = event.target;
            const originalText = btn.textContent;
            btn.textContent = '✅ Adicionado!';
            btn.style.background = '#28a745';
            
            setTimeout(() => {
                btn.textContent = originalText;
                btn.style.background = '#28a745';
            }, 1500);
        }

        // Atualizar badge do carrinho
        function updateCartBadge() {
            const badge = document.getElementById('cartBadge');
            const totalItems = cart.reduce((sum, item) => sum + item.quantity, 0);
            badge.textContent = totalItems;
        }

        // Atualizar conteúdo do carrinho
        function updateCartContent() {
            const cartContent = document.getElementById('cartContent');
            
            if (cart.length === 0) {
                cartContent.innerHTML = `
                    <div class="empty-cart">
                        <div style="font-size: 3rem; margin-bottom: 20px;">🛒</div>
                        <p>Seu carrinho está vazio</p>
                        <p style="font-size: 0.9rem; margin-top: 10px;">Adicione produtos para começar!</p>
                    </div>
                `;
                return;
            }

            const cartItemsHTML = cart.map(item => `
                <div class="cart-item">
                    <div class="cart-item-title">${item.name}</div>
                    <div class="cart-item-details">
                        Tamanho: ${item.size} | Cor: ${item.color} | Qtd: ${item.quantity}
                    </div>
                    <div class="cart-item-price">R$ ${item.total.toFixed(2).replace('.', ',')}</div>
                    <button class="btn btn-danger" style="margin-top: 10px; padding: 5px 10px; font-size: 0.8rem;" onclick="removeFromCart(${item.id})">
                        🗑️ Remover
                    </button>
                </div>
            `).join('');

            const subtotal = cart.reduce((sum, item) => sum + item.total, 0);
            const pixDiscount = subtotal * 0.05;
            const pixTotal = subtotal - pixDiscount;
            const cardTotal = subtotal;
            const cardInstallment = cardTotal / 3;

            cartContent.innerHTML = `
                ${cartItemsHTML}
                
                <div class="payment-options" style="margin: 20px 0;">
                    <h4 style="color: #2c3e50; margin-bottom: 15px; text-align: center;">💳 Formas de Pagamento</h4>
                    
                    <!-- Opção PIX -->
                    <div class="payment-option" style="background: #e8f5e8; border: 2px solid #28a745; border-radius: 10px; padding: 15px; margin-bottom: 15px; cursor: pointer;" onclick="selectPayment('pix')">
                        <div style="display: flex; align-items: center; margin-bottom: 10px;">
                            <input type="radio" name="payment" id="pixPayment" style="margin-right: 10px;">
                            <label for="pixPayment" style="font-weight: 600; color: #28a745; font-size: 1.1rem;">🏦 PIX - 5% de Desconto</label>
                        </div>
                        <div style="font-size: 0.9rem; color: #155724; margin-bottom: 8px;">
                            Subtotal: R$ ${subtotal.toFixed(2).replace('.', ',')}
                        </div>
                        <div style="font-size: 0.9rem; color: #155724; margin-bottom: 8px;">
                            Desconto (5%): -R$ ${pixDiscount.toFixed(2).replace('.', ',')}
                        </div>
                        <div style="font-size: 1.2rem; font-weight: 700; color: #28a745;">
                            Total: R$ ${pixTotal.toFixed(2).replace('.', ',')}
                        </div>
                    </div>
                    
                    <!-- Opção Cartão -->
                    <div class="payment-option" style="background: #e3f2fd; border: 2px solid #007bff; border-radius: 10px; padding: 15px; margin-bottom: 15px; cursor: pointer;" onclick="selectPayment('card')">
                        <div style="display: flex; align-items: center; margin-bottom: 10px;">
                            <input type="radio" name="payment" id="cardPayment" style="margin-right: 10px;">
                            <label for="cardPayment" style="font-weight: 600; color: #007bff; font-size: 1.1rem;">💳 Cartão de Crédito</label>
                        </div>
                        <div style="font-size: 0.9rem; color: #0c5460; margin-bottom: 8px;">
                            3x sem juros de R$ ${cardInstallment.toFixed(2).replace('.', ',')}
                        </div>
                        <div style="font-size: 1.2rem; font-weight: 700; color: #007bff;">
                            Total: R$ ${cardTotal.toFixed(2).replace('.', ',')}
                        </div>
                    </div>
                </div>
                
                <button class="whatsapp-btn" onclick="sendWhatsAppOrder()" id="finalizeBtn" disabled style="opacity: 0.6;">
                    📱 Finalizar Pedido
                </button>
                <button class="btn btn-danger" style="width: 100%; margin-top: 10px;" onclick="clearCart()">
                    🗑️ Limpar Carrinho
                </button>
            `;
        }

        // Remover item do carrinho
        function removeFromCart(itemId) {
            cart = cart.filter(item => item.id !== itemId);
            updateCartBadge();
            updateCartContent();
        }

        // Limpar carrinho
        function clearCart() {
            if (confirm('Tem certeza que deseja limpar o carrinho?')) {
                cart = [];
                selectedPaymentMethod = null;
                updateCartBadge();
                updateCartContent();
            }
        }

        // Variável global para armazenar forma de pagamento selecionada
        let selectedPaymentMethod = null;

        // Selecionar forma de pagamento
        function selectPayment(method) {
            selectedPaymentMethod = method;
            
            // Atualizar visual dos radio buttons
            document.getElementById('pixPayment').checked = (method === 'pix');
            document.getElementById('cardPayment').checked = (method === 'card');
            
            // Habilitar botão de finalizar
            const finalizeBtn = document.getElementById('finalizeBtn');
            finalizeBtn.disabled = false;
            finalizeBtn.style.opacity = '1';
            
            // Atualizar visual das opções
            const paymentOptions = document.querySelectorAll('.payment-option');
            paymentOptions.forEach(option => {
                option.style.transform = 'scale(1)';
                option.style.boxShadow = 'none';
            });
            
            // Destacar opção selecionada
            const selectedOption = event.currentTarget;
            selectedOption.style.transform = 'scale(1.02)';
            selectedOption.style.boxShadow = '0 5px 15px rgba(0,0,0,0.2)';
        }

        // Enviar pedido pelo WhatsApp
        function sendWhatsAppOrder() {
            if (cart.length === 0) {
                alert('Carrinho vazio!');
                return;
            }

            if (!selectedPaymentMethod) {
                alert('⚠️ Por favor, selecione uma forma de pagamento!');
                return;
            }

            const subtotal = cart.reduce((sum, item) => sum + item.total, 0);
            let finalTotal, paymentInfo;

            if (selectedPaymentMethod === 'pix') {
                const discount = subtotal * 0.05;
                finalTotal = subtotal - discount;
                paymentInfo = `💳 *FORMA DE PAGAMENTO: PIX*\n🏦 Chave PIX: ${whatsappConfig.pixKey}\n💰 Desconto de 5%: -R$ ${discount.toFixed(2).replace('.', ',')}\n`;
            } else {
                finalTotal = subtotal;
                paymentInfo = `💳 *FORMA DE PAGAMENTO: CARTÃO DE CRÉDITO*\n📊 Parcelamento: 3x sem juros de R$ ${(finalTotal/3).toFixed(2).replace('.', ',')}\n💻 Link de pagamento será enviado\n`;
            }

            let message = '🛒 *NOVO PEDIDO - New Stylos Camisetas*\n\n';
            
            cart.forEach((item, index) => {
                message += `${index + 1}. *${item.name}*\n`;
                message += `   Tamanho: ${item.size}\n`;
                message += `   Cor: ${item.color}\n`;
                message += `   Quantidade: ${item.quantity}\n`;
                message += `   Valor: R$ ${item.total.toFixed(2).replace('.', ',')}\n\n`;
            });

            message += `📊 *RESUMO DO PEDIDO:*\n`;
            message += `Subtotal: R$ ${subtotal.toFixed(2).replace('.', ',')}\n`;
            message += paymentInfo;
            message += `💰 *TOTAL FINAL: R$ ${finalTotal.toFixed(2).replace('.', ',')}*\n\n`;
            
            if (selectedPaymentMethod === 'pix') {
                message += '🏦 *Dados para PIX:*\n';
                message += `Chave PIX: ${whatsappConfig.pixKey}\n`;
                message += `Favorecido: ${whatsappConfig.pixName}\n\n`;
                message += '📱 Após o pagamento, envie o comprovante!';
            } else {
                message += '💳 *Pagamento no Cartão:*\n';
                message += 'Vou enviar o link de pagamento seguro\n';
                message += 'Parcelamento em 3x sem juros\n\n';
                message += '📱 Aguarde o link de pagamento!';
            }

            const encodedMessage = encodeURIComponent(message);
            const whatsappURL = `https://wa.me/${whatsappConfig.number}?text=${encodedMessage}`;
            
            window.open(whatsappURL, '_blank');
            
            // Limpar carrinho após envio
            setTimeout(() => {
                if (confirm('Pedido enviado! Deseja limpar o carrinho?')) {
                    clearCart();
                    toggleCart();
                }
            }, 2000);
        }

        // Toggle carrinho
        function toggleCart() {
            const cartSidebar = document.getElementById('cartSidebar');
            cartSidebar.classList.toggle('active');
        }

        // Toggle painel admin
        function toggleAdminPanel() {
            const adminPanel = document.getElementById('adminPanel');
            adminPanel.classList.toggle('active');
        }

        // Adicionar novo produto
        function addNewProduct() {
            editingProductId = null;
            document.getElementById('productForm').reset();
            document.getElementById('adminPanel').classList.add('active');
        }

        // Editar produto
        function editProduct(productId) {
            const product = products.find(p => p.id === productId);
            editingProductId = productId;
            
            document.getElementById('productName').value = product.name;
            document.getElementById('productDescription').value = product.description;
            document.getElementById('productPrice').value = product.price;
            document.getElementById('productSizes').value = product.sizes.join(',');
            document.getElementById('productColors').value = product.colors.join(',');
            
            document.getElementById('adminPanel').classList.add('active');
        }

        // Funções para gerenciar imagens
        function uploadImage(productId, imageIndex) {
            const input = document.getElementById(`upload-${productId}-${imageIndex}`);
            if (input) {
                input.click();
            } else {
                // Criar input temporário para upload
                const tempInput = document.createElement('input');
                tempInput.type = 'file';
                tempInput.accept = 'image/*';
                tempInput.onchange = function() {
                    handleImageUpload(productId, imageIndex, this);
                };
                tempInput.click();
            }
        }

        function handleImageUpload(productId, imageIndex, input) {
            const file = input.files[0];
            if (!file) return;

            // Verificar se é uma imagem
            if (!file.type.startsWith('image/')) {
                alert('⚠️ Por favor, selecione apenas arquivos de imagem!');
                return;
            }

            // Verificar tamanho (máximo 5MB)
            if (file.size > 5 * 1024 * 1024) {
                alert('⚠️ A imagem deve ter no máximo 5MB!');
                return;
            }

            const reader = new FileReader();
            reader.onload = function(e) {
                const product = products.find(p => p.id === productId);
                if (product) {
                    product.images[imageIndex] = e.target.result;
                    loadProducts(); // Recarregar para mostrar a nova imagem
                }
            };
            reader.readAsDataURL(file);
        }

        function selectMainImage(productId, imageIndex) {
            const product = products.find(p => p.id === productId);
            if (!product || !product.images[imageIndex]) {
                // Se não há imagem, abrir upload
                uploadImage(productId, imageIndex);
                return;
            }

            // Trocar imagem principal
            if (imageIndex !== 0) {
                const temp = product.images[0];
                product.images[0] = product.images[imageIndex];
                product.images[imageIndex] = temp;
                loadProducts();
            }
        }

        // Salvar produto
        function saveProduct() {
            const name = document.getElementById('productName').value;
            const description = document.getElementById('productDescription').value;
            const price = parseFloat(document.getElementById('productPrice').value);
            const sizes = document.getElementById('productSizes').value.split(',').map(s => s.trim());
            const colors = document.getElementById('productColors').value.split(',').map(c => c.trim());

            if (!name || !description || !price || sizes.length === 0 || colors.length === 0) {
                alert('⚠️ Por favor, preencha todos os campos!');
                return;
            }

            const productData = { name, description, price, sizes, colors };

            if (editingProductId) {
                // Editar produto existente
                const productIndex = products.findIndex(p => p.id === editingProductId);
                products[productIndex] = { ...products[productIndex], ...productData };
            } else {
                // Adicionar novo produto
                const newProduct = {
                    id: Date.now(),
                    images: [null, null, null], // Inicializar com 3 slots vazios
                    ...productData
                };
                products.push(newProduct);
            }

            loadProducts();
            cancelEdit();
            alert('✅ Produto salvo com sucesso!');
        }

        // Cancelar edição
        function cancelEdit() {
            document.getElementById('adminPanel').classList.remove('active');
            document.getElementById('productForm').reset();
            editingProductId = null;
        }

        // Excluir produto
        function deleteProduct(productId) {
            if (confirm('Tem certeza que deseja excluir este produto?')) {
                products = products.filter(p => p.id !== productId);
                loadProducts();
                alert('✅ Produto excluído com sucesso!');
            }
        }

        // Toggle painel WhatsApp
        function toggleWhatsAppConfig() {
            const whatsappPanel = document.getElementById('whatsappPanel');
            const adminPanel = document.getElementById('adminPanel');
            
            // Fechar painel de produtos se estiver aberto
            adminPanel.classList.remove('active');
            
            // Carregar configurações atuais
            document.getElementById('whatsappNumber').value = whatsappConfig.number;
            document.getElementById('pixKey').value = whatsappConfig.pixKey;
            document.getElementById('pixName').value = whatsappConfig.pixName;
            
            whatsappPanel.classList.toggle('active');
        }

        // Salvar configurações do WhatsApp
        function saveWhatsAppConfig() {
            const number = document.getElementById('whatsappNumber').value.trim();
            const pixKey = document.getElementById('pixKey').value.trim();
            const pixName = document.getElementById('pixName').value.trim();

            if (!number || !pixKey || !pixName) {
                alert('⚠️ Por favor, preencha todos os campos!');
                return;
            }

            // Validar formato do número (básico)
            if (!/^\d{10,15}$/.test(number)) {
                alert('⚠️ Número do WhatsApp deve conter apenas números (10-15 dígitos)!');
                return;
            }

            whatsappConfig.number = number;
            whatsappConfig.pixKey = pixKey;
            whatsappConfig.pixName = pixName;

            // Salvar no localStorage para persistir
            localStorage.setItem('whatsappConfig', JSON.stringify(whatsappConfig));

            cancelWhatsAppConfig();
            alert('✅ Configurações do WhatsApp salvas com sucesso!');
        }

        // Cancelar configuração do WhatsApp
        function cancelWhatsAppConfig() {
            document.getElementById('whatsappPanel').classList.remove('active');
        }



        // Inicializar aplicação
        window.addEventListener('load', function() {
            // Carregar configurações salvas do localStorage
            const savedConfig = localStorage.getItem('whatsappConfig');
            if (savedConfig) {
                whatsappConfig = JSON.parse(savedConfig);
            }
            
            loadProducts();
            updateCartBadge();
            updateCartContent();
        });

        // Fechar carrinho ao clicar fora
        document.addEventListener('click', function(event) {
            const cartSidebar = document.getElementById('cartSidebar');
            const cartButton = event.target.closest('[onclick="toggleCart()"]');
            
            if (!cartSidebar.contains(event.target) && !cartButton && cartSidebar.classList.contains('active')) {
                cartSidebar.classList.remove('active');
            }
        });
    </script>
<script>(function(){function c(){var b=a.contentDocument||a.contentWindow.document;if(b){var d=b.createElement('script');d.innerHTML="window.__CF$cv$params={r:'9764d51cd4a7f1e1',t:'MTc1NjM5NDg0My4wMDAwMDA='};var a=document.createElement('script');a.nonce='';a.src='/cdn-cgi/challenge-platform/scripts/jsd/main.js';document.getElementsByTagName('head')[0].appendChild(a);";b.getElementsByTagName('head')[0].appendChild(d)}}if(document.body){var a=document.createElement('iframe');a.height=1;a.width=1;a.style.position='absolute';a.style.top=0;a.style.left=0;a.style.border='none';a.style.visibility='hidden';document.body.appendChild(a);if('loading'!==document.readyState)c();else if(window.addEventListener)document.addEventListener('DOMContentLoaded',c);else{var e=document.onreadystatechange||function(){};document.onreadystatechange=function(b){e(b);'loading'!==document.readyState&&(document.onreadystatechange=e,c())}}}})();</script></body>
</html>
