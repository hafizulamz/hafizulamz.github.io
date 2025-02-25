---
layout: about
title: 
permalink: /businesscard
subtitle: false

profile: false
  align:false
  image: false
  image_circular: false
  more_info: false

news: false
selected_papers: false
social: false
---


<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Digital Business Card</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
            background-color: #121212;
            color: #ffffff;
        }
        .card {
            background: #1e1e1e;
            padding: 20px;
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
        }
        .card a {
            color: #2698ba;
            text-decoration: none;
            margin: 5px 10px;
        }
        .card a:hover {
            text-decoration: underline;
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
        }
        .email-popup img {
            max-width: 100%;
            height: auto;
        }
        .close-btn {
            margin-top: 10px;
            padding: 5px 10px;
            background: #2698ba;
            color: white;
            border: none;
            border-radius: 5px;
            cursor: pointer;
        }
        .close-btn:hover {
            background: #1b7087;
        }
    </style>
</head>
<body>
    <div class="card">
        <img src="/assets/img/hafizul.jpg" alt="Profile Picture">
        <h2>Mohd Hafizul Afifi bin Abdullah</h2>
        <p>Lecturer, Universiti Tunku Abdul Rahman (UTAR), Malaysia</p>
        <p>
            <a href="#" onclick="showEmailPopup()">Email</a> | 
            <a href="http://hafizulabdullah.com/" target="_blank">Website</a> | 
            <a href="https://www.linkedin.com/in/hafizulamz/" target="_blank">LinkedIn</a>
        </p>
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