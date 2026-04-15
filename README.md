<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>For Silavm 💖</title>
    <style>
        @import url('https://fonts.googleapis.com/css2?family=Dancing+Script:wght@600&family=Poppins:wght@300;400&display=swap');

        * {
            box-sizing: border-box;
            margin: 0;
            padding: 0;
        }

        body {
            font-family: 'Poppins', sans-serif;
            background-color: #ffe6ea;
            /* Beautiful white and pink lilies background from Unsplash */
            background-image: linear-gradient(rgba(255, 255, 255, 0.5), rgba(255, 255, 255, 0.5)), url('https://images.unsplash.com/photo-1593005510509-d05b264f1c9c?q=80&w=2070&auto=format&fit=crop');
            background-size: cover;
            background-position: center;
            background-attachment: fixed;
            height: 100vh;
            overflow: hidden;
            display: flex;
            justify-content: center;
            align-items: center;
        }

        /* --- Welcome Screen --- */
        #welcome-screen {
            text-align: center;
            background: rgba(255, 255, 255, 0.85);
            padding: 40px;
            border-radius: 20px;
            box-shadow: 0 10px 30px rgba(0,0,0,0.1);
            cursor: pointer;
            transition: transform 0.3s ease, opacity 0.5s ease;
            backdrop-filter: blur(5px);
        }

        #welcome-screen:hover {
            transform: scale(1.05);
        }

        #welcome-screen h1 {
            font-family: 'Dancing Script', cursive;
            color: #d81b60;
            font-size: 3.5rem;
            margin-bottom: 10px;
        }

        #welcome-screen p {
            color: #666;
            font-size: 1.1rem;
            animation: pulse 2s infinite;
        }

        /* --- Lily Garden Screen --- */
        #garden-screen {
            display: none;
            width: 100%;
            height: 100%;
            padding: 20px;
            overflow-y: auto;
        }

        .garden-container {
            display: flex;
            flex-wrap: wrap;
            justify-content: center;
            gap: 30px;
            max-width: 900px;
            margin: 50px auto;
        }

        .lily {
            width: 120px;
            height: 120px;
            background-image: url('https://cdn-icons-png.flaticon.com/512/862/862080.png'); /* Lily Icon */
            background-size: contain;
            background-repeat: no-repeat;
            background-position: center;
            cursor: pointer;
            transition: transform 0.3s ease, filter 0.3s ease;
            filter: drop-shadow(0 5px 10px rgba(216, 27, 96, 0.3));
            animation: float 4s ease-in-out infinite;
        }

        .lily:hover {
            transform: scale(1.2) rotate(5deg);
            filter: drop-shadow(0 8px 15px rgba(216, 27, 96, 0.5));
        }

        /* Stagger the floating animation for a natural look */
        .lily:nth-child(2) { animation-delay: 0.5s; }
        .lily:nth-child(3) { animation-delay: 1s; }
        .lily:nth-child(4) { animation-delay: 1.5s; }
        .lily:nth-child(5) { animation-delay: 2s; }
        .lily:nth-child(6) { animation-delay: 2.5s; }

        /* --- Hidden Message Modal --- */
        #modal {
            display: none;
            position: fixed;
            top: 0; left: 0; width: 100%; height: 100%;
            background: rgba(0, 0, 0, 0.6);
            backdrop-filter: blur(4px);
            justify-content: center;
            align-items: center;
            z-index: 1000;
            opacity: 0;
            transition: opacity 0.4s ease;
        }

        .modal-content {
            background: white;
            padding: 40px;
            border-radius: 20px;
            text-align: center;
            max-width: 80%;
            width: 400px;
            box-shadow: 0 15px 40px rgba(0,0,0,0.2);
            transform: translateY(20px);
            transition: transform 0.4s ease;
            border: 2px solid #ffe6ea;
        }

        .modal-content p {
            font-family: 'Dancing Script', cursive;
            font-size: 2.5rem;
            color: #c2185b;
            margin-bottom: 20px;
            line-height: 1.3;
        }

        .close-btn {
            background: #d81b60;
            color: white;
            border: none;
            padding: 10px 25px;
            font-size: 1rem;
            border-radius: 30px;
            cursor: pointer;
            font-family: 'Poppins', sans-serif;
            transition: background 0.3s ease;
        }

        .close-btn:hover {
            background: #ad144d;
        }

        /* --- Animations --- */
        @keyframes pulse {
            0% { transform: scale(1); opacity: 0.8; }
            50% { transform: scale(1.05); opacity: 1; }
            100% { transform: scale(1); opacity: 0.8; }
        }

        @keyframes float {
            0% { transform: translateY(0px); }
            50% { transform: translateY(-15px); }
            100% { transform: translateY(0px); }
        }

        /* --- Mobile Responsiveness --- */
        @media (max-width: 600px) {
            #welcome-screen h1 { font-size: 2.8rem; }
            .lily { width: 90px; height: 90px; }
            .modal-content p { font-size: 2rem; }
        }
    </style>
</head>
<body>

    <div id="welcome-screen" onclick="enterGarden()">
        <h1>Hey Silavm , <br>click on this 💖</h1>
        <p>(Tap to open)</p>
    </div>

    <div id="garden-screen">
        <div class="garden-container">
            <div class="lily" data-message="Love you gyanakam ❤️" onclick="showMessage(this)"></div>
            <div class="lily" data-message="Az guri te bm jwankilakam ✨" onclick="showMessage(this)"></div>
            <div class="lily" data-message="You are my favorite person in the whole world 🌸" onclick="showMessage(this)"></div>
            <div class="lily" data-message="Your smile lights up my darkest days 🌷" onclick="showMessage(this)"></div>
            <div class="lily" data-message="Every moment with you is a blessing 💖" onclick="showMessage(this)"></div>
            <div class="lily" data-message="I am so lucky to have you, my love 🥰" onclick="showMessage(this)"></div>
        </div>
    </div>

    <div id="modal">
        <div class="modal-content" id="modal-box">
            <p id="secret-message"></p>
            <button class="close-btn" onclick="closeModal()">Close</button>
        </div>
    </div>

    <script>
        function enterGarden() {
            // Hide welcome screen and show garden
            document.getElementById('welcome-screen').style.display = 'none';
            
            const garden = document.getElementById('garden-screen');
            garden.style.display = 'block';
            
            // Allow scrolling once in the garden
            document.body.style.overflow = 'auto'; 
        }

        function showMessage(element) {
            // Get the hidden message from the clicked lily
            const message = element.getAttribute('data-message');
            
            // Set the message text
            document.getElementById('secret-message').innerText = message;
            
            // Show the modal with animation
            const modal = document.getElementById('modal');
            const modalBox = document.getElementById('modal-box');
            
            modal.style.display = 'flex';
            
            // Small delay to allow CSS transitions to trigger
            setTimeout(() => {
                modal.style.opacity = '1';
                modalBox.style.transform = 'translateY(0)';
            }, 10);
        }

        function closeModal() {
            const modal = document.getElementById('modal');
            const modalBox = document.getElementById('modal-box');
            
            // Animate out
            modal.style.opacity = '0';
            modalBox.style.transform = 'translateY(20px)';
            
            // Wait for animation to finish before hiding
            setTimeout(() => {
                modal.style.display = 'none';
            }, 400);
        }
    </script>

</body>
</html>
