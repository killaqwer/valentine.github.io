# valentine.github.io
<!DOCTYPE html>
<html lang="ru">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Будь моей валентинкой? 💖</title>
<style>
* {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
}

body {
    font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
    background: linear-gradient(135deg, #ffeef8 0%, #ffe6f0 50%, #ffd6e8 100%);
    min-height: 100vh;
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    overflow: hidden;
    transition: all 0.8s ease;
}

body.celebration {
    background: linear-gradient(135deg, #ff99cc 0%, #ff66b2 50%, #ff3385 100%);
}

.container {
    text-align: center;
    padding: 20px;
    max-width: 600px;
    position: relative;
    z-index: 10;
}

h1 {
    font-size: 2.5em;
    color: #ff1a75;
    margin-bottom: 30px;
    text-shadow: 2px 2px 4px rgba(255, 26, 117, 0.2);
    animation: pulse 2s ease-in-out infinite;
}

@keyframes pulse {
    0%, 100% { transform: scale(1); }
    50% { transform: scale(1.05); }
}

.gif-container {
    margin: 30px 0;
}

#mainGif {
    width: 280px;
    max-width: 90vw;
    border-radius: 20px;
    box-shadow: 0 10px 30px rgba(0, 0, 0, 0.2);
    transition: transform 0.3s ease;
}

#mainGif:hover {
    transform: scale(1.05);
}

.buttons {
    margin-top: 40px;
    position: relative;
    height: 80px;
}

button {
    padding: 18px 45px;
    font-size: 22px;
    margin: 10px;
    cursor: pointer;
    border-radius: 15px;
    border: none;
    font-weight: bold;
    transition: all 0.3s ease;
    box-shadow: 0 5px 15px rgba(0, 0, 0, 0.2);
}

#yesBtn {
    background: linear-gradient(135deg, #ff4d88 0%, #ff1a75 100%);
    color: white;
    position: relative;
    z-index: 2;
}

#yesBtn:hover {
    transform: scale(1.1);
    box-shadow: 0 8px 25px rgba(255, 26, 117, 0.4);
}

#yesBtn:active {
    transform: scale(0.95);
}

#noBtn {
    background: linear-gradient(135deg, #bbb 0%, #999 100%);
    color: white;
    position: absolute;
    transition: all 0.15s ease;
}

.celebration-content {
    display: none;
    opacity: 0;
    animation: fadeIn 1s ease forwards;
}

.celebration-content.show {
    display: block;
}

@keyframes fadeIn {
    to { opacity: 1; }
}

.celebration-text {
    font-size: 3em;
    color: white;
    margin: 30px 0;
    text-shadow: 3px 3px 6px rgba(0, 0, 0, 0.3);
    animation: bounce 1s ease infinite;
}

@keyframes bounce {
    0%, 100% { transform: translateY(0); }
    50% { transform: translateY(-10px); }
}

.photo-gallery {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
    gap: 20px;
    margin-top: 30px;
}

.photo-placeholder {
    width: 100%;
    aspect-ratio: 1;
    background: white;
    border-radius: 15px;
    display: flex;
    align-items: center;
    justify-content: center;
    font-size: 1.2em;
    color: #ff4d88;
    box-shadow: 0 5px 15px rgba(0, 0, 0, 0.2);
    transition: transform 0.3s ease;
}

.photo-placeholder:hover {
    transform: scale(1.05) rotate(2deg);
}

/* Конфетти */
.confetti {
    position: fixed;
    width: 10px;
    height: 10px;
    background: #ff4d88;
    position: absolute;
    animation: confetti-fall 3s linear forwards;
}

@keyframes confetti-fall {
    to {
        transform: translateY(100vh) rotate(360deg);
        opacity: 0;
    }
}

/* Плавающие сердечки */
.heart {
    position: fixed;
    font-size: 30px;
    animation: float-up 4s ease-in forwards;
    pointer-events: none;
}

@keyframes float-up {
    to {
        transform: translateY(-100vh) scale(0);
        opacity: 0;
    }
}

.love-message {
    background: rgba(255, 255, 255, 0.9);
    padding: 20px;
    border-radius: 15px;
    margin-top: 20px;
    box-shadow: 0 5px 20px rgba(0, 0, 0, 0.2);
    display: none;
}

.love-message.show {
    display: block;
    animation: slideUp 0.6s ease;
}

@keyframes slideUp {
    from {
        transform: translateY(50px);
        opacity: 0;
    }
    to {
        transform: translateY(0);
        opacity: 1;
    }
}

.love-message p {
    color: #ff1a75;
    font-size: 1.1em;
    line-height: 1.6;
    margin: 10px 0;
}
</style>
</head>
<body>

