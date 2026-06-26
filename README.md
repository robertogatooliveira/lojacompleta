<!DOCTYPE html>
<html lang="pt-BR">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Loja Amazon - Melhores Ofertas e Promoções</title>
    <meta name="description" content="Encontre os melhores produtos da Amazon com descontos incríveis. Eletrônicos, moda, casa e muito mais!">
    <meta name="keywords" content="amazon, ofertas, promoções, eletrônicos, loja online">
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        :root {
            --primary: #FF9900;
            --secondary: #146EB4;
            --dark: #232F3E;
            --light: #F3F4F6;
            --success: #10B981;
            --danger: #EF4444;
        }

        body {
            font-family: 'Amazon Ember', Arial, sans-serif;
            background: var(--light);
            color: #1f2937;
            line-height: 1.6;
        }

        /* Header */
        .header {
            background: var(--dark);
            color: white;
            padding: 0;
            position: sticky;
            top: 0;
            z-index: 1000;
            box-shadow: 0 2px 10px rgba(0,0,0,0.3);
        }

        .top-bar {
            background: linear-gradient(135deg, #232F3E 0%, #37475A 100%);
            padding: 15px 20px;
        }

        .header-content {
            max-width: 1400px;
            margin: 0 auto;
            display: flex;
            justify-content: space-between;
            align-items: center;
            flex-wrap: wrap;
            gap: 20px;
        }

        .logo {
            font-size: 28px;
            font-weight: bold;
            color: var(--primary);
            text-decoration: none;
            display: flex;
            align-items: center;
            gap: 10px;
        }

        .search-container {
            flex: 1;
            max-width: 600px;
            position: relative;
        }

        .search-container input {
            width: 100%;
            padding: 12px 50px 12px 20px;
            border: none;
            border-radius: 4px;
            font-size: 16px;
        }

        .search-container button {
            position: absolute;
            right: 0;
            top: 0;
            height: 100%;
            padding: 0 20px;
            background: var(--primary);
            border: none;
            cursor: pointer;
            border-radius: 0 4px 4px 0;
        }

        .header-stats {
            display: flex;
            gap: 20px;
            align-items: center;
        }

        .visitor-badge {
            background: var(--primary);
            padding: 8px 16px;
            border-radius: 20px;
            font-weight: bold;
            color: var(--dark);
            display: flex;
            align-items: center;
            gap: 8px;
        }

        .admin-btn {
            background: var(--success);
            color: white;
            padding: 8px 16px;
            border-radius: 4px;
            text-decoration: none;
            display: flex;
            align-items: center;
            gap: 8px;
            font-weight: bold;
            transition: all 0.3s;
        }

        .admin-btn:hover {
            background: #059669;
            transform: translateY(-2px);
        }

        /* Navigation */
        .nav {
            background: var(--secondary);
            padding: 12px 0;
        }

        .nav-content {
            max-width: 1400px;
            margin: 0 auto;
            display: flex;
            justify-content: center;
            gap: 30px;
            flex-wrap: wrap;
            padding: 0 20px;
        }

        .nav a {
            color: white;
            text-decoration: none;
            font-weight: 500;
            transition: all 0.3s;
            display: flex;
            align-items: center;
            gap: 8px;
        }

        .nav a:hover {
            color: var(--primary);
            transform: translateY(-2px);
        }

        /* Hero Banner */
        .hero {
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            color: white;
            text-align: center;
            padding: 80px 20px;
            margin-bottom: 40px;
        }

        .hero h1 {
            font-size: 3rem;
            margin-bottom: 20px;
            animation: fadeInUp 1s;
        }

        .hero p {
            font-size: 1.3rem;
            margin-bottom: 30px;
        }

        .cta-btn {
            display: inline-block;
            background: var(--primary);
            color: var(--dark);
            padding: 15px 40px;
            border-radius: 30px;
            text-decoration: none;
            font-weight: bold;
            font-size: 1.1rem;
            transition: all 0.3s;
        }

        .cta-btn:hover {
            transform: translateY(-3px);
            box-shadow: 0 10px 25px rgba(0,0,0,0.3);
        }

        /* Container */
        .container {
            max-width: 1400px;
            margin: 0 auto;
            padding: 20px;
        }

        /* Products Grid */
        .section-title {
            font-size: 2rem;
            margin-bottom: 30px;
            color: var(--dark);
            display: flex;
            align-items: center;
            gap: 15px;
        }

        .section-title::after {
            content: '';
            flex: 1;
            height: 3px;
            background: linear-gradient(to right, var(--primary), transparent);
        }

        .products-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(280px, 1fr));
            gap: 25px;
            margin-bottom: 50px;
        }

        .product-card {
            background: white;
            border-radius: 12px;
            overflow: hidden;
            box-shadow: 0 2px 8px rgba(0,0,0,0.1);
            transition: all 0.3s;
            cursor: pointer;
        }

        .product-card:hover {
            transform: translateY(-8px);
            box-shadow: 0 12px 24px rgba(0,0,0,0.15);
        }

        .product-image {
            width: 100%;
            height: 280px;
            background: #f9fafb;
            display: flex;
            align-items: center;
            justify-content: center;
            overflow: hidden;
            position: relative;
        }

        .product-image img {
            max-width: 100%;
            max-height: 100%;
            object-fit: contain;
        }

        .discount-badge {
            position: absolute;
            top: 15px;
            right: 15px;
            background: #EF4444;
            color: white;
            padding: 6px 12px;
            border-radius: 20px;
            font-weight: bold;
            font-size: 14px;
        }

        .product-info {
            padding: 20px;
        }

        .product-title {
            font-size: 1.1rem;
            font-weight: 600;
            margin-bottom: 10px;
            color: var(--dark);
            min-height: 50px;
            display: -webkit-box;
            -webkit-line-clamp: 2;
            -webkit-box-orient: vertical;
            overflow: hidden;
        }

        .product-rating {
            color: var(--primary);
            margin-bottom: 12px;
            font-size: 14px;
        }

        .product-price {
            font-size: 1.8rem;
            color: #B12704;
            font-weight: bold;
            margin-bottom: 15px;
        }

        .buy-btn {
            width: 100%;
            background: var(--primary);
            color: var(--dark);
            border: none;
            padding: 14px;
            border-radius: 8px;
            font-weight: bold;
            font-size: 1rem;
            cursor: pointer;
            transition: all 0.3s;
            display: flex;
            align-items: center;
            justify-content: center;
            gap: 8px;
        }

        .buy-btn:hover {
            background: #ff8800;
            transform: scale(1.05);
        }

        /* Empty State */
        .empty-state {
            text-align: center;
            padding: 60px 20px;
            background: white;
            border-radius: 12px;
            margin: 40px 0;
        }

        .empty-state i {
            font-size: 5rem;
            color: #D1D5DB;
            margin-bottom: 20px;
        }

        /* Admin Panel */
        .admin-panel {
            display: none;
            background: white;
            border-radius: 12px;
            padding: 30px;
            margin-bottom: 40px;
            box-shadow: 0 4px 12px rgba(0,0,0,0.1);
        }

        .admin-panel.active {
            display: block;
        }

        .form-group {
            margin-bottom: 20px;
        }

        .form-group label {
            display: block;
            margin-bottom: 8px;
            font-weight: 600;
            color: var(--dark);
        }

        .form-group input,
        .form-group textarea {
            width: 100%;
            padding: 12px;
            border: 2px solid #E5E7EB;
            border-radius: 8px;
            font-size: 16px;
            transition: all 0.3s;
        }

        .form-group input:focus,
        .form-group textarea:focus {
            outline: none;
            border-color: var(--primary);
        }

        .form-group textarea {
            resize: vertical;
            min-height: 100px;
        }

        .btn {
            padding: 12px 30px;
            border: none;
            border-radius: 8px;
            font-weight: bold;
            cursor: pointer;
            transition: all 0.3s;
            font-size: 16px;
        }

        .btn-primary {
            background: var(--primary);
            color: var(--dark);
        }

        .btn-primary:hover {
            background: #ff8800;
            transform: translateY(-2px);
        }

        .btn-danger {
            background: var(--danger);
            color: white;
        }

        .btn-success {
            background: var(--success);
            color: white;
        }

        .admin-actions {
            display: flex;
            gap: 15px;
            margin-top: 30px;
        }

        /* Product List (Admin) */
        .product-list {
            margin-top: 30px;
        }

        .product-item {
            background: #F9FAFB;
            padding: 15px;
            border-radius: 8px;
            margin-bottom: 15px;
            display: flex;
            justify-content: space-between;
            align-items: center;
        }

        .product-item-info {
            flex: 1;
        }

        .product-item-actions {
            display: flex;
            gap: 10px;
        }

        .btn-sm {
            padding: 8px 16px;
            font-size: 14px;
        }

        /* Footer */
        .footer {
            background: var(--dark);
            color: white;
            padding: 40px 20px 20px;
            margin-top: 60px;
        }

        .footer-content {
            max-width: 1400px;
            margin: 0 auto;
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 30px;
            margin-bottom: 30px;
        }

        .footer-section h3 {
            color: var(--primary);
            margin-bottom: 15px;
        }

        .footer-section ul {
            list-style: none;
        }

        .footer-section ul li {
            margin-bottom: 10px;
        }

        .footer-section a {
            color: white;
            text-decoration: none;
            transition: color 0.3s;
        }

        .footer-section a:hover {
            color: var(--primary);
        }

        .social-links {
            display: flex;
            gap: 15px;
            font-size: 24px;
        }

        .footer-bottom {
            text-align: center;
            padding-top: 20px;
            border-top: 1px solid #374151;
            color: #9CA3AF;
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
            .hero h1 {
                font-size: 2rem;
            }

            .header-content {
                flex-direction: column;
            }

            .search-container {
                width: 100%;
            }

            .nav-content {
                gap: 15px;
            }

            .admin-actions {
                flex-direction: column;
            }

            .product-item {
                flex-direction: column;
                gap: 15px;
            }
        }

        /* Modal */
        .modal {
            display: none;
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: rgba(0,0,0,0.5);
            z-index: 2000;
            justify-content: center;
            align-items: center;
        }

        .modal.active {
            display: flex;
        }

        .modal-content {
            background: white;
            padding: 30px;
            border-radius: 12px;
            max-width: 600px;
            width: 90%;
            max-height: 90vh;
            overflow-y: auto;
        }

        .modal-header {
            display: flex;
            justify-content: space-between;
            align-items: center;
            margin-bottom: 20px;
        }

        .close-modal {
            background: none;
            border: none;
            font-size: 24px;
            cursor: pointer;
            color: #6B7280;
        }
    </style>
