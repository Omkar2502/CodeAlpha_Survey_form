# CodeAlpha_Survey_form
<!DOCTYPE html>
<html>
<head>
  <title>Multi-Page Survey</title>
  <style>
    /* Add your custom styles here */
    /* For simplicity, we won't focus much on styling in this example */
    .page {
      display: none;
    }
    .active-page {
      display: block;
    }
  </style>
</head>
<body>
  <div id="page1" class="page active-page">
    <h1>Page 1</h1>
    <form onsubmit="saveData(1); return false;">
      <label>Question 1:</label>
      <input type="text" id="q1" required><br>

      <!-- Add more questions for Page 1 as needed -->

      <button onclick="saveData(1)">Next</button>
    </form>
  </div>

  <div id="page2" class="page">
    <h1>Page 2</h1>
    <form onsubmit="saveData(2); return false;">
      <label>Question 4:</label>
      <input type="text" id="q4" required><br>

      <!-- Add more questions for Page 2 as needed -->

      <button onclick="saveData(2)">Next</button>
    </form>
  </div>

  <div id="page3" class="page">
    <h1>Page 3</h1>
    <form onsubmit="submitSurvey(); return false;">
      <label>Question 7:</label>
      <input type="text" id="q7" required><br>

      <!-- Add more questions for Page 3 as needed -->

      <button onclick="saveData(3)">Previous</button>
      <button onclick="submitSurvey()">Submit</button>
    </form>
  </div>

  <div id="result-page" class="page">
    <h1>Survey Results</h1>
    <div id="survey-results"></div>
  </div>

  <script>
    function saveData(pageNumber) {
      // Save data to localStorage based on the current page number
      // ...

      // Go to the next page
      // ...
    }

    function submitSurvey() {
      // Save data from the last page (Page 3) to localStorage
      // ...

      // Retrieve and format data from all pages
      // ...

      // Send the survey data to the server using AJAX or form submission
      // Replace the following with your server-side endpoint and method (e.g., PHP, Node.js, etc.).
      const serverEndpoint = 'your_server_endpoint_here';

      const surveyData = {
        q1: localStorage.getItem('q1'),
        q2: localStorage.getItem('q2'),
        q3: localStorage.getItem('q3'),
        // Add more items for all questions
      };

      // Sending data to the server using AJAX
      const xhr = new XMLHttpRequest();
      xhr.open('POST', serverEndpoint, true);
      xhr.setRequestHeader('Content-Type', 'application/json');
      xhr.onreadystatechange = function() {
        if (xhr.readyState === XMLHttpRequest.DONE) {
          if (xhr.status === 200) {
            // Handle successful submission
            console.log('Survey data submitted successfully.');
          } else {
            // Handle submission error
            console.error('Error submitting survey data.');
          }
        }
      };
      xhr.send(JSON.stringify(surveyData));

      // You can also use other methods like Fetch API, jQuery AJAX, etc.

      // Display the survey results on the result page (optional)
      // ...
    }
  </script>
</body>
</html>
