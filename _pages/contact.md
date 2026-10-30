---
layout: page
title: contact
permalink: /contact/
description: virtual business card. scan the QR code to save my contact.
nav: false
---

<style>
  .vcard {
    background-color: var(--global-card-bg-color);
    border: 2px solid var(--global-theme-color);
    border-radius: 16px;
    box-shadow: 0 4px 12px rgba(0, 0, 0, 0.15);
    padding: 24px;
    max-width: 550px;
    margin: 1rem auto;
    text-align: center;
  }
  .vcard .name {
    font-size: 1.8em;
    font-weight: bold;
    color: var(--global-theme-color);
  }
  .vcard .title,
  .vcard .speciality,
  .vcard .note {
    color: var(--global-text-color-light);
  }
  .vcard .title {
    font-size: 1.1em;
    margin-bottom: 6px;
  }
  .vcard .speciality {
    font-size: 0.95em;
    margin-bottom: 16px;
  }
  .vcard .org {
    margin-bottom: 18px;
  }
  .vcard .contact a {
    display: block;
    margin: 4px 0;
    word-break: break-all;
  }
  .vcard .qr-container {
    margin: 20px 0 10px 0;
  }
  .vcard .qr-container img {
    width: 160px;
    height: 160px;
    border: 2px solid var(--global-theme-color);
    border-radius: 12px;
    background-color: #fff;
    padding: 8px;
  }
  .vcard .note {
    font-size: 0.9em;
    margin-bottom: 20px;
  }
  .vcard .btn-appointment {
    background-color: var(--global-theme-color);
    color: #fff;
    padding: 12px 24px;
    border-radius: 8px;
    text-decoration: none;
    display: inline-block;
  }
  .vcard .btn-appointment:hover {
    opacity: 0.85;
    color: #fff;
  }
</style>

<div class="vcard">
  <div class="name">Dr. Hafizul Abdullah</div>
  <div class="title">Assistant Professor / Researcher</div>
  <div class="speciality">
    Specialising in deep learning for biomedical imaging and natural language processing.
  </div>
  <div class="org">Universiti Tunku Abdul Rahman (UTAR)</div>

  <div class="contact">
    <a href="mailto:hafizulafifi@utar.edu.my">hafizulafifi@utar.edu.my</a>
    <a href="https://hafizulabdullah.com/">https://hafizulabdullah.com</a>
  </div>

  <div class="qr-container">
    <img src="https://api.qrserver.com/v1/create-qr-code/?size=160x160&data=BEGIN%3AVCARD%0AVERSION%3A3.0%0AN%3AAbdullah%3BHafizul%3B%3BDr.%3B%0AFN%3ADr.%20Hafizul%20Abdullah%0ATITLE%3AAssistant%20Professor%0AORG%3AUniversiti%20Tunku%20Abdul%20Rahman%20(UTAR)%0AEMAIL%3BTYPE%3Dwork%3Ahafizulafifi%40utar.edu.my%0AURL%3BTYPE%3Dwork%3Ahttps%3A%2F%2Fhafizulabdullah.com%2F%0ANOTE%3ASpecialising%20in%20deep%20learning%20for%20biomedical%20imaging%20and%20natural%20language%20processing.%0AEND%3AVCARD" alt="vCard QR code for Dr. Hafizul Abdullah">
  </div>

  <div class="note">Scan the QR to save contact.</div>

  <a class="btn-appointment" href="https://calendar.google.com/calendar/appointments/AcZssZ0ct9pezfkSREcf1EtOf3vrDOFKKMIcQITPDpQ=" target="_blank" rel="noopener noreferrer">
    Schedule Appointment
  </a>
</div>
