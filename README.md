# homepage-design
Converting Figma Design to HTML UsingTailwind CS
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Arslan Ash E-Shop</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <script src="https://cdn.jsdelivr.net/npm/alpinejs@2.8.2/dist/alpine.min.js" defer></script>
    <style>
        .card {
            transition: transform 0.3s ease, box-shadow 0.3s ease;
        }

        .card:hover {
            transform: translateY(-10px);
            box-shadow: 0 15px 25px rgba(0, 0, 0, 0.1);
        }

        .product-image {
            transition: transform 0.3s ease;
        }

        .card:hover .product-image {
            transform: scale(1.05);
        }

        .tab-content {
            display: none;
        }

        .tab-content.active {
            display: block;
        }

        .tab {
            cursor: pointer;
        }

        .tab:hover {
            background-color: rgba(59, 130, 246, 0.1);
        }

        .tabs-container {
            display: flex;
            justify-content: space-around;
            margin-top: 2rem;
            margin-bottom: 2rem;
        }

        .category-menu {
            display: flex;
            justify-content: center;
            gap: 1rem;
            margin-bottom: 3rem;
        }

        .category-menu a {
            background-color: #4f46e5;
            padding: 10px 20px;
            text-white;
            border-radius: 5px;
            cursor: pointer;
        }

        .category-menu a:hover {
            background-color: #6366f1;
        }
    </style>
</head>

