<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Dope Gem Coffee</title>
    <link href="https://fonts.googleapis.com/css2?family=Roboto:wght@400;700&display=swap" rel="stylesheet">
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Roboto', sans-serif;
        }

        body {
            background-image: url('https://images.unsplash.com/photo-1507525428034-b723cf961d3e?ixlib=rb-4.0.3&auto=format&fit=crop&w=1350&q=80');
            background-size: cover;
            background-attachment: fixed;
            color: #3c2f2f;
            transition: background-color 0.3s, color 0.3s;
        }

        body.dark-mode {
            background-color: #2c1e1e;
            color: #f5f5f5;
        }

        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 20px;
        }

        .menu {
            position: fixed;
            top: 20px;
            left: 20px;
            cursor: pointer;
            z-index: 1000;
        }

        .menu div {
            width: 30px;
            height: 4px;
            background-color: #3c2f2f;
            margin: 6px 0;
            transition: background-color 0.3s;
        }

        body.dark-mode .menu div {
            background-color: #f5f5f5;
        }

        .nav {
            display: none;
            position: fixed;
            top: 60px;
            left: 20px;
            background-color: #fff;
            padding: 20px;
            border-radius: 5px;
            box-shadow: 0 2px 5px rgba(0, 0, 0, 0.2);
            transition: background-color 0.3s;
        }

        body.dark-mode .nav {
            background-color: #3c2f2f;
        }

        .nav a {
            display: block;
            color: #3c2f2f;
            text-decoration: none;
            margin: 10px 0;
            font-size: 18px;
        }

        body.dark-mode .nav a {
            color: #f5f5f5;
        }

        .nav a:hover {
            color: #8b5e3c;
        }

        .page {
            display: none;
            text-align: center;
            padding: 50px 20px;
        }

        .page.active {
            display: block;
        }

        .home .logo {
            max-width: 200px;
            margin: 20px auto;
        }

        h1, h2 {
            color: #8b5e3c;
        }

        body.dark-mode h1, body.dark-mode h2 {
            color: #e6d5b8;
        }

        .order-form {
            background-color: rgba(255, 255, 255, 0.9);
            padding: 20px;
            border-radius: 10px;
            max-width: 500px;
            margin: 20px auto;
            transition: background-color 0.3s;
        }

        body.dark-mode .order-form {
            background-color: rgba(60, 47, 47, 0.9);
        }

        .order-form input, .order-form select {
            width: 100%;
            padding: 10px;
            margin: 10px 0;
            border: 1px solid #8b5e3c;
            border-radius: 5px;
            font-size: 16px;
        }

        .order-form button {
            background-color: #8b5e3c;
            color: #fff;
            border: none;
            padding: 10px 20px;
            border-radius: 5px;
            cursor: pointer;
            font-size: 16px;
        }

        .order-form button:hover {
            background-color: #6b4e31;
        }

        .footer {
            text-align: center;
            padding: 20px;
            background-color: rgba(255, 255, 255, 0.9);
            transition: background-color 0.3s;
        }

        body.dark-mode .footer {
            background-color: rgba(60, 47, 47, 0.9);
        }

        .footer a {
            color: #8b5e3c;
            text-decoration: none;
        }

        body.dark-mode .footer a {
            color: #e6d5b8;
        }

        .mode-toggle {
            position: fixed;
            top: 20px;
            right: 20px;
            background-color: #8b5e3c;
            color: #fff;
            border: none;
            padding: 10px;
            border-radius: 5px;
            cursor: pointer;
        }
    </style>
</head>
<body>
    <div class="menu" onclick="toggleNav()">
        <div></div>
        <div></div>
        <div></div>
    </div>
    <div class="nav" id="nav">
        <a href="#" onclick="showPage('home')">Home</a>
        <a href="#" onclick="showPage('about')">About</a>
        <a href="#" onclick="showPage('contact')">Contact</a>
    </div>

    <div class="page active" id="home">
        <div class="container">
            <img src="https://via.placeholder.com/200?text=Starbucks+Inspired+Logo" alt="Dope Gem Coffee Logo" class="logo">
            <h1>Welcome to Dope Gem Coffee</h1>
            <div class="order-form">
                <h2>Place Your Order</h2>
                <input type="text" id="name" placeholder="Your Name" required>
                <input type="tel" id="phone" placeholder="Phone (+254)" pattern="\+254[0-9]{9}" required>
                <select id="coffee" required>
                    <option value="" disabled selected>Select Coffee</option>
                    <option value="latte">Latte</option>
                    <option value="espresso">Espresso</option>
                    <option value="cappuccino">Cappuccino</option>
                </select>
                <input type="number" id="amount" placeholder="Amount (Min KES 50)" min="50" required>
                <select id="payment" required>
                    <option value="" disabled selected>Payment Method</option>
                    <option value="mpesa">M-Pesa</option>
                    <option value="paypal">PayPal</option>
                    <option value="stripe">Stripe</option>
                </select>
                <button onclick="placeOrder()">Place Order</button>
            </div>
        </div>
        <div class="footer">
            <a href="https://instagram.com/dic3.y_zsn" target="_blank">Follow us on Instagram: dic3.y_zsn</a>
        </div>
    </div>

    <div class="page" id="about">
        <div class="container">
            <h1>About Us</h1>
            <p>Order fine coffee (dope/gem) through us</p>
        </div>
    </div>

    <div class="page" id="contact">
        <div class="container">
            <h1>Contact Us</h1>
            <p>Email: <a href="mailto:hopeeugine47@gmail.com">hopeeugine47@gmail.com</a></p>
        </div>
    </div>

    <button class="mode-toggle" onclick="toggleMode()">Toggle Dark/Light Mode</button>

    <script>
        function toggleNav() {
            const nav = document.getElementById('nav');
            nav.style.display = nav.style.display === 'block' ? 'none' : 'block';
        }

        function showPage(pageId) {
            document.querySelectorAll('.page').forEach(page => page.classList.remove('active'));
            document.getElementById(pageId).classList.add('active');
            document.getElementById('nav').style.display = 'none';
        }

        function toggleMode() {
            document.body.classList.toggle('dark-mode');
        }

        function placeOrder() {
            const name = document.getElementById('name').value;
            const phone = document.getElementById('phone').value;
            const coffee = document.getElementById('coffee').value;
            const amount = document.getElementById('amount').value;
            const payment = document.getElementById('payment').value;

            if (!name || !phone || !coffee || !amount || !payment) {
                alert('Please fill in all fields');
                return;
            }

            if (!phone.match(/\+254[0-9]{9}/)) {
                alert('Phone number must start with +254 and be followed by 9 digits');
                return;
            }

            if (amount < 50) {
                alert('Minimum amount is KES 50');
                return;
            }

            // Simulate payment processing (replace with actual payment gateway integration)
            alert(`Order placed!\nName: ${name}\nPhone: ${phone}\nCoffee: ${coffee}\nAmount: KES ${amount}\nPayment: ${payment}`);
            // For M-Pesa, PayPal, or Stripe, integrate their APIs here
            // M-Pesa payments would be sent to the registered number (not shown in UI)
        }
    </script>
</body>
</html>
