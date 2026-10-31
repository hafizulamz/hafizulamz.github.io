---
layout: page
title: UTAR CGPA calculator
permalink: /utilities/utar-cgpa-calculator/
description: estimate your trimester GPA and cumulative CGPA using the UTAR grading scale.
nav: false
---

<style>
  .cgpa-card {
    max-width: 560px;
    margin-top: 1rem;
  }
  .cgpa-card label {
    display: block;
    margin-bottom: 6px;
    color: var(--global-text-color);
  }
  .cgpa-card select,
  .cgpa-card input[type="number"] {
    width: 100%;
    padding: 10px;
    border-radius: 6px;
    border: 1px solid var(--global-divider-color);
    font-size: 16px;
    background-color: var(--global-bg-color);
    color: var(--global-text-color);
  }
  .cgpa-card input.invalid,
  .cgpa-card select.invalid {
    border: 2px solid #e03131 !important;
  }
  .cgpa-card .radio-group {
    margin-bottom: 15px;
  }
  .cgpa-card .radio-group label {
    display: inline-block;
    margin-right: 15px;
    color: var(--global-text-color);
    cursor: pointer;
  }
  .cgpa-card .radio-group label:first-child,
  .cgpa-card .instruction,
  .cgpa-card .subject-label {
    font-size: 1.125rem;
    font-weight: 400;
  }
  .cgpa-card .radio-group label:first-child {
    display: block;
  }
  .cgpa-card .prev-row {
    display: flex;
    gap: 15px;
    align-items: flex-end;
  }
  .cgpa-card .prev-row > div {
    flex: 1;
  }
  .cgpa-card .instruction {
    margin-bottom: 0;
  }
  .cgpa-card .link-btn {
    padding: 0;
    border: 0;
    background: none;
    font: inherit;
    color: var(--global-theme-color);
    cursor: pointer;
  }
  .cgpa-card .link-btn:hover {
    text-decoration: underline;
  }
  .cgpa-card .course-row {
    margin-top: 15px;
    border-top: 1px solid var(--global-divider-color);
    padding-top: 15px;
  }
  .cgpa-card .subject-label {
    margin-bottom: 6px;
  }
  .cgpa-card .course-inputs {
    display: flex;
    gap: 10px;
    align-items: flex-start;
  }
  .cgpa-card .course-inputs > div {
    flex: 1;
  }
  .cgpa-card .button-row {
    display: flex;
    gap: 10px;
    margin-top: 20px;
    flex-wrap: wrap;
  }
  .cgpa-btn {
    cursor: pointer;
    border: 1px solid var(--global-theme-color);
    border-radius: 6px;
    font-size: 1rem;
    padding: 10px 16px;
    background-color: transparent;
    color: var(--global-theme-color);
  }
  .cgpa-btn:hover {
    opacity: 0.85;
  }
  .cgpa-btn.add {
    flex: 1 1 160px;
  }
  .cgpa-btn.reset {
    flex: 0 1 auto;
    border-color: var(--global-divider-color);
    color: var(--global-text-color-light);
  }
  .cgpa-btn.calculate {
    flex: 1 1 100%;
    background-color: var(--global-theme-color);
    color: #fff;
  }
  .cgpa-card .result {
    margin-top: 20px;
    font-size: 1.1rem;
    padding: 12px 16px;
    border-radius: 6px;
    min-height: 28px;
  }
  .cgpa-card .result:empty {
    display: none;
  }
  .cgpa-card .result.error {
    color: #e03131;
    background-color: rgba(224, 49, 49, 0.1);
    border: 1px solid #e03131;
  }
  .cgpa-card .result.success {
    color: var(--global-text-color);
    background-color: color-mix(in srgb, var(--global-theme-color) 12%, transparent);
  }
  .cgpa-card .result.success strong {
    color: var(--global-theme-color);
  }
  .cgpa-card .warning-message {
    margin-top: 12px;
    padding: 10px;
    border-radius: 6px;
    background-color: #e03131;
    color: #fff;
    font-size: 14px;
  }
  .cgpa-card .footer-links {
    margin-top: 18px;
  }
  .cgpa-card .footer-links .sep {
    color: var(--global-text-color-light);
    margin: 0 0.5rem;
  }
  #modal-bg {
    position: fixed;
    inset: 0;
    background-color: rgba(0, 0, 0, 0.6);
    display: none;
    justify-content: center;
    align-items: center;
    z-index: 1050;
    padding: 16px;
  }
  #modal {
    background-color: var(--global-card-bg-color);
    color: var(--global-text-color);
    border: 2px solid var(--global-theme-color);
    padding: 20px 25px;
    border-radius: 12px;
    max-width: 380px;
    width: 100%;
    text-align: left;
    position: relative;
  }
  #modal h3 {
    font-size: 1.2em;
    color: var(--global-theme-color);
    margin-top: 0;
  }
  #modal table {
    width: 100%;
    border-collapse: collapse;
    margin: 10px 0;
  }
  #modal th,
  #modal td {
    border: 1px solid var(--global-divider-color);
    padding: 6px 8px;
    text-align: center;
  }
  #modal button.close-btn {
    position: absolute;
    top: 8px;
    right: 10px;
    background: transparent;
    border: none;
    color: var(--global-theme-color);
    font-size: 20px;
    cursor: pointer;
  }
