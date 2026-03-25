<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<title>Quran - Al Fatiha</title>
<meta name="viewport" content="width=device-width, initial-scale=1.0">

<style>
body {
    margin: 0;
    font-family: Arial, sans-serif;
    background: #0f172a;
    color: white;
    text-align: center;
}

header {
    padding: 20px;
    font-size: 22px;
    background: #1e293b;
}

.container {
    padding: 20px;
}

.ayah {
    margin: 15px 0;
    padding: 15px;
    background: #1e293b;
    border-radius: 12px;
}

.arabic {
    font-size: 24px;
    direction: rtl;
    margin-bottom: 8px;
}

.english {
    font-size: 16px;
    color: #cbd5f5;
}

button {
    padding: 8px 15px;
    border: none;
    border-radius: 8px;
    background: #22c55e;
    color: white;
    font-size: 14px;
    cursor: pointer;
}
</style>
</head>

<body>

<header>📖 Surah Al-Fatiha</header>

<div class="container" id="quran"></div>

<script>
const ayahs = [
{
ar: "بِسْمِ اللَّهِ الرَّحْمَٰنِ الرَّحِيمِ",
en: "In the name of Allah, the Most Gracious, the Most Merciful.",
audio: "https://cdn.islamic.network/quran/audio/128/ar.alafasy/1.mp3"
},
{
ar: "الْحَمْدُ لِلَّهِ رَبِّ الْعَالَمِينَ",
en: "All praise is due to Allah, Lord of the worlds.",
audio: "https://cdn.islamic.network/quran/audio/128/ar.alafasy/2.mp3"
},
{
ar: "الرَّحْمَٰنِ الرَّحِيمِ",
en: "The Most Gracious, the Most Merciful.",
audio: "https://cdn.islamic.network/quran/audio/128/ar.alafasy/3.mp3"
},
{
ar: "مَالِكِ يَوْمِ الدِّينِ",
en: "Master of the Day of Judgment.",
audio: "https://cdn.islamic.network/quran/audio/128/ar.alafasy/4.mp3"
},
{
ar: "إِيَّاكَ نَعْبُدُ وَإِيَّاكَ نَسْتَعِينُ",
en: "You alone we worship, and You alone we ask for help.",
audio: "https://cdn.islamic.network/quran/audio/128/ar.alafasy/5.mp3"
},
{
ar: "اهْدِنَا الصِّرَاطَ الْمُسْتَقِيمَ",
en: "Guide us to the straight path.",
audio: "https://cdn.islamic.network/quran/audio/128/ar.alafasy/6.mp3"
},
{
ar: "صِرَاطَ الَّذِينَ أَنْعَمْتَ عَلَيْهِمْ",
en: "The path of those You have blessed,",
audio: "https://cdn.islamic.network/quran/audio/128/ar.alafasy/7.mp3"
},
{
ar: "غَيْرِ الْمَغْضُوبِ عَلَيْهِمْ وَلَا الضَّالِّينَ",
en: "not of those who earned Your anger, nor of those who went astray.",
audio: "https://cdn.islamic.network/quran/audio/128/ar.alafasy/7.mp3"
}
];

let currentAudio = null;

const container = document.getElementById("quran");

ayahs.forEach((ayah, index) => {
    const div = document.createElement("div");
    div.className = "ayah";

    const button = document.createElement("button");
    button.textContent = "▶️ Play";

    const audio = new Audio(ayah.audio);

    button.onclick = () => {
        // Stop other audio
        if (currentAudio && currentAudio !== audio) {
            currentAudio.pause();
        }

        if (audio.paused) {
            audio.play();
            button.textContent = "⏸ Pause";
            currentAudio = audio;
        } else {
            audio.pause();
            button.textContent = "▶️ Play";
        }
    };

    audio.onended = () => {
        button.textContent = "▶️ Play";
    };

    div.innerHTML = `
        <div class="arabic">${ayah.ar}</div>
        <div class="english">${ayah.en}</div>
    `;

    div.appendChild(button);
    container.appendChild(div);
});
</script>

</body>
</html>
