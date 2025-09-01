# Ml-chats
Sites de messagerie 
<!DOCTYPE html>
<html lang="fr">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>ML Chats - Messagerie</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            margin: 0;
            padding: 0;
            background-color: #f0f2f5;
            color: #333;
        }
        header {
            background-color: #0084ff;
            color: white;
            text-align: center;
            padding: 1em;
        }
        nav {
            background-color: #333;
            padding: 1em;
            text-align: center;
        }
        nav a {
            color: white;
            margin: 0 1em;
            text-decoration: none;
        }
        nav a:hover {
            text-decoration: underline;
        }
        .container {
            max-width: 1200px;
            margin: 2em auto;
            display: flex;
            gap: 1em;
        }
        .sidebar {
            width: 30%;
            background-color: white;
            border-radius: 8px;
            padding: 1em;
            box-shadow: 0 2px 5px rgba(0,0,0,0.1);
        }
        .sidebar h3 {
            margin-top: 0;
        }
        .chat-area {
            width: 70%;
            background-color: white;
            border-radius: 8px;
            padding: 1em;
            box-shadow: 0 2px 5px rgba(0,0,0,0.1);
            display: flex;
            flex-direction: column;
        }
        .messages {
            flex-grow: 1;
            overflow-y: auto;
            height: 400px;
            padding: 1em;
            border-bottom: 1px solid #ddd;
        }
        .message {
            margin: 0.5em 0;
            padding: 0.5em 1em;
            border-radius: 8px;
        }
        .message.sent {
            background-color: #0084ff;
            color: white;
            margin-left: 20%;
            text-align: right;
        }
        .message.received {
            background-color: #e9ecef;
            margin-right: 20%;
        }
        .chat-input {
            display: flex;
            gap: 1em;
            padding: 1em 0;
        }
        .chat-input input {
            flex-grow: 1;
            padding: 0.5em;
            border: 1px solid #ddd;
            border-radius: 4px;
        }
        .chat-input button {
            padding: 0.5em 1em;
            background-color: #0084ff;
            color: white;
            border: none;
            border-radius: 4px;
            cursor: pointer;
        }
        .youtube-section {
            margin: 2em auto;
            text-align: center;
        }
        .youtube-section iframe {
            width: 560px;
            height: 315px;
            max-width: 100%;
        }
        footer {
            background-color: #333;
            color: white;
            text-align: center;
            padding: 1em;
            position: relative;
            width: 100%;
        }
    </style>
</head>
<body>
    <header>
        <h1>ML Chats</h1>
        <p>Votre plateforme de messagerie simple et rapide</p>
    </header>
    <nav>
        <a href="#home">Accueil</a>
        <a href="#chat">Chat</a>
        <a href="#youtube">Ma Chaîne YouTube</a>
        <a href="#contact">Contact</a>
    </nav>
    <div class="container">
        <div class="sidebar">
            <h3>Contacts</h3>
            <ul style="list-style: none; padding: 0;">
                <li><a href="#" onclick="selectContact('Ami 1')">Ami 1</a></li>
                <li><a href="#" onclick="selectContact('Ami 2')">Ami 2</a></li>
            </ul>
        </div>
        <div class="chat-area">
            <h3>Chat avec <span id="current-contact">Ami 1</span></h3>
            <div class="messages" id="messages">
                <div class="message received">Salut ! Ça va ?</div>
                <div class="message sent">Oui, super ! Et toi ?</div>
            </div>
            <div class="chat-input">
                <input type="text" id="message-input" placeholder="Écrivez votre message...">
                <button onclick="sendMessage()">Envoyer</button>
            </div>
        </div>
    </div>
    <div class="youtube-section" id="youtube">
        <h2>Ma Chaîne YouTube</h2>
        <p>Découvrez mes vidéos et abonnez-vous pour ne rien manquer !</p>
        <!-- Remplace l'URL par l'ID de ta vidéo YouTube -->
        <iframe src="https://www.youtube.com/embed/https://youtu.be/7dWKpqaU3lo?si=CCm7WRB26ahdr66a" allowfullscreen></iframe>
        <p><a href="https://www.youtube.com/channel/https://youtube.com/@loctiniel?si=lRM39Wpz6IOblibB" target="_blank">Abonnez-vous à ma chaîne !</a></p>
    </div>
    <footer>
        <p>&copy; 2025 ML Chats. Tous droits réservés.</p>
    </footer>

    <script>
        function selectContact(contact) {
            document.getElementById('current-contact').textContent = contact;
            document.getElementById('messages').innerHTML = `<div class="message received">Salut ${contact} !</div>`;
        }

        function sendMessage() {
            const input = document.getElementById('message-input');
            const message = input.value.trim();
            if (message) {
                const messages = document.getElementById('messages');
                const newMessage = document.createElement('div');
                newMessage.className = 'message sent';
                newMessage.textContent = message;
                messages.appendChild(newMessage);
                input.value = '';
                messages.scrollTop = messages.scrollHeight;
            }
        }
    </script>
</body>
</html>
