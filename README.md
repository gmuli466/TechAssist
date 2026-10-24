
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>TechAssist | ICT Help Desk</title>
  <style>
    body {
      margin: 0;
      padding: 20px;
      background: #08111f;
      color: #eef5ff;
      font-family: Arial, sans-serif;
    }

    header {
      background: #112944;
      padding: 20px;
      border-radius: 15px;
    }

    h1 { color: #39a0ff; }

    .card {
      background: #111d30;
      border: 1px solid #263852;
      border-radius: 14px;
      padding: 16px;
      margin-top: 18px;
    }

    select, button {
      width: 100%;
      padding: 13px;
      margin-top: 10px;
      border-radius: 9px;
      font-size: 16px;
    }

    select {
      background: #08111f;
      color: white;
      border: 1px solid #39a0ff;
    }

    button {
      background: #2388e8;
      color: white;
      border: none;
      font-weight: bold;
    }

    #result {
      line-height: 1.7;
      color: #c8d7e9;
    }
  </style>
</head>

<body>
  <header>
    <h1>🛠️ TechAssist</h1>
    <p>Your friendly ICT troubleshooting desk.</p>
  </header>

  <div class="card">
    <h2>Diagnose a computer problem</h2>
    <p>Select the problem you're experiencing.</p>

    <select id="problem">
      <option value="slow">Computer is slow</option>
      <option value="wifi">No internet connection</option>
      <option value="power">Computer won't turn on</option>
      <option value="printer">Printer is not printing</option>
    </select>

    <button onclick="diagnose()">Find a solution</button>

    <div id="result" aria-live="polite"></div>
  </div>

  <script>
    function diagnose() {
      const problem =
        document.getElementById("problem").value;

      const result =
        document.getElementById("result");

      const solutions = {
        slow: {
          title: "Computer is running slowly",
          steps: [
            "Save your work.",
            "Close unused apps and browser tabs.",
            "Restart the computer.",
            "Check available storage space."
          ]
        },

        wifi: {
          title: "Internet connection problem",
          steps: [
            "Make sure Wi-Fi is switched on.",
            "Check whether another device can connect.",
            "Reconnect to the correct Wi-Fi network.",
            "Contact the network administrator if needed."
          ]
        },

        power: {
          title: "Computer will not turn on",
          steps: [
            "Check the power socket.",
            "Check that the power cable is connected.",
            "For a laptop, check the charging indicator.",
            "Seek technical help if the device appears damaged."
          ]
        },

        printer: {
          title: "Printer is not printing",
          steps: [
            "Check that the printer is powered on.",
            "Check for paper or ink warnings.",
            "Select the correct printer.",
            "Check the print queue for stuck jobs."
          ]
        }
      };

      const answer = solutions[problem];

      result.innerHTML =
        "<h3>" + answer.title + "</h3><ol>" +
        answer.steps.map(step =>
          "<li>" + step + "</li>"
        ).join("") +
        "</ol>";
    }
  </script>
</body>
</html>
