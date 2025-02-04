<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Web Development Project</title>
    <style>
        :root {
            --primary-color: #ff7f50; /* Coral */
            --secondary-color: #4caf50; /* Green */
            --tertiary-color: #ffd700; /* Gold */
            --font-family: 'Dancing Script', cursive;
        }

        body {
            margin: 0;
            font-family: var(--font-family);
            background: linear-gradient(135deg, #ff7f50, #4caf50);
            color: white;
        }

        header {
            background-color: var(--tertiary-color);
            color: white;
            padding: 20px;
            text-align: center;
            font-size: 2.5rem;
            font-weight: bold;
            text-shadow: 3px 3px 6px rgba(0, 0, 0, 0.3);
        }

        nav {
            display: flex;
            justify-content: center;
            background-color: rgba(0, 0, 0, 0.7);
            padding: 15px;
            box-shadow: 0px 4px 6px rgba(0, 0, 0, 0.3);
        }

        nav a {
            color: var(--tertiary-color);
            margin: 0 15px;
            text-decoration: none;
            padding: 10px 20px;
            border: 2px solid var(--tertiary-color);
            border-radius: 25px;
            font-weight: bold;
            transition: all 0.3s ease;
        }

        nav a:hover {
            background-color: var(--tertiary-color);
            color: white;
            transform: scale(1.1);
        }

        main {
            padding: 30px;
            text-align: center;
        }

        footer {
            background-color: rgba(0, 0, 0, 0.7);
            color: var(--tertiary-color);
            text-align: center;
            padding: 15px;
            position: fixed;
            bottom: 0;
            width: 100%;
            box-shadow: 0px -2px 4px rgba(0, 0, 0, 0.3);
        }

        .form-container {
            max-width: 500px;
            margin: 30px auto;
            padding: 25px;
            background: white;
            border-radius: 15px;
            box-shadow: 0 8px 16px rgba(0, 0, 0, 0.2);
            color: black;
        }

        .form-container input, .form-container select, .form-container button {
            width: 100%;
            margin: 15px 0;
            padding: 12px;
            border: 1px solid #ddd;
            border-radius: 8px;
            font-size: 1rem;
        }

        .form-container button {
            background-color: var(--primary-color);
            color: white;
            border: none;
            font-weight: bold;
            transition: all 0.3s ease;
        }

        .form-container button:hover {
            background-color: var(--secondary-color);
            transform: scale(1.05);
        }

        .link-container {
            margin: 30px 0;
        }

        .link-container a {
            display: inline-block;
            margin: 15px;
            padding: 15px 20px;
            background: var(--primary-color);
            color: white;
            text-decoration: none;
            border-radius: 10px;
            box-shadow: 0 4px 6px rgba(0, 0, 0, 0.2);
            font-weight: bold;
            transition: transform 0.3s ease, background 0.3s ease;
        }

        .link-container a:hover {
            background: var(--secondary-color);
            transform: scale(1.1);
        }

        .popup {
            display: none;
            position: fixed;
            top: 50%;
            left: 50%;
            transform: translate(-50%, -50%);
            background: white;
            padding: 30px;
            box-shadow: 0 8px 16px rgba(0, 0, 0, 0.3);
            border-radius: 15px;
            z-index: 1000;
        }

        .popup-overlay {
            display: none;
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: rgba(0, 0, 0, 0.6);
            z-index: 999;
        }

        @media (max-width: 768px) {
            nav {
                flex-direction: column;
            }

            .link-container a {
                margin: 10px auto;
            }
        }
    </style>
</head>
<body>
    <header>
        Web Development Project
    </header>

    <nav>
        <a href="#">Home</a>
        <a href="#">About</a>
        <a href="#">Contact Us</a>
    </nav>

    <main>
        <section class="link-container">
            <h2>Important Links</h2>
            <a href="https://ptuk.edu.ps/ar/" target="_blank">Palestine Technical University</a>
			 <a href="http://www.qutaibamustafa.eb2a.com/?i=1" target="_blank">Calculate GPA</a>
            <a href="https://ps.opensooq.com/ar?gad_source=1&gclid=CjwKCAiAneK8BhAVEiwAoy2HYZ24HPyTwwLjtApjyfFhhrBuLZRR8H1ccmYrhOLjW9DepQIgzJrThBoCytgQAvD_BwE" target="_blank">OpenSooq</a>
           
        </section>

        <section>
            <h2>Leave a Message</h2>
            <div class="form-container">
                <form id="contactForm">
                    <input type="text" id="name" placeholder="Your Name" required>
                    <select id="selection">
                        <option value="">Choose a Service</option>
                        <option value="technical-support">Technical Support</option>
                        <option value="general-inquiry">General Inquiry</option>
                    </select>
                    <button type="submit">Submit</button>
                </form>
            </div>
        </section>

        <div class="popup-overlay" id="popupOverlay"></div>
        <div class="popup" id="popup">
            <p>Your form has been submitted successfully!</p>
            <button onclick="closePopup()">Close</button>
        </div>
    </main>

    <footer>
        <p> 2025 Web Development Project. All rights reserved.</p>
    </footer>

    <script>
        document.getElementById('contactForm').addEventListener('submit', function(e) {
            e.preventDefault();
            const name = document.getElementById('name').value;
            const selection = document.getElementById('selection').value;

            if (!name || !selection) {
                alert('Please fill in all fields.');
                return;
            }

            showPopup();
        });

        function showPopup() {
            document.getElementById('popup').style.display = 'block';
            document.getElementById('popupOverlay').style.display = 'block';
        }

        function closePopup() {
            document.getElementById('popup').style.display = 'none';
            document.getElementById('popupOverlay').style.display = 'none';
        }
    </script>
</body>
</html>
