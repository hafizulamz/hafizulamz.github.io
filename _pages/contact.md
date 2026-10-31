---
layout: page
title: contact
permalink: /contact/
description: book an appointment or save my contact details.
nav: false
---

<style>
  .vcard {
    margin-top: 1rem;
    text-align: center;
  }
  /* framed QR card: theme-colour border, white panel, caption band */
  .vcard .qr-card {
    display: block;
    width: min(320px, 100%);
    margin: 0 auto 28px auto;
    padding: 14px 14px 0 14px;
    background-color: var(--global-theme-fill-color);
    border-radius: 6px;
  }
  .vcard .qr-panel {
    padding: 22px 22px 16px 22px;
    background-color: #fff;
    border-radius: 14px;
  }
  .vcard .qr-panel img {
    display: block;
    width: 100%;
    height: auto;
    aspect-ratio: 1;
  }
  .vcard .qr-name {
    margin-top: 14px;
    color: #000;
    font-size: 1.05rem;
    font-weight: 500;
    letter-spacing: 0.04em;
    text-transform: uppercase;
  }
  .vcard .qr-caption {
    padding: 12px 0 14px 0;
    color: #fff;
    font-size: 1.1rem;
    font-weight: 500;
    letter-spacing: 0.04em;
    text-transform: uppercase;
  }
  .vcard .btn-appointment {
    background-color: var(--global-theme-fill-color);
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
  <div class="qr-card">
    <div class="qr-panel">
      <img src="{{ '/assets/img/contact-qr.svg' | relative_url }}" alt="vCard QR code for Dr. Hafizul Abdullah">
      <div class="qr-name">Dr. Hafizul Abdullah</div>
    </div>
    <div class="qr-caption">Scan to save my contact</div>
  </div>

  <a class="btn-appointment" href="https://calendar.google.com/calendar/appointments/AcZssZ0ct9pezfkSREcf1EtOf3vrDOFKKMIcQITPDpQ=" target="_blank" rel="noopener noreferrer">
    Book Appointment
  </a>
</div>
