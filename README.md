```html
<!DOCTYPE html>
<html lang="pt">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Animação de Digitação</title>
    <style>
        @keyframes typing {
            from { width: 0; }
            to { width: 100%; }
        }
        @keyframes blink {
            50% { border-color: transparent; }
        }
        .typing-container {
            font-family: Arial, sans-serif;
            font-size: 24px;
            font-weight: bold;
            white-space: nowrap;
            overflow: hidden;
            border-right: 3px solid black;
            display: inline-block;
            width: 0;
            animation: typing 3s steps(20, end) forwards, blink 0.7s step-end infinite;
        }
    </style>
</head>
<body>
    <svg width="500" height="150" viewBox="0 0 500 150" xmlns="http://www.w3.org/2000/svg">
        <text x="10" y="50" id="text" font-family="Arial" font-size="24" font-weight="bold">Vc é o melhor!</text>
    </svg>
    <script>
        document.addEventListener("DOMContentLoaded", function() {
            const text = document.getElementById("text");
            const words = "Vc é o melhor!";
            let index = 0;
            text.textContent = "";
            
            function type() {
                if (index < words.length) {
                    text.textContent += words[index];
                    index++;
                    setTimeout(type, 150);
                }
            }
            type();
        });
    </script>
</body>
</html>
```
