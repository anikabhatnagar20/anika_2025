---
layout: base
title: Student Home 
description: Home Page
hide: true
---

Anika's page: 
Welcome to my blog. 

<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Music Recommendation Tool</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            margin: 50px;
            background-color: #f0f0f0;
            text-align: center;
        }
        select, button {
            padding: 10px;
            font-size: 16px;
            margin: 5px;
        }
        #recommendation {
            margin-top: 20px;
            font-size: 18px;
            color: #333;
        }
    </style>
</head>
<body>
    <h1>Music Recommendation Tool</h1>
    <p>Select your current mood, and i'll recommend a music genre for you.</p>
    
    <select id="moodSelect">
        <option value="">--Select a mood--</option>
        <option value="happy">Happy</option>
        <option value="sad">Sad</option>
        <option value="energetic">Energetic</option>
        <option value="relaxed">Relaxed</option>
    </select>
    <button onclick="recommendMusic()">Recommend Music</button>
    
    <div id="recommendation"></div>

    <script>
        function recommendMusic() {
            const mood = document.getElementById('moodSelect').value;
            let recommendation;

            switch(mood) {
                case 'happy':
                    recommendation = "Pop or Dance music";
                    break;
                case 'sad':
                    recommendation = "Blues or Acoustic";
                    break;
                case 'energetic':
                    recommendation = "Rock or EDM";
                    break;
                case 'relaxed':
                    recommendation = "Jazz or Chillout";
                    break;
                default:
                    recommendation = "Please select a mood to get a recommendation.";
            }

            document.getElementById('recommendation').textContent = `I recommend listening to ${recommendation}.`;
        }
    </script>
</body>
</html>

