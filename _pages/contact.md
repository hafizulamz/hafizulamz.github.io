---
layout: page
title: "Contact"
permalink: /contact/
subtitle: false

profile: 
  align: false
  image: false
  image_circular: false
  more_info: false

news: false
selected_papers: false
social: false
---

<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <link rel="shortcut icon" href="/assets/img/favicon.ico"/>
    <title>Virtual Business Card | Mohd Hafizul Afifi Abdullah</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
            background-color: #121212;
            color: #ffffff;
            margin: 0;
        }
        .card {
            background: #1e1e1e;
            padding: 25px;
            border-radius: 10px;
            box-shadow: 0 4px 8px rgba(255, 255, 255, 0.1);
            text-align: center;
            max-width: 350px;
        }
        .card img {
            width: 100px;
            height: 100px;
            border-radius: 50%;
            margin-bottom: 15px;
            border: 2px solid #ffffff;
        }
        .card h2 {
            margin: 10px 0;
            color: #ffffff;
        }
        .card p {
            color: #aaaaaa;
            margin-bottom: 8px;
        }
        .button {
            display: inline-block;
            margin: 8px 5px;
            padding: 10px 15px;
            background: #2698ba;
            color: white !important;
            border: none;
            border-radius: 5px;
            cursor: pointer;
            text-decoration: none !important;
            font-size: 14px;
            font-weight: bold;
        }
        .button:hover {
            background: #1b7087;
        }
        .meeting-buttons {
            margin-top: 10px;
            display: flex;
            justify-content: center;
            gap: 10px;
        }
        .email-popup {
            display: none;
            position: fixed;
            top: 50%;
            left: 50%;
            transform: translate(-50%, -50%);
            background: #1e1e1e;
            padding: 20px;
            border-radius: 10px;
            box-shadow: 0 4px 8px rgba(255, 255, 255, 0.1);
            text-align: center;
            width: 90%;
            max-width: 400px;
        }
        .email-popup img {
            max-width: 100%;
            height: auto;
            margin-bottom: 15px;
        }
        .close-btn {
            display: block;
            margin-top: 15px;
            padding: 8px 15px;
            background: #2698ba;
            color: white;
            border: none;
            border-radius: 5px;
            cursor: pointer;
            font-size: 14px;
            font-weight: bold;
            width: 100%;
        }
        .close-btn:hover {
            background: #1b7087;
        }
        .back-home {
            display: block;
            margin-top: 20px;
            color: #2698ba;
            text-decoration: none;
            font-size: 14px;
            font-weight: bold;
        }
        .back-home:hover {
            text-decoration: underline;
        }
    </style>
</head>
<body>
    <div class="card">
        <img src="/assets/img/hafizul.jpg" alt="Profile Picture">
        <h2>Mohd Hafizul Afifi bin Abdullah</h2>
        <p>Lecturer, Universiti Tunku Abdul Rahman (UTAR), Malaysia</p>
        <p><b>Office: NG-002, FICT (Block N), UTAR</b></p>

        <div class="meeting-buttons">
            <a href="https://calendar.app.google/akiTetLdJ64gZ2p9A" class="button">Online Meeting</a>
            <a href="https://calendar.app.google/ZVAdQqetn9LHdkuU6" class="button">Physical Meeting</a>
        </div>

        <a href="#" onclick="showEmailPopup()" class="button">Email</a>
        <a href="/assets/contact/vcard.vcf" class="button">Add to Contact</a>

        <a href="http://hafizulabdullah.com/" class="back-home">&larr; Back to Homepage</a>
    </div>
    
    <div id="email-popup" class="email-popup">
        <img src="/assets/img/email.png" alt="Email Address">
        <button class="close-btn" onclick="closeEmailPopup()">Close</button>
    </div>
    
    <script>
        function showEmailPopup() {
            document.getElementById('email-popup').style.display = 'block';
        }
        function closeEmailPopup() {
            document.getElementById('email-popup').style.display = 'none';
        }
    </script>
</body>
</html>