<body class="bg-gray-100 font-sans">

    <!-- Company Introduction -->
    <section class="bg-gradient-to-r from-blue-500 to-indigo-600 text-white py-10">
        <div class="container mx-auto text-center">
            <h1 class="text-5xl font-bold">Welcome to Arslan Ash E-Shop</h1>
            <p class="mt-4 text-xl">Discover quality products at affordable prices. Shop with us now!</p>
        </div>
    </section>

    <!-- Header -->
    <header class="bg-blue-600 text-white py-4 shadow-md">
        <div class="container mx-auto flex justify-between items-center">
            <div class="text-3xl font-bold">Arslan Ash E-Shop</div>
            <nav class="space-x-6">
                <a href="#home" class="hover:text-gray-200">Home</a>
                <a href="#products" class="hover:text-gray-200">Shop</a>
                <a href="#contact" class="hover:text-gray-200">Contact</a>
            </nav>
        </div>
    </header>

    <!-- Category Menu (Home, Women, Men, etc.) -->
    <section id="categories" class="container mx-auto py-10">
        <div class="category-menu">
            <a href="#home-products">Home</a>
            <a href="#women-products">Women</a>
            <a href="#men-products">Men</a>
            <a href="#accessories-products">Accessories</a>
            <a href="#electronics-products">Electronics</a>
            <a href="#sale-products">Sale</a>
        </div>
    </section>

    <!-- Product Tabs Section -->
    <section id="products" class="container mx-auto py-10 px-5">
        <h2 class="text-3xl font-bold text-center mb-10">Shop Our Products</h2>

        <!-- Tab Navigation -->
        <div class="tabs-container">
            <div x-data="{ selectedTab: 1 }">
                <div class="flex space-x-6">
                    <button :class="selectedTab === 1 ? 'bg-blue-600 text-white' : 'bg-gray-200 text-black'"
                        @click="selectedTab = 1" class="tab px-4 py-2 rounded-lg font-semibold">Home Products</button>
                    <button :class="selectedTab === 2 ? 'bg-blue-600 text-white' : 'bg-gray-200 text-black'"
                        @click="selectedTab = 2" class="tab px-4 py-2 rounded-lg font-semibold">Women Products</button>
                    <button :class="selectedTab === 3 ? 'bg-blue-600 text-white' : 'bg-gray-200 text-black'"
                        @click="selectedTab = 3" class="tab px-4 py-2 rounded-lg font-semibold">Men Products</button>
                    <button :class="selectedTab === 4 ? 'bg-blue-600 text-white' : 'bg-gray-200 text-black'"
                        @click="selectedTab = 4" class="tab px-4 py-2 rounded-lg font-semibold">Accessories</button>
                    <button :class="selectedTab === 5 ? 'bg-blue-600 text-white' : 'bg-gray-200 text-black'"
                        @click="selectedTab = 5" class="tab px-4 py-2 rounded-lg font-semibold">Electronics</button>
                    <button :class="selectedTab === 6 ? 'bg-blue-600 text-white' : 'bg-gray-200 text-black'"
                        @click="selectedTab = 6" class="tab px-4 py-2 rounded-lg font-semibold">Sale</button>
                </div>

                <!-- Tab Content -->
                <div x-show="selectedTab === 1" class="tab-content active">
                    <div class="grid grid-cols-1 sm:grid-cols-2 md:grid-cols-3 lg:grid-cols-3 gap-10 mt-6">
                        <div class="card bg-white p-5 rounded-lg shadow-lg hover:shadow-2xl">
                            <img src="a.jpg" alt="Product 1"
                                class="product-image w-full h-48 object-cover rounded-md mb-4">
                            <h3 class="text-xl font-semibold mb-2">Home Product 1</h3>
                            <p class="text-gray-500 mb-4">Stylish home decoration piece.</p>
                            <span class="text-lg font-semibold">$30.99</span>
                        </div>
                        <div class="card bg-white p-5 rounded-lg shadow-lg hover:shadow-2xl">
                            <img src="b.jpg" alt="Product 2"
                                class="product-image w-full h-48 object-cover rounded-md mb-4">
                            <h3 class="text-xl font-semibold mb-2">Home Product 2</h3>
                            <p class="text-gray-500 mb-4">Comfy sofa for your living room.</p>
                            <span class="text-lg font-semibold">$150.99</span>
                        </div>
                        <div class="card bg-white p-5 rounded-lg shadow-lg hover:shadow-2xl">
                            <img src="c.jpg" alt="Product 3"
                                class="product-image w-full h-48 object-cover rounded-md mb-4">
                            <h3 class="text-xl font-semibold mb-2">Home Product 3</h3>
                            <p class="text-gray-500 mb-4">Modern coffee table to complement your living space.</p>
                            <span class="text-lg font-semibold">$120.99</span>
                        </div>
                    </div>
                </div>
                <div x-show="selectedTab === 2" class="tab-content">
                    <div class="grid grid-cols-1 sm:grid-cols-2 md:grid-cols-3 lg:grid-cols-3 gap-10 mt-6">
                        <div class="card bg-white p-5 rounded-lg shadow-lg hover:shadow-2xl">
                            <img src="https://via.placeholder.com/300" alt="Product 1"
                                class="product-image w-full h-48 object-cover rounded-md mb-4">
                            <h3 class="text-xl font-semibold mb-2">Women Product 1</h3>
                            <p class="text-gray-500 mb-4">Trendy dress for any occasion.</p>
                            <span class="text-lg font-semibold">$50.99</span>
                        </div>
                        <div class="card bg-white p-5 rounded-lg shadow-lg hover:shadow-2xl">
                            <img src="https://via.placeholder.com/300" alt="Product 2"
                                class="product-image w-full h-48 object-cover rounded-md mb-4">
                            <h3 class="text-xl font-semibold mb-2">Women Product 2</h3>
                            <p class="text-gray-500 mb-4">Beautiful pair of earrings.</p>
                            <span class="text-lg font-semibold">$15.99</span>
                        </div>
                        <div class="card bg-white p-5 rounded-lg shadow-lg hover:shadow-2xl">
                            <img src="https://via.placeholder.com/300" alt="Product 3"
                                class="product-image w-full h-48 object-cover rounded-md mb-4">
                            <h3 class="text-xl font-semibold mb-2">Women Product 3</h3>
                            <p class="text-gray-500 mb-4">Stylish handbag to complement your outfit.</p>
                            <span class="text-lg font-semibold">$35.99</span>
                        </div>
                    </div>
                </div>
                <div x-show="selectedTab === 3" class="tab-content">
                    <div class="grid grid-cols-1 sm:grid-cols-2 md:grid-cols-3 lg:grid-cols-3 gap-10 mt-6">
                        <div class="card bg-white p-5 rounded-lg shadow-lg hover:shadow-2xl">
                            <img src="https://via.placeholder.com/300" alt="Product 1"
                                class="product-image w-full h-48 object-cover rounded-md mb-4">
                            <h3 class="text-xl font-semibold mb-2">Men Product 1</h3>
                            <p class="text-gray-500 mb-4">Cool leather jacket for every season.</p>
                            <span class="text-lg font-semibold">$80.99</span>
                        </div>
                        <div class="card bg-white p-5 rounded-lg shadow-lg hover:shadow-2xl">
                            <img src="https://via.placeholder.com/300" alt="Product 2"
                                class="product-image w-full h-48 object-cover rounded-md mb-4">
                            <h3 class="text-xl font-semibold mb-2">Men Product 2</h3>
                            <p class="text-gray-500 mb-4">Casual shoes for everyday use.</p>
                            <span class="text-lg font-semibold">$40.99</span>
                        </div>
                        <div class="card bg-white p-5 rounded-lg shadow-lg hover:shadow-2xl">
                            <img src="https://via.placeholder.com/300" alt="Product 3"
                                class="product-image w-full h-48 object-cover rounded-md mb-4">
                            <h3 class="text-xl font-semibold mb-2">Men Product 3</h3>
                            <p class="text-gray-500 mb-4">Classic wristwatch for any occasion.</p>
                            <span class="text-lg font-semibold">$55.99</span>
                        </div>
                    </div>
                </div>
                <div x-show="selectedTab === 4" class="tab-content">
                    <div class="grid grid-cols-1 sm:grid-cols-2 md:grid-cols-3 lg:grid-cols-3 gap-10 mt-6">
                        <div class="card bg-white p-5 rounded-lg shadow-lg hover:shadow-2xl">
                            <img src="https://via.placeholder.com/300" alt="Product 1"
                                class="product-image w-full h-48 object-cover rounded-md mb-4">
                            <h3 class="text-xl font-semibold mb-2">Accessories Product 1</h3>
                            <p class="text-gray-500 mb-4">Stylish sunglasses for the summer.</p>
                            <span class="text-lg font-semibold">$25.99</span>
                        </div>
                        <div class="card bg-white p-5 rounded-lg shadow-lg hover:shadow-2xl">
                            <img src="https://via.placeholder.com/300" alt="Product 2"
                                class="product-image w-full h-48 object-cover rounded-md mb-4">
                            <h3 class="text-xl font-semibold mb-2">Accessories Product 2</h3>
                            <p class="text-gray-500 mb-4">High-quality watch strap.</p>
                            <span class="text-lg font-semibold">$15.99</span>
                        </div>
                        <div class="card bg-white p-5 rounded-lg shadow-lg hover:shadow-2xl">
                            <img src="https://via.placeholder.com/300" alt="Product 3"
                                class="product-image w-full h-48 object-cover rounded-md mb-4">
                            <h3 class="text-xl font-semibold mb-2">Accessories Product 3</h3>
                            <p class="text-gray-500 mb-4">Portable wireless charger for your phone.</p>
                            <span class="text-lg font-semibold">$40.99</span>
                        </div>
                    </div>
                </div>
                <div x-show="selectedTab === 5" class="tab-content">
                    <div class="grid grid-cols-1 sm:grid-cols-2 md:grid-cols-3 lg:grid-cols-3 gap-10 mt-6">
                        <div class="card bg-white p-5 rounded-lg shadow-lg hover:shadow-2xl">
                            <img src="https://via.placeholder.com/300" alt="Product 1"
                                class="product-image w-full h-48 object-cover rounded-md mb-4">
                            <h3 class="text-xl font-semibold mb-2">Electronics Product 1</h3>
                            <p class="text-gray-500 mb-4">Smartphone with latest features.</p>
                            <span class="text-lg font-semibold">$499.99</span>
                        </div>
                        <div class="card bg-white p-5 rounded-lg shadow-lg hover:shadow-2xl">
                            <img src="https://via.placeholder.com/300" alt="Product 2"
                                class="product-image w-full h-48 object-cover rounded-md mb-4">
                            <h3 class="text-xl font-semibold mb-2">Electronics Product 2</h3>
                            <p class="text-gray-500 mb-4">Noise-cancelling headphones.</p>
                            <span class="text-lg font-semibold">$89.99</span>
                        </div>
                        <div class="card bg-white p-5 rounded-lg shadow-lg hover:shadow-2xl">
                            <img src="https://via.placeholder.com/300" alt="Product 3"
                                class="product-image w-full h-48 object-cover rounded-md mb-4">
                            <h3 class="text-xl font-semibold mb-2">Electronics Product 3</h3>
                            <p class="text-gray-500 mb-4">Smartwatch with fitness tracking.</p>
                            <span class="text-lg font-semibold">$149.99</span>
                        </div>
                    </div>
                </div>
                <div x-show="selectedTab === 6" class="tab-content">
                    <div class="grid grid-cols-1 sm:grid-cols-2 md:grid-cols-3 lg:grid-cols-3 gap-10 mt-6">
                        <div class="card bg-white p-5 rounded-lg shadow-lg hover:shadow-2xl">
                            <img src="https://via.placeholder.com/300" alt="Product 1"
                                class="product-image w-full h-48 object-cover rounded-md mb-4">
                            <h3 class="text-xl font-semibold mb-2">Sale Product 1</h3>
                            <p class="text-gray-500 mb-4">Get 50% off on this amazing product.</p>
                            <span class="text-lg font-semibold">$45.99</span>
                        </div>
                        <div class="card bg-white p-5 rounded-lg shadow-lg hover:shadow-2xl">
                            <img src="https://via.placeholder.com/300" alt="Product 2"
                                class="product-image w-full h-48 object-cover rounded-md mb-4">
                            <h3 class="text-xl font-semibold mb-2">Sale Product 2</h3>
                            <p class="text-gray-500 mb-4">Special offer on this gadget.</p>
                            <span class="text-lg font-semibold">$39.99</span>
                        </div>
                        <div class="card bg-white p-5 rounded-lg shadow-lg hover:shadow-2xl">
                            <img src="https://via.placeholder.com/300" alt="Product 3"
                                class="product-image w-full h-48 object-cover rounded-md mb-4">
                            <h3 class="text-xl font-semibold mb-2">Sale Product 3</h3>
                            <p class="text-gray-500 mb-4">Limited time offer: 30% off!</p>
                            <span class="text-lg font-semibold">$69.99</span>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Footer -->
    <footer class="bg-blue-600 text-white py-6 mt-10">
        <div class="container mx-auto text-center">
            <p>&copy; 2024 Arslan Ash E-Shop. All Rights Reserved.</p>
        </div>
    </footer>

</body>

</html>