</style>

<div class="cgpa-card">
  <div class="radio-group">
    <label>Is this your first trimester?</label>
    <label><input type="radio" name="firstSem" value="yes" checked /> Yes</label>
    <label><input type="radio" name="firstSem" value="no" /> No</label>
  </div>
  <div id="prev-info" style="display:none; margin-bottom: 15px;">
    <div class="prev-row">
      <div>
        <label for="prev-cgpa">Current CGPA</label>
        <input type="number" id="prev-cgpa" step="0.01" min="0" max="4" placeholder="e.g. 3.50" />
      </div>
      <div>
        <label for="prev-credits">Total Credits Taken</label>
        <input type="number" id="prev-credits" step="1" min="0" placeholder="e.g. 40" />
      </div>
    </div>
  </div>
  <div id="course-container">
    <p class="instruction">Enter your target grade for each course this trimester.</p>
    <div class="course-row">
      <div class="subject-label">Course 1</div>
      <div class="course-inputs">
        <div>
          <label>Targeted Grade</label>
          <select class="grade" required>
            <option value="" disabled selected>Select Grade</option>
            <option value="4">A+</option>
            <option value="4">A</option>
            <option value="3.67">A-</option>
            <option value="3.33">B+</option>
            <option value="3">B</option>
            <option value="2.67">B-</option>
            <option value="2.33">C+</option>
            <option value="2">C</option>
            <option value="0">F</option>
          </select>
        </div>
        <div>
          <label>Credit Hours</label>
          <input type="number" step="1" min="1" max="10" class="credit" placeholder="e.g. 3" required />
        </div>
      </div>
    </div>
  </div>
  <div class="button-row">
    <button class="cgpa-btn add" onclick="addCourse()">+ Add Another Course</button>
    <button class="cgpa-btn reset" onclick="resetCalculator()">Reset</button>
    <button class="cgpa-btn calculate" onclick="calculateCGPA()">Calculate CGPA</button>
  </div>
  <div id="result" class="result" aria-live="polite"></div>
  <div class="footer-links">
    <button type="button" id="info-icon" class="link-btn">See the UTAR grade table</button>
    <span class="sep" aria-hidden="true">&middot;</span>
    <a href="#" id="report-issues">Report an issue</a>
  </div>
</div>

<!-- Modal for grade conversion -->
<div id="modal-bg">
  <div id="modal" role="dialog" aria-modal="true" aria-labelledby="modal-title">
    <button class="close-btn" aria-label="Close">&times;</button>
    <h3 id="modal-title">UTAR Grade Conversion Table</h3>
    <p>This grade conversion table is used at Universiti Tunku Abdul Rahman (UTAR).</p>
    <table>
      <thead>
        <tr><th>Grade</th><th>Marks</th><th>Points</th></tr>
      </thead>
      <tbody>
        <tr><td>A+</td><td>90-100</td><td>4</td></tr>
        <tr><td>A</td><td>80-89</td><td>4</td></tr>
        <tr><td>A-</td><td>75-79</td><td>3.67</td></tr>
        <tr><td>B+</td><td>70-74</td><td>3.33</td></tr>
        <tr><td>B</td><td>65-69</td><td>3</td></tr>
        <tr><td>B-</td><td>60-64</td><td>2.67</td></tr>
        <tr><td>C+</td><td>55-59</td><td>2.33</td></tr>
        <tr><td>C</td><td>50-54</td><td>2</td></tr>
        <tr><td>F</td><td>0-49</td><td>0</td></tr>
      </tbody>
    </table>
    <p>This CGPA calculator is for guidance only. For assistance, book an appointment:</p>
    <a class="cgpa-btn add" href="/contact/" style="display:inline-block; text-decoration:none;">Book Appointment</a>
  </div>
