<!DOCTYPE html>
<html>
<head>
    <title>بنك الشمس</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            text-align: center;
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh; /* لملء الصفحة بالكامل */
            margin: 0;
            background-image: url('https://th.bing.com/th/id/R.697f81fe3fb86332671378d7bc5090c1?rik=kmaEcX%2bFu%2fY%2bWg&pid=ImgRaw&r=0'); /* رابط صورة الشمس */
            background-size: cover;
            background-position: center;
            color: white;
            transition: background-image 0.5s ease; /* إضافة انتقال لتغيير الخلفية */
            flex-direction: column; /* ترتيب العناصر عموديًا */
            justify-content: space-between; /* توزيع العناصر مع الفراغات بينها */
        }
        .content {
            text-align: center;
            background: rgba(0, 0, 0, 0.5); /* خلفية شفافة للنص */
            padding: 20px;
            border-radius: 10px;
            margin-top: 20px;
        }
        input, button {
            padding: 10px;
            margin: 10px;
            font-size: 16px;
        }
        #result {
            font-size: 20px;
            margin-top: 20px;
        }
        footer {
            margin-bottom: 20px;
        }
    </style>
</head>
<body>
    <div class="content">
        <h1>بنك الشمس</h1>
        <p>أدخل اسم الشخصية لترى الستارز والإنذارات</p>
        <input type="text" id="characterName" placeholder="اسم الشخصية">
        <button onclick="showStars()">إظهار المعلومات</button>
        <div id="result"></div>
    </div>
    
    <footer>
        <p>حقوق الطبع والنشر محفوظة <a href="https://www.instagram.com/talal_megumi" target="_blank">talal_megumi</a></p>
    </footer>

    <script>
        const characters = [
            { name: "فايوليت", stars: 1500, alerts: 0, rank: "الملكة", imageUrl: 'https://media1.tenor.com/m/TZ89Av8QBVkAAAAd/violet-evergarden-violet.gif' },
            { name: "شوتو", stars: 1500, alerts: 0, rank: "وزير", imageUrl: 'https://64.media.tumblr.com/2ab9ce88b76275915865b615a0934a24/c5f1d2f2eb86057c-03/s1280x1920/27a5ca69c458325cc450f9f02304c39bff4deb7d.gifv' },
            { name: "توكيتو", stars: 1500, alerts: 0, rank: "رائيس الوزراء", imageUrl: 'https://media1.tenor.com/m/VO0p4rzSGQ4AAAAd/demon-slayer-kimetsu-no-yaiba.gif' },
            { name: "ميغومي", stars: 1500, alerts: 0, rank: "مؤسس البنك", imageUrl: 'https://media1.tenor.com/m/AtKrHqCCRsEAAAAC/megumi.gif' },
            { name: "ايزن", stars: 1500, alerts: 0, rank: "نائب وزير", imageUrl: 'https://media1.tenor.com/m/efkQYGrEwaMAAAAC/aizen-bleach.gif' },
        ];

        function showStars() {
            const name = document.getElementById("characterName").value;
            const character = characters.find(char => char.name === name);
            if (!character) {
                document.getElementById("result").innerHTML = "الشخصية غير موجودة.";
                document.body.style.backgroundImage = "url('https://th.bing.com/th/id/R.697f81fe3fb86332671378d7bc5090c1?rik=kmaEcX%2bFu%2fY%2bWg&pid=ImgRaw&r=0')"; // استعادة الخلفية الأصلية إذا لم توجد الشخصية
                return;
            }
            document.getElementById("result").innerHTML = `
                <p>الرتبة: ${character.rank}</p>
                <p>الستارز: ${character.stars}</p>
                <p>الإنذارات: ${character.alerts}</p>`;
            if (character.imageUrl) {
                document.body.style.backgroundImage = url(${character.imageUrl}); // تغيير الخلفية لصورة الشخصية
            } else {
                document.body.style.backgroundImage = "url('https://th.bing.com/th/id/R.697f81fe3fb86332671378d7bc5090c1?rik=kmaEcX%2bFu%2fY%2bWg&pid=ImgRaw&r=0')"; // استعادة الخلفية الأصلية إذا لم توجد الصورة للشخصية
            }
        }
    </script>
</body>
</html>