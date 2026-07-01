<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Nuestra Primera Cita</title>
    <style>
        @import url('https://fonts.googleapis.com/css2?family=Playfair+Display:wght@400;700&family=Dancing+Script:wght@400;700&display=swap');
        
        body {
            margin: 0;
            padding: 0;
            font-family: 'Playfair Display', serif;
            background: linear-gradient(to bottom, #0a001f, #1a0033);
            color: #fff;
            overflow-x: hidden;
            position: relative;
            min-height: 100vh;
        }
        
        .stars {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: radial-gradient(circle, rgba(255,255,255,0.9) 1px, transparent 2px);
            background-size: 60px 60px;
            opacity: 0.3;
            z-index: 1;
            animation: twinkle 7s infinite alternate;
        }
        
        @keyframes twinkle {
            0% { opacity: 0.25; }
            100% { opacity: 0.45; }
        }
        
        .container {
            position: relative;
            z-index: 2;
        }
        
        .cover {
            height: 100vh;
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
            background: linear-gradient(rgba(10,0,30,0.65), rgba(26,0,51,0.75)), 
                        url('https://i.imgur.com/49802.jpg') center/cover no-repeat;
            text-align: center;
            position: relative;
        }
        
        .cover h1 {
            font-family: 'Dancing Script', cursive;
            font-size: 3.6rem;
            line-height: 1.15;
            color: #ffb6c1;
            text-shadow: 0 0 25px #ff1493;
            margin: 0 25px 20px;
        }
        
        .envelope-container {
            padding: 110px 20px;
            background: rgba(8, 2, 35, 0.96);
        }
        
        .envelope {
            max-width: 430px;
            margin: 0 auto;
            background: linear-gradient(#f8e9c9, #e8d5a3);
            padding: 55px 40px 75px;
            border-radius: 18px;
            box-shadow: 0 30px 60px rgba(0,0,0,0.65);
            cursor: pointer;
            transition: all 0.4s;
            border: 14px solid #8b5a2b;
        }
        
        .envelope:hover {
            transform: scale(1.07) rotate(3deg);
        }
        
        .open-btn {
            background: linear-gradient(#ff1493, #db2777);
            color: white;
            border: none;
            padding: 17px 58px;
            font-size: 1.4rem;
            border-radius: 9999px;
            margin-top: 35px;
            box-shadow: 0 10px 30px rgba(255,20,147,0.5);
        }
        
        .modal {
            display: none;
            position: fixed;
            inset: 0;
            background: rgba(4,0,22,0.97);
            z-index: 999;
            align-items: center;
            justify-content: center;
        }
        
        .modal-content {
            background: #fff9f0;
            color: #3c2a2a;
            padding: 50px 40px;
            border-radius: 22px;
            max-width: 520px;
            box-shadow: 0 35px 80px rgba(0,0,0,0.75);
            border: 16px solid #9c6644;
        }
        
        .no-response {
            display: none;
            margin-top: 25px;
            padding: 20px;
            background: #ffe4e1;
            border-radius: 12px;
            color: #9f2a6b;
            font-size: 1.35rem;
        }
    </style>
</head>
<body>
    <div class="stars"></div>
    
    <!-- Portada con tu foto -->
    <section class="cover">
        <div class="container">
            <h1>Nuestra primera cita,<br>una de muchas,<br>el inicio de una vida juntos</h1>
        </div>
    </section>
    
    <!-- Sobre -->
    <section class="envelope-container">
        <div class="container">
            <div class="envelope" onclick="openEnvelope()">
                <h2 style="color:#5c3311;font-size:2.2rem;">Abre mi carta para ti</h2>
                <button class="open-btn">Abrir Sobre</button>
            </div>
        </div>
    </section>
    
    <!-- Modal Pregunta -->
    <div id="questionModal" class="modal">
        <div class="modal-content">
            <h2 style="font-family:'Dancing Script',cursive;color:#c71585;text-align:center;">Elizabeth, ¿quieres pasar conmigo una eternidad?</h2>
            <div style="text-align:center;margin:40px 0;">
                <button onclick="answerYes()" style="background:#22c55e;color:white;font-size:1.65rem;padding:18px 55px;border:none;border-radius:9999px;margin:0 12px;cursor:pointer;">siii 🙂‍↕️</button>
                <button onclick="answerNo()" style="background:#f97316;color:white;font-size:1.65rem;padding:18px 55px;border:none;border-radius:9999px;margin:0 12px;cursor:pointer;">noo 😿</button>
            </div>
            <div id="noResponse" class="no-response">
                mi niña se que te haces la difícil, solo preciona que si 😿🫰
            </div>
        </div>
    </div>
    
    <!-- Modal Carta -->
    <div id="letterModal" class="modal">
        <div class="modal-content" style="max-height:88vh;overflow-y:auto;">
            <h2 style="text-align:center;color:#9f2a6b;">Sabía que aceptarías mi niña hermosa</h2>
            <div style="font-size:1.32rem;line-height:1.8;text-align:left;">
                <p>Sabes? Desde que te conozco mis sentimientos fueron confusos, pero hoy en día sé que te quiero, que te amo, que quiero estar contigo y entregarte todo lo que tengo.</p>
                <p>Gracias por estar en mi vida, porque desde que estás conmigo sacas una risa, una sonrisa y me haces feliz. Me gustas mucho, eres la chica que quiero en mi vida, poder cocinar juntos, dormir, reír, ver películas, aprender más de tu mundo y conocer cosas que nadie más conoce.</p>
                <p>Yo me estaba ahogando cuando te conocí, pero tú, tú me salvaste. Tú eres la luz de mi vida, apareciste cuando menos lo esperaba, y nos unimos cuando yo no quería nada en el amor.</p>
                <p>Te quiero mi preciosa Elizabeth, eres todo lo que alguna vez pedí a Dios, y cada día me enamoro y te amo más.</p>
            </div>
            <p style="text-align:right;margin-top:45px;font-weight:bold;color:#9f2a6b;">ATT: el niño más bromista,<br>tu novio, tu amigo, tu confidente Jonathan...</p>
            <button onclick="closeLetter()" style="margin-top:35px;width:100%;padding:15px;background:#c71585;color:white;border:none;border-radius:50px;font-size:1.25rem;">Cerrar carta</button>
        </div>
    </div>
    
    <script>
        function openEnvelope() {
            document.getElementById('questionModal').style.display = 'flex';
            document.getElementById('noResponse').style.display = 'none';
        }
        
        function answerYes() {
            document.getElementById('questionModal').style.display = 'none';
            document.getElementById('letterModal').style.display = 'flex';
            createHearts();
        }
        
        function answerNo() {
            document.getElementById('noResponse').style.display = 'block';
        }
        
        function closeLetter() {
            document.getElementById('letterModal').style.display = 'none';
        }
        
        function createHearts() {
            for (let i = 0; i < 40; i++) {
                setTimeout(() => {
                    const heart = document.createElement('div');
                    heart.innerHTML = '❤️';
                    heart.style.position = 'fixed';
                    heart.style.fontSize = '2rem';
                    heart.style.left = Math.random() * 100 + 'vw';
                    heart.style.bottom = '-60px';
                    heart.style.zIndex = '2000';
                    heart.style.transition = 'transform 4.2s linear, opacity 4.2s';
                    document.body.appendChild(heart);
                    
                    requestAnimationFrame(() => {
                        heart.style.transform = `translateY(-\( {window.innerHeight + 300}px) rotate( \){Math.random()*90-45}deg)`;
                        heart.style.opacity = '0';
                    });
                    
                    setTimeout(() => heart.remove(), 5000);
                }, i * 38);
            }
        }
    </script>
</body>
</html>