</div>

<script>
  const firstSemRadios = document.getElementsByName('firstSem');
  const prevInfo = document.getElementById('prev-info');
  const prevCgpaInput = document.getElementById('prev-cgpa');
  const prevCreditsInput = document.getElementById('prev-credits');
  const courseContainer = document.getElementById('course-container');
  const reportIssuesLink = document.getElementById('report-issues');
  const resultDiv = document.getElementById('result');
  // Modal elements
  const modalBg = document.getElementById('modal-bg');
  const modal = document.getElementById('modal');
  const infoIcon = document.getElementById('info-icon');
  const closeModalBtn = modal.querySelector('.close-btn');
  // Show or hide previous trimester input section
  function togglePrevInfo() {
    if (document.querySelector('input[name="firstSem"]:checked').value === 'no') {
      prevInfo.style.display = 'block';
      prevCgpaInput.required = true;
      prevCreditsInput.required = true;
    } else {
      prevInfo.style.display = 'none';
      prevCgpaInput.required = false;
      prevCreditsInput.required = false;
      prevCgpaInput.value = '';
      prevCreditsInput.value = '';
      clearInvalidHighlights();
      enableFirstSemRadios(true);
    }
  }
  // Enable or disable first trimester radio buttons
  function enableFirstSemRadios(enable) {
    firstSemRadios.forEach(radio => {
      radio.disabled = !enable;
    });
  }
  // When previous inputs have values, adjust first trimester radio buttons accordingly
  function checkPrevInputs() {
    if (prevCgpaInput.value.trim() !== '' || prevCreditsInput.value.trim() !== '') {
      firstSemRadios.forEach(radio => {
        if (radio.value === 'yes') {
          radio.checked = false;
          radio.disabled = true;
        }
        if (radio.value === 'no') {
          radio.checked = true;
          radio.disabled = false;
        }
      });
      togglePrevInfo();
    } else {
      enableFirstSemRadios(true);
    }
  }
  // Clear invalid input highlights
  function clearInvalidHighlights() {
    document.querySelectorAll('.cgpa-card input, .cgpa-card select').forEach(el => {
      el.classList.remove('invalid');
    });
  }
  // Add new course input row
  function addCourse() {
    const count = courseContainer.querySelectorAll('.course-row').length + 1;
    const div = document.createElement('div');
    div.className = 'course-row';
    div.innerHTML = `
      <div class="subject-label">Course ${count}</div>
      <div class="course-inputs">
        <div>
          <label>Targeted Grade</label>
          <select class="grade" required>
            <option value="" disabled selected>Select Grade</option>
            <option value="4">A+</option>
            <option value="4">A</option>
            <option value="3.67">A-</option>
            <option value="3.33">B+</option>
            <option value="3">B</option>
            <option value="2.67">B-</option>
            <option value="2.33">C+</option>
            <option value="2">C</option>
            <option value="0">F</option>
          </select>
        </div>
        <div>
          <label>Credit Hours</label>
          <input type="number" step="1" min="1" max="10" class="credit" placeholder="e.g. 3" required />
        </div>
      </div>`;
    courseContainer.appendChild(div);
  }
  // Reset the entire calculator form and results
  function resetCalculator() {
    document.querySelector('input[name="firstSem"][value="yes"]').checked = true;
    togglePrevInfo();
    prevCgpaInput.value = '';
    prevCreditsInput.value = '';
    // Remove all additional courses except first
    const courses = courseContainer.querySelectorAll('.course-row');
    for (let i = courses.length - 1; i >= 1; i--) {
      courses[i].remove();
    }
    courseContainer.querySelector('.grade').value = '';
    courseContainer.querySelector('.credit').value = '';
    clearInvalidHighlights();
    resultDiv.textContent = '';
    resultDiv.classList.remove('error', 'success');
  }
  // Calculate CGPA and show results + warning if below 2
  function calculateCGPA() {
    clearInvalidHighlights();
    resultDiv.classList.remove('error', 'success');
    const grades = document.querySelectorAll('.grade');
    const credits = document.querySelectorAll('.credit');
    let totalPoints = 0;
    let totalCredits = 0;
    for (let i = 0; i < grades.length; i++) {
      const gradeSelect = grades[i];
      const creditInput = credits[i];
      const gradeValue = gradeSelect.value;
      const creditValue = creditInput.value.trim();
      if (!gradeValue) {
        gradeSelect.classList.add('invalid');
        resultDiv.classList.add('error');
        resultDiv.textContent = 'Please select a grade for each course.';
        gradeSelect.focus();
        return;
      }
      const creditNum = parseFloat(creditValue);
      if (creditValue === '' || isNaN(creditNum) || creditNum <= 0 || creditNum > 10) {
        creditInput.classList.add('invalid');
        resultDiv.classList.add('error');
        resultDiv.textContent = 'Please enter valid credit hours (1-10) for each course.';
        creditInput.focus();
        return;
      }
      totalPoints += parseFloat(gradeValue) * creditNum;
      totalCredits += creditNum;
    }
    if (totalCredits === 0) {
      resultDiv.classList.add('error');
      resultDiv.textContent = 'Please enter at least one course with credit hours.';
      return;
    }
    const currentTrimesterGPA = totalPoints / totalCredits;
    let cumulativeCgpa = currentTrimesterGPA;
    if (document.querySelector('input[name="firstSem"]:checked').value === 'no') {
      const prevCgpaValue = prevCgpaInput.value.trim();
      const prevCreditsValue = prevCreditsInput.value.trim();
      const prevCgpa = parseFloat(prevCgpaValue);
      const prevCredits = parseFloat(prevCreditsValue);
      if (prevCgpaValue === '' || isNaN(prevCgpa) || prevCgpa < 0 || prevCgpa > 4) {
        prevCgpaInput.classList.add('invalid');
        resultDiv.classList.add('error');
        resultDiv.textContent = 'Please enter a valid current CGPA between 0 and 4.';
        prevCgpaInput.focus();
        return;
      }
      if (prevCreditsValue === '' || isNaN(prevCredits) || prevCredits < 0) {
        prevCreditsInput.classList.add('invalid');
        resultDiv.classList.add('error');
        resultDiv.textContent = 'Please enter valid total credits taken (0 or more).';
        prevCreditsInput.focus();
        return;
      }
      cumulativeCgpa = (prevCgpa * prevCredits + totalPoints) / (prevCredits + totalCredits);
    }
    let warningMessage = '';
    if (currentTrimesterGPA < 2 || cumulativeCgpa < 2) {
      warningMessage = '<div class="warning-message">⚠️ Reminder: Targeted GPA/CGPA is below 2. Please strive to maintain a CGPA above 2 for good academic standing.</div>';
    }
    resultDiv.classList.add('success');
    resultDiv.innerHTML = `Targeted Trimester GPA: <strong>${currentTrimesterGPA.toFixed(2)}</strong><br>Targeted Cumulative CGPA: <strong>${cumulativeCgpa.toFixed(2)}</strong>${warningMessage}`;
  }
  // Event listeners for radio and previous inputs
  firstSemRadios.forEach(radio => {
    radio.addEventListener('change', togglePrevInfo);
  });
  prevCgpaInput.addEventListener('input', checkPrevInputs);
  prevCreditsInput.addEventListener('input', checkPrevInputs);
  togglePrevInfo();
  // Report issue link email protection
  reportIssuesLink.addEventListener('click', function (event) {
    event.preventDefault();
    const email = 'hafizulafifi' + '@' + 'utar.edu.my';
    const subject = encodeURIComponent('CGPA Calculator Issue Report');
    const body = encodeURIComponent('Please describe the issue you faced:');
    window.location.href = `mailto:${email}?subject=${subject}&body=${body}`;
  });
  // Modal open/close handlers
  infoIcon.addEventListener('click', () => {
    modalBg.style.display = 'flex';
  });
  closeModalBtn.addEventListener('click', () => {
    modalBg.style.display = 'none';
  });
  modalBg.addEventListener('click', e => {
    if (e.target === modalBg) {
      modalBg.style.display = 'none';
    }
  });
  document.addEventListener('keydown', e => {
    if (e.key === 'Escape') {
      modalBg.style.display = 'none';
    }
  });
</script>