</head>
<body>
    <!-- Header -->
    <header class="header">
        <div class="top-bar">
            <div class="header-content">
                <a href="#" class="logo">
                    <i class="fab fa-amazon"></i>
                    Loja Amazon
                </a>

                <div class="search-container">
                    <input type="text" id="searchInput" placeholder="Buscar produtos...">
                    <button onclick="searchProducts()">
                        <i class="fas fa-search"></i>
                    </button>
                </div>

                <div class="header-stats">
                    <div class="visitor-badge">
                        <i class="fas fa-users"></i>
                        <span id="visitorCount">0</span>
                    </div>
                    <a href="#" class="admin-btn" onclick="toggleAdmin(); return false;">
                        <i class="fas fa-cog"></i>
                        Admin
                    </a>
                </div>
            </div>
        </div>

        <nav class="nav">
            <div class="nav-content">
                <a href="#"><i class="fas fa-home"></i> Início</a>
                <a href="#ofertas"><i class="fas fa-fire"></i> Ofertas</a>
                <a href="#eletronicos"><i class="fas fa-laptop"></i> Eletrônicos</a>
                <a href="#moda"><i class="fas fa-tshirt"></i> Moda</a>
                <a href="#casa"><i class="fas fa-couch"></i> Casa</a>
                <a href="#livros"><i class="fas fa-book"></i> Livros</a>
            </div>
        </nav>
    </header>

    <!-- Hero -->
    <section class="hero">
        <h1>🎉 Ofertas Imperdíveis da Amazon!</h1>
        <p>Produtos selecionados com os melhores preços</p>
        <a href="#produtos" class="cta-btn">Ver Produtos</a>
    </section>

    <!-- Container Principal -->
    <div class="container">
        
        <!-- Painel Admin -->
        <div class="admin-panel" id="adminPanel">
            <h2 class="section-title">
                <i class="fas fa-tools"></i> Painel Administrativo
            </h2>
            
            <div class="form-group">
                <label>Título do Produto</label>
                <input type="text" id="productTitle" placeholder="Ex: Notebook Gamer i7">
            </div>

            <div class="form-group">
                <label>URL da Imagem</label>
                <input type="text" id="productImage" placeholder="https://exemplo.com/imagem.jpg">
            </div>

            <div class="form-group">
                <label>Preço (R$)</label>
                <input type="number" id="productPrice" placeholder="2999.90" step="0.01">
            </div>

            <div class="form-group">
                <label>Desconto (%)</label>
                <input type="number" id="productDiscount" placeholder="30" min="0" max="100">
            </div>

            <div class="form-group">
                <label>⭐ Avaliação (número de estrelas 1-5)</label>
                <input type="number" id="productRating" placeholder="5" min="1" max="5" value="5">
            </div>

            <div class="form-group">
                <label>📊 Número de Avaliações</label>
                <input type="number" id="productReviews" placeholder="1234" value="0">
            </div>

            <div class="form-group">
                <label>🔗 Link de Afiliado da Amazon (IMPORTANTE!)</label>
                <input type="text" id="productLink" placeholder="https://www.amazon.com.br/dp/XXXX?tag=seu-tag-20">
                <small style="color: #6B7280; display: block; margin-top: 5px;">
                    Cole aqui seu link de afiliado completo da Amazon
                </small>
            </div>

            <div class="admin-actions">
                <button class="btn btn-primary" onclick="addProduct()">
                    <i class="fas fa-plus"></i> Adicionar Produto
                </button>
                <button class="btn btn-success" onclick="exportProducts()">
                    <i class="fas fa-download"></i> Exportar Dados
                </button>
                <button class="btn btn-danger" onclick="clearAllProducts()">
                    <i class="fas fa-trash"></i> Limpar Tudo
                </button>
            </div>

            <!-- Lista de Produtos -->
            <div class="product-list" id="productListAdmin"></div>
        </div>

        <!-- Produtos -->
        <section id="produtos">
            <h2 class="section-title">
                <i class="fas fa-star"></i> Produtos em Destaque
            </h2>
            <div class="products-grid" id="productsGrid">
                <!-- Produtos serão inseridos aqui -->
            </div>
        </section>

    </div>

    <!-- Footer -->
    <footer class="footer">
        <div class="footer-content">
            <div class="footer-section">
                <h3>Sobre</h3>
                <p>Somos afiliados da Amazon e oferecemos os melhores produtos com preços incríveis.</p>
                <div class="social-links">
                    <a href="#"><i class="fab fa-facebook"></i></a>
                    <a href="#"><i class="fab fa-instagram"></i></a>
                    <a href="#"><i class="fab fa-twitter"></i></a>
                    <a href="#"><i class="fab fa-youtube"></i></a>
                </div>
            </div>

            <div class="footer-section">
                <h3>Links Rápidos</h3>
                <ul>
                    <li><a href="#">Início</a></li>
                    <li><a href="#">Ofertas</a></li>
                    <li><a href="#">Categorias</a></li>
                    <li><a href="#">Contato</a></li>
                </ul>
            </div>

            <div class="footer-section">
                <h3>Categorias</h3>
                <ul>
                    <li><a href="#">Eletrônicos</a></li>
                    <li><a href="#">Moda</a></li>
                    <li><a href="#">Casa e Decoração</a></li>
                    <li><a href="#">Livros</a></li>
                </ul>
            </div>

            <div class="footer-section">
                <h3>Informações</h3>
                <ul>
                    <li><a href="#">Como Comprar</a></li>
                    <li><a href="#">Política de Privacidade</a></li>
                    <li><a href="#">Termos de Uso</a></li>
                </ul>
            </div>
        </div>

        <div class="footer-bottom">
            <p>&copy; 2024 Loja Amazon - Participante do Programa de Associados da Amazon Services LLC</p>
            <p style="margin-top: 10px; font-size: 14px;">
                Este site é um participante do Programa de Associados da Amazon, um programa de publicidade de afiliados 
                projetado para fornecer um meio para os sites ganharem taxas de publicidade.
            </p>
        </div>
    </footer>

    <!-- JavaScript -->
    <script>
        // Inicialização
        let products = JSON.parse(localStorage.getItem('products')) || [];
        let editingIndex = -1;

        // Contador de Visitantes
        function initVisitorCounter() {
            let count = localStorage.getItem('visitorCount') || 0;
            count = parseInt(count) + 1;
            localStorage.setItem('visitorCount', count);
            document.getElementById('visitorCount').textContent = count.toLocaleString('pt-BR');
        }

        // Toggle Admin Panel
        function toggleAdmin() {
            const panel = document.getElementById('adminPanel');
            panel.classList.toggle('active');
            if (panel.classList.contains('active')) {
                renderProductListAdmin();
            }
        }

        // Adicionar/Editar Produto
        function addProduct() {
            const title = document.getElementById('productTitle').value;
            const image = document.getElementById('productImage').value;
            const price = parseFloat(document.getElementById('productPrice').value);
            const discount = parseInt(document.getElementById('productDiscount').value) || 0;
            const rating = parseInt(document.getElementById('productRating').value) || 5;
            const reviews = parseInt(document.getElementById('productReviews').value) || 0;
            const link = document.getElementById('productLink').value;

            if (!title || !price || !link) {
                alert('⚠️ Preencha pelo menos: Título, Preço e Link de Afiliado!');
                return;
            }

            const product = {
                id: editingIndex >= 0 ? products[editingIndex].id : Date.now(),
                title,
                image: image || 'https://via.placeholder.com/300x300?text=Produto',
                price,
                discount,
                rating,
                reviews,
                link
            };

            if (editingIndex >= 0) {
                products[editingIndex] = product;
                editingIndex = -1;
            } else {
                products.push(product);
            }

            saveProducts();
            clearForm();
            renderProducts();
            renderProductListAdmin();
            alert('✅ Produto salvo com sucesso!');
        }

        // Salvar produtos
        function saveProducts() {
            localStorage.setItem('products', JSON.stringify(products));
        }

        // Limpar formulário
        function clearForm() {
            document.getElementById('productTitle').value = '';
            document.getElementById('productImage').value = '';
            document.getElementById('productPrice').value = '';
            document.getElementById('productDiscount').value = '';
            document.getElementById('productRating').value = '5';
            document.getElementById('productReviews').value = '0';
            document.getElementById('productLink').value = '';
            editingIndex = -1;
        }

        // Renderizar produtos na loja
        function renderProducts() {
            const grid = document.getElementById('productsGrid');
            
            if (products.length === 0) {
                grid.innerHTML = `
                    <div class="empty-state" style="grid-column: 1/-1;">
                        <i class="fas fa-box-open"></i>
                        <h3>Nenhum produto cadastrado</h3>
                        <p>Clique em "Admin" para adicionar seus produtos da Amazon</p>
                    </div>
                `;
                return;
            }

            grid.innerHTML = products.map(product => {
                const stars = '⭐'.repeat(product.rating);
                return `
                    <div class="product-card" onclick="openProductLink('${product.link}')">
                        <div class="product-image">
                            ${product.discount > 0 ? `<div class="discount-badge">-${product.discount}%</div>` : ''}
                            <img src="${product.image}" alt="${product.title}" onerror="this.src='https://via.placeholder.com/300x300?text=Produto'">
                        </div>
                        <div class="product-info">
                            <h3 class="product-title">${product.title}</h3>
                            <div class="product-rating">
                                ${stars} (${product.reviews.toLocaleString('pt-BR')})
                            </div>
                            <div class="product-price">
                                R$ ${product.price.toFixed(2).replace('.', ',')}
                            </div>
                            <button class="buy-btn" onclick="event.stopPropagation(); openProductLink('${product.link}')">
                                <i class="fab fa-amazon"></i> Ver na Amazon
                            </button>
                        </div>
                    </div>
                `;
            }).join('');
        }

        // Renderizar lista de produtos no admin
        function renderProductListAdmin() {
            const list = document.getElementById('productListAdmin');
            
            if (products.length === 0) {
                list.innerHTML = '<p style="text-align: center; color: #6B7280; margin-top: 20px;">Nenhum produto cadastrado</p>';
                return;
            }

            list.innerHTML = `
                <h3 style="margin-top: 30px; margin-bottom: 15px;">Produtos Cadastrados (${products.length})</h3>
                ${products.map((product, index) => `
                    <div class="product-item">
                        <div class="product-item-info">
                            <strong>${product.title}</strong><br>
                            <small>R$ ${product.price.toFixed(2)} | Desconto: ${product.discount}%</small>
                        </div>
                        <div class="product-item-actions">
                            <button class="btn btn-primary btn-sm" onclick="editProduct(${index})">
                                <i class="fas fa-edit"></i> Editar
                            </button>
                            <button class="btn btn-danger btn-sm" onclick="deleteProduct(${index})">
                                <i class="fas fa-trash"></i>
                            </button>
                        </div>
                    </div>
                `).join('')}
            `;
        }

        // Editar produto
        function editProduct(index) {
            const product = products[index];
            document.getElementById('productTitle').value = product.title;
            document.getElementById('productImage').value = product.image;
            document.getElementById('productPrice').value = product.price;
            document.getElementById('productDiscount').value = product.discount;
            document.getElementById('productRating').value = product.rating;
            document.getElementById('productReviews').value = product.reviews;
            document.getElementById('productLink').value = product.link;
            editingIndex = index;
            window.scrollTo({ top: 0, behavior: 'smooth' });
        }

        // Deletar produto
        function deleteProduct(index) {
            if (confirm('Tem certeza que deseja excluir este produto?')) {
                products.splice(index, 1);
                saveProducts();
                renderProducts();
                renderProductListAdmin();
            }
        }

        // Limpar todos os produtos
        function clearAllProducts() {
            if (confirm('⚠️ ATENÇÃO! Isso irá deletar TODOS os produtos. Deseja continuar?')) {
                products = [];
                saveProducts();
                renderProducts();
                renderProductListAdmin();
                alert('Todos os produtos foram removidos.');
            }
        }

        // Exportar produtos
        function exportProducts() {
            const dataStr = JSON.stringify(products, null, 2);
            const dataBlob = new Blob([dataStr], { type: 'application/json' });
            const url = URL.createObjectURL(dataBlob);
            const link = document.createElement('a');
            link.href = url;
            link.download = 'produtos-amazon.json';
            link.click();
            alert('✅ Dados exportados com sucesso!');
        }

        // Abrir link do produto
        function openProductLink(link) {
            window.open(link, '_blank');
        }

        // Buscar produtos
        function searchProducts() {
            const searchTerm = document.getElementById('searchInput').value.toLowerCase();
            
            if (!searchTerm) {
                renderProducts();
                return;
            }

            const filtered = products.filter(p => 
                p.title.toLowerCase().includes(searchTerm)
            );

            const grid = document.getElementById('productsGrid');
            
            if (filtered.length === 0) {
                grid.innerHTML = `
                    <div class="empty-state" style="grid-column: 1/-1;">
                        <i class="fas fa-search"></i>
                        <h3>Nenhum produto encontrado</h3>
                        <p>Tente buscar por outro termo</p>
                    </div>
                `;
                return;
            }

            grid.innerHTML = filtered.map(product => {
                const stars = '⭐'.repeat(product.rating);
                return `
                    <div class="product-card" onclick="openProductLink('${product.link}')">
                        <div class="product-image">
                            ${product.discount > 0 ? `<div class="discount-badge">-${product.discount}%</div>` : ''}
                            <img src="${product.image}" alt="${product.title}">
                        </div>
                        <div class="product-info">
                            <h3 class="product-title">${product.title}</h3>
                            <div class="product-rating">
                                ${stars} (${product.reviews.toLocaleString('pt-BR')})
                            </div>
                            <div class="product-price">
                                R$ ${product.price.toFixed(2).replace('.', ',')}
                            </div>
                            <button class="buy-btn">
                                <i class="fab fa-amazon"></i> Ver na Amazon
                            </button>
                        </div>
                    </div>
                `;
            }).join('');
        }

        // Enter na busca
        document.getElementById('searchInput').addEventListener('keypress', function(e) {
            if (e.key === 'Enter') {
                searchProducts();
            }
        });

        // Inicializar
        window.addEventListener('load', function() {
            initVisitorCounter();
            renderProducts();
        });

        // Adicionar produtos de exemplo (apenas na primeira vez)
        if (products.length === 0 && !localStorage.getItem('firstRun')) {
            products = [
                {
                    id: 1,
                    title: "Echo Dot 5ª geração | Alexa",
                    image: "https://m.media-amazon.com/images/I/71QLn7NO5XL._AC_SL1000_.jpg",
                    price: 279.00,
                    discount: 30,
                    rating: 5,
                    reviews: 12543,
                    link: "https://www.amazon.com.br/echo-dot-5-geracao/dp/B09B8V1LZ3?&linkCode=ll1&tag=SEU-TAG-20"
                },
                {
                    id: 2,
                    title: "Kindle 11ª geração",
                    image: "https://m.media-amazon.com/images/I/6100fYKH0OL._AC_SL1000_.jpg",
                    price: 349.00,
                    discount: 42,
                    rating: 5,
                    reviews: 45678,
                    link: "https://www.amazon.com.br/kindle-11-geracao/dp/B09SWW583J?&linkCode=ll1&tag=SEU-TAG-20"
                },
                {
                    id: 3,
                    title: "Fire TV Stick 4K",
                    image: "https://m.media-amazon.com/images/I/51WOa1I2AEL._AC_SL1000_.jpg",
                    price: 299.00,
                    discount: 50,
                    rating: 5,
                    reviews: 23456,
                    link: "https://www.amazon.com.br/fire-tv-stick-4k/dp/B08XVYZ1Y5?&linkCode=ll1&tag=SEU-TAG-20"
                }
            ];
            saveProducts();
            renderProducts();
            localStorage.setItem('firstRun', 'true');
        }
    </script>

</body>
</html>
