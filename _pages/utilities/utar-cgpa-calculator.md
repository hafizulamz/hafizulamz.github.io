---
layout:
title: "UTAR CGPA Calculator | Mohd Hafizul Afifi Abdullah"
permalink: /utilities/utar-cgpa-calculator/
subtitle: false
---

<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1" />
    <link rel="shortcut icon" href="/assets/img/favicon.ico">
    <title>UTAR CGPA Calculator | Mohd Hafizul Afifi Abdullah</title>
    <style>
      body {
        font-family: Arial, sans-serif;
        display: flex;
        justify-content: center;
        align-items: flex-start;
        padding: 40px 0;
        min-height: 100vh;
        background-color: #121212;
        color: #fff;
        margin: 0;
      }

      .card {
        background: #1e1e1e;
        padding: 25px 25px 35px;
        border-radius: 10px;
        box-shadow: 0 4px 8px rgba(255, 255, 255, 0.1);
        max-width: 420px;
        width: 100%;
        text-align: center;
        position: relative;
      }

      .card h2 {
        margin-bottom: 20px;
        color: #fff;
        display: inline-block;
      }

      /* Info icon */
      #info-icon {
        cursor: pointer;
        position: absolute;
        top: 25px;
        right: 25px;
        font-size: 20px;
        color: #2698ba;
        user-select: none;
        transition: color 0.3s ease;
      }

      #info-icon:hover {
        color: #1b7087;
      }

      label {
        display: block;
        margin-bottom: 6px;
        text-align: left;
        color: #aaa;
        font-weight: bold;
      }

      select,
      input[type="number"] {
        width: 100%;
        padding: 10px;
        border-radius: 5px;
        border: none;
        font-size: 16px;
        box-sizing: border-box;
        background-color: #121212;
        color: #fff;
        transition: border-color 0.3s ease;
      }

      select option[disabled] {
        color: #666;
      }

      input.invalid,
      select.invalid {
        border: 2px solid #ff5555 !important;
        background-color: #3a1a1a;
      }

      .radio-group {
        text-align: left;
        margin-bottom: 15px;
      }

      .radio-group label {
        display: inline-block;
        margin-right: 15px;
        font-weight: normal;
        color: #ccc;
        cursor: pointer;
      }

      /* Buttons container */
      .button-row {
        display: flex;
        gap: 10px;
        margin-top: 10px;
        flex-wrap: wrap;
        justify-content: center;
      }

      .add-course-button,
      .reset-button,
      .calculate-button {
        cursor: pointer;
        border: 0;
        border-radius: 5px;
        font-size: 14px;
        font-weight: bold;
        padding: 10px 15px;
        color: white !important;
        transition: background-color 0.3s ease;
        flex-shrink: 0;
      }

      .add-course-button {
        background: #2698ba;
        flex: 1 1 140px;
      }

      .add-course-button:hover {
        background: #1b7087;
      }

      .reset-button {
        background-color: #555555;
        flex: 1 1 100px;
      }

      .reset-button:hover {
        background-color: #777777;
      }

      .calculate-button {
        background: #00264d;
        flex: 2 1 160px;
      }

      .calculate-button:hover {
        background: #0a3d62;
      }

      .result {
        margin-top: 22px;
        font-size: 18px;
        font-weight: bold;
        padding: 10px;
        border-radius: 6px;
        text-align: center;
        min-height: 28px;
      }

      /* Error message style */
      .result.error {
        color: #ff5555;
        background-color: #3a1a1a;
        border: 1px solid #ff4444;
      }

      /* Success message style */
      .result.success {
        color: #2698ba;
        background-color: #142f44;
        border: 1px solid #1b7087;
      }

      .back-home,
      .report-issues {
        display: block;
        margin-top: 6px;
        font-size: 14px;
        font-weight: bold;
        cursor: pointer;
        text-decoration: none;
        transition: color 0.3s ease;
        text-align: center;
      }

      .back-home {
        color: #2698ba;
      }

      .back-home:hover {
        text-decoration: underline;
      }

      .report-issues {
        color: #ba2626;
        margin-top: 0;
        /* reduce gap between links */
      }

      .report-issues:hover {
        text-decoration: underline;
      }

      .course-row {
        margin-top: 15px;
        border-top: 1px solid #444;
        padding-top: 15px;
        text-align: left;
      }

      .subject-label {
        font-weight: bold;
        color: #ccc;
        margin-bottom: 6px;
      }

      .course-inputs {
        display: flex;
        gap: 10px;
        align-items: flex-start;
      }

      .course-inputs>div {
        flex: 1;
      }

      /* Styled instruction */
      .instruction {
        background-color: #222;
        color: #8ecae6;
        padding: 12px 15px;
        border-radius: 6px;
        font-size: 14px;
        font-style: italic;
        margin-bottom: 15px;
        text-align: left;
      }

      /* Warning message style */
      .warning-message {
        margin-top: 12px;
        padding: 10px;
        border-radius: 6px;
        background-color: #ff4444;
        color: #fff;
        font-weight: bold;
        font-size: 14px;
      }

      /* Modal styles */
      #modal-bg {
        position: fixed;
        top: 0;
        left: 0;
        right: 0;
        bottom: 0;
        background-color: rgba(0, 0, 0, 0.7);
        display: none;
        justify-content: center;
        align-items: center;
        z-index: 1000;
      }

      #modal {
        background-color: #222;
        padding: 20px 25px;
        border-radius: 10px;
        max-width: 360px;
        color: #ccc;
        text-align: left;
        box-shadow: 0 0 10px #2698ba;
        position: relative;
      }

      #modal h3 {
        color: #2698ba;
        margin-top: 0;
      }

      #modal table {
        width: 100%;
        border-collapse: collapse;
        margin-top: 10px;
      }

      #modal th,
      #modal td {
        border: 1px solid #555;
        padding: 6px 8px;
        text-align: center;
      }

      #modal th {
        background-color: #1e1e1e;
      }

      #modal button.close-btn {
        position: absolute;
        top: 8px;
        right: 8px;
        background: transparent;
        border: none;
        color: #2698ba;
        font-size: 18px;
        cursor: pointer;
        font-weight: bold;
      }

      #modal button.close-btn:hover {
        color: #1b7087;
      }
    </style>
  </head>
  <body>
    <div class="card">
      <h2>UTAR CGPA Calculator</h2>
      <span id="info-icon" title="Grade Conversion Table">&#9432;</span>
      <div class="radio-group">
        <label>Is this your first semester?</label>
        <label>
          <input type="radio" name="firstSem" value="yes" checked /> Yes </label>
        <label>
          <input type="radio" name="firstSem" value="no" /> No </label>
      </div>
      <div id="prev-info" style="display:none; margin-bottom: 15px;">
        <div style="display: flex; gap: 15px;">
          <div style="flex: 1;">
            <label for="prev-cgpa">Previous Semester CGPA</label>
            <input type="number" id="prev-cgpa" step="0.01" min="0" max="4" placeholder="e.g. 3.50" />
          </div>
          <div style="flex: 1;">
            <label for="prev-credits">Total Credits Taken</label>
            <input type="number" id="prev-credits" step="1" min="0" placeholder="e.g. 40" />
          </div>
        </div>
      </div>
      <p class="instruction">Enter your current semester grades and credit hours below:</p>
      <div id="course-container">
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
        <button class="add-course-button" onclick="addCourse()">+ Add Another Course</button>
        <button class="reset-button" onclick="resetCalculator()">Reset</button>
        <button class="calculate-button" onclick="calculateCGPA()">Calculate CGPA</button>
      </div>
      <div id="result" class="result"></div>
      <a href="http://hafizulabdullah.com/" class="back-home" rel="external nofollow noopener" target="_blank">← Back to Homepage</a>
      <a href="#" id="report-issues" class="report-issues">Report Issues</a>
    </div>
    <!-- Modal for grade conversion -->
    <div id="modal-bg">
      <div id="modal" role="dialog" aria-modal="true" aria-labelledby="modal-title">
        <button class="close-btn" aria-label="Close">&times;</button>
        <h3 id="modal-title">UTAR Grade Conversion Table</h3>
        <p>This grade conversion table is used at Universiti Tunku Abdul Rahman (UTAR)</p>
        <table>
          <thead>
            <tr>
              <th>Grade</th>
              <th>Marks</th>
              <th>Points</th>
            </tr>
          </thead>
          <tbody>
            <tr>
              <td>A+</td>
              <td>90-100</td>
              <td>4</td>
            </tr>
            <tr>
              <td>A</td>
              <td>80-89</td>
              <td>4</td>
            </tr>
            <tr>
              <td>A-</td>
              <td>75-79</td>
              <td>3.67</td>
            </tr>
            <tr>
              <td>B+</td>
              <td>70-74</td>
              <td>3.33</td>
            </tr>
            <tr>
              <td>B</td>
              <td>65-69</td>
              <td>3</td>
            </tr>
            <tr>
              <td>B-</td>
              <td>60-64</td>
              <td>2.67</td>
            </tr>
            <tr>
              <td>C+</td>
              <td>55-59</td>
              <td>2.33</td>
            </tr>
            <tr>
              <td>C</td>
              <td>50-54</td>
              <td>2</td>
            </tr>
            <tr>
              <td>F</td>
              <td>0-49</td>
              <td>0</td>
            </tr>
          </tbody>
        </table>
        <p>This CGPA calculator is for guidance only. To get assistance, click the button below:</p>
        <button class="add-course-button" onclick="window.open('https://hafizulabdullah.com/contact/', '_blank', 'noopener,noreferrer')"> Schedule Appointment </button>
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
      // Show or hide previous semester input section
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
      // Enable or disable first semester radio buttons
      function enableFirstSemRadios(enable) {
        firstSemRadios.forEach(radio => {
          radio.disabled = !enable;
        });
      }
      // When previous inputs have values, adjust first semester radio buttons accordingly
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
        document.querySelectorAll('input, select').forEach(el => {
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
				</div>
    `;
        courseContainer.appendChild(div);
      }
      // Reset the entire calculator form and results
      function resetCalculator() {
        // Reset semester radio
        document.querySelector('input[name="firstSem"][value="yes"]').checked = true;
        togglePrevInfo();
        // Clear previous CGPA and credits
        prevCgpaInput.value = '';
        prevCreditsInput.value = '';
        // Remove all additional courses except first
        const courses = courseContainer.querySelectorAll('.course-row');
        for (let i = courses.length - 1; i >= 1; i--) {
          courses[i].remove();
        }
        // Reset first course inputs
        const firstGrade = courseContainer.querySelector('.grade');
        const firstCredit = courseContainer.querySelector('.credit');
        firstGrade.value = '';
        firstCredit.value = '';
        clearInvalidHighlights();
        // Clear result
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
          } else {
            gradeSelect.classList.remove('invalid');
          }
          const creditNum = parseFloat(creditValue);
          if (creditValue === "" || isNaN(creditNum) || creditNum <= 0 || creditNum > 10) {
            creditInput.classList.add('invalid');
            resultDiv.classList.add('error');
            resultDiv.textContent = 'Please enter valid credit hours (1-10) for each course.';
            creditInput.focus();
            return;
          } else {
            creditInput.classList.remove('invalid');
          }
          totalPoints += parseFloat(gradeValue) * creditNum;
          totalCredits += creditNum;
        }
        if (totalCredits === 0) {
          resultDiv.classList.add('error');
          resultDiv.textContent = 'Please enter at least one course with credit hours.';
          return;
        }
        let currentSemesterGPA = totalPoints / totalCredits;
        let cumulativeCgpa = currentSemesterGPA;
        if (document.querySelector('input[name="firstSem"]:checked').value === 'no') {
          const prevCgpaValue = prevCgpaInput.value.trim();
          const prevCreditsValue = prevCreditsInput.value.trim();
          prevCgpaInput.classList.remove('invalid');
          prevCreditsInput.classList.remove('invalid');
          let prevCgpa = parseFloat(prevCgpaValue);
          let prevCredits = parseFloat(prevCreditsValue);
          if (prevCgpaValue === "" || isNaN(prevCgpa) || prevCgpa < 0 || prevCgpa > 4) {
            prevCgpaInput.classList.add('invalid');
            resultDiv.classList.add('error');
            resultDiv.textContent = 'Please enter a valid Previous Semester CGPA between 0 and 4.';
            prevCgpaInput.focus();
            return;
          }
          if (prevCreditsValue === "" || isNaN(prevCredits) || prevCredits < 0) {
            prevCreditsInput.classList.add('invalid');
            resultDiv.classList.add('error');
            resultDiv.textContent = 'Please enter valid Previous Credits (0 or more).';
            prevCreditsInput.focus();
            return;
          }
          cumulativeCgpa = ((prevCgpa * prevCredits) + totalPoints) / (prevCredits + totalCredits);
        }
        // Warning if below 2
        let warningMessage = '';
        if (currentSemesterGPA < 2 || cumulativeCgpa < 2) {
          warningMessage = `
				
				<div class="warning-message">⚠️ Reminder: Your GPA/CGPA is below 2. Please strive to maintain a GPA above 2 for good academic standing.</div>`;
        }
        resultDiv.classList.remove('error');
        resultDiv.classList.add('success');
        resultDiv.innerHTML = `
      Your Current Semester GPA is: 
				
				<strong>${currentSemesterGPA.toFixed(2)}</strong>
				<br>
      Your Cumulative CGPA is: 
					
					<strong>${cumulativeCgpa.toFixed(2)}</strong>
      ${warningMessage}
    `;
      }
      // Event listeners for radio and previous inputs
      firstSemRadios.forEach(radio => {
        radio.addEventListener('change', togglePrevInfo);
      });
      prevCgpaInput.addEventListener('input', checkPrevInputs);
      prevCreditsInput.addEventListener('input', checkPrevInputs);
      // Initial toggle
      togglePrevInfo();
      // Report issue link email protection
      reportIssuesLink.addEventListener('click', function(event) {
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
      // Close modal if clicking outside modal content
      modalBg.addEventListener('click', (e) => {
        if (e.target === modalBg) {
          modalBg.style.display = 'none';
        }
      });
    </script>
  </body>
</html>