<div class="container" id="mainContainer">
    <h1>Ты станешь моей валентинкой? 💖</h1>
    
    <div class="gif-container">
        <img id="mainGif" src="https://media.giphy.com/media/JIX9t2j0ZTN9S/giphy.gif" alt="Cute puppy">
    </div>
    
    <div class="buttons">
        <button id="yesBtn">Да 💗</button>
        <button id="noBtn">Нет 🙈</button>
    </div>
</div>

<div class="celebration-content" id="celebrationContent">
    <h1 class="celebration-text">Урааааа!!! 💖💖💖</h1>
    
    <div class="gif-container">
        <img id="celebrationGif" src="https://media.giphy.com/media/MDJ9IbxxvDUQM/giphy.gif" alt="Celebration">
    </div>
    
    <div class="love-message show">
        <p>🌹 Ты сделала меня самым счастливым! 🌹</p>
        <p>💕 Вместе мы — идеальная пара! 💕</p>
        <p>✨ С днём Святого Валентина, моя любовь! ✨</p>
    </div>
    
    <div class="photo-gallery">
        <div class="photo-placeholder">📸 Фото 1<br>(загрузи свои)</div>
        <div class="photo-placeholder">📸 Фото 2<br>(загрузи свои)</div>
        <div class="photo-placeholder">📸 Фото 3<br>(загрузи свои)</div>
        <div class="photo-placeholder">📸 Фото 4<br>(загрузи свои)</div>
    </div>
</div>

<script>
const noBtn = document.getElementById("noBtn");
const yesBtn = document.getElementById("yesBtn");
const mainContainer = document.getElementById("mainContainer");
const celebrationContent = document.getElementById("celebrationContent");

// Массив текстов для кнопки "Нет"
const noTexts = [
    "Нет 🙈",
    "Ты уверена? 🥺",
    "Подумай ещё... 😢",
    "А если хорошо подумать? 😏",
    "Точно нет? 🥹",
    "Может всё-таки да? 💝",
    "Пожалуйста? 🙏"
];

let noClickCount = 0;
let noBtnSize = 100; // процент от изначального размера

// Перемещение кнопки "Нет" при наведении
noBtn.addEventListener("mouseover", () => {
    const maxX = window.innerWidth - noBtn.offsetWidth - 20;
    const maxY = window.innerHeight - noBtn.offsetHeight - 20;
    
    const x = Math.random() * maxX;
    const y = Math.random() * maxY;
    
    noBtn.style.left = x + "px";
    noBtn.style.top = y + "px";
    
    // Изменение текста
    noClickCount++;
    if (noClickCount < noTexts.length) {
        noBtn.textContent = noTexts[noClickCount];
    }
    
    // Уменьшение кнопки
    noBtnSize = Math.max(30, noBtnSize - 10);
    noBtn.style.transform = `scale(${noBtnSize / 100})`;
});

// Клик на "Да"
yesBtn.addEventListener("click", () => {
    // Скрываем главный контейнер
    mainContainer.style.display = "none";
    
    // Показываем праздничный контент
    celebrationContent.classList.add("show");
    
    // Меняем фон
    document.body.classList.add("celebration");
    
    // Создаём конфетти
    createConfetti();
    
    // Создаём плавающие сердечки
    setInterval(createHeart, 300);
});

// Функция создания конфетти
function createConfetti() {
    const colors = ['#ff1a75', '#ff4d88', '#ff99cc', '#ffd6e8', '#ffeb3b', '#4caf50'];
    
    for (let i = 0; i < 100; i++) {
        setTimeout(() => {
            const confetti = document.createElement('div');
            confetti.className = 'confetti';
            confetti.style.left = Math.random() * 100 + 'vw';
            confetti.style.background = colors[Math.floor(Math.random() * colors.length)];
            confetti.style.animationDelay = Math.random() * 2 + 's';
            confetti.style.animationDuration = (Math.random() * 2 + 2) + 's';
            document.body.appendChild(confetti);
            
            setTimeout(() => confetti.remove(), 5000);
        }, i * 30);
    }
}

// Функция создания сердечек
function createHeart() {
    const heart = document.createElement('div');
    heart.className = 'heart';
    heart.textContent = ['💖', '💕', '💗', '💓', '💝'][Math.floor(Math.random() * 5)];
    heart.style.left = Math.random() * 100 + 'vw';
    heart.style.bottom = '-50px';
    heart.style.animationDuration = (Math.random() * 2 + 3) + 's';
    document.body.appendChild(heart);
    
    setTimeout(() => heart.remove(), 5000);
}

// Инициализация позиции кнопки "Нет"
function initNoButton() {
    const rect = yesBtn.getBoundingClientRect();
    noBtn.style.left = (rect.right + 20) + 'px';
    noBtn.style.top = rect.top + 'px';
}

window.addEventListener('load', initNoButton);
window.addEventListener('resize', initNoButton);
</script>

</body>
</html>
