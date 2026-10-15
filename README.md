# privacy-risk-shield
A security awareness companion for whatsapp users
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Privacy Risk Shield</title>
<style>
* { box-sizing: border-box; }
body {
  margin: 0;
  font-family: Arial, sans-serif;
  background: #f1f6f5;
  color: #173b38;
}
header {
  background: #103e39;
  color: white;
  padding: 24px 18px;
  border-radius: 0 0 24px 24px;
}
header h1 { margin: 0 0 8px; }
header p { margin: 0; color: #d4e9e4; }
main { padding: 18px; max-width: 650px; margin: auto; }
.score {
  background: white;
  padding: 20px;
  border-radius: 18px;
  margin: 18px 0;
  box-shadow: 0 3px 12px #173b3810;
}
.score strong { font-size: 34px; color: #16816b; }
.item {
  background: white;
  margin: 12px 0;
  padding: 16px;
  border-radius: 14px;
}
.item h3 { margin: 0 0 8px; }
.item p { line-height: 1.5; color: #526763; }
button {
  background: #167c68;
  color: white;
  padding: 12px 16px;
  border: 0;
  border-radius: 9px;
  font-size: 15px;
  cursor: pointer;
}
.result { margin-top: 10px; font-weight: bold; }
footer { text-align: center; padding: 22px; font-size: 12px; color: #526763; }
</style>
</head>
<body>
<header>
  <h1>🛡️ Privacy Risk Shield</h1>
  <p>Your personal digital safety companion</p>
</header>

<main>
  <h2>Security Dashboard</h2>
  <p>Take a few simple steps to improve your account safety.</p>

  <section class="score">
    <p>Your self-check progress</p>
    <strong id="score">0%</strong>
    <p id="progress">0 of 4 checks completed</p>
  </section>

  <section class="item">
    <h3>📱 Linked Devices</h3>
    <p>Review devices connected to your WhatsApp account. Log out of any you don't recognise.</p>
    <button onclick="check(this)">Mark as reviewed</button>
    <div class="result"></div>
  </section>

  <section class="item">
    <h3>🔐 Two-step Verification</h3>
    <p>Check WhatsApp Settings → Account → Two-step verification.</p>
    <button onclick="check(this)">Mark as reviewed</button>
    <div class="result"></div>
  </section>

  <section class="item">
    <h3>⚠️ Verification Code Safety</h3>
    <p>Never share your SMS registration code or two-step verification PIN with anyone.</p>
    <button onclick="check(this)">I understand</button>
    <div class="result"></div>
  </section>

  <section class="item">
    <h3>☁️ Chat Backup Privacy</h3>
    <p>Review your chat backup settings and learn about end-to-end encrypted backups.</p>
    <button onclick="check(this)">Mark as reviewed</button>
    <div class="result"></div>
  </section>

  <section class="item">
    <h3>🚨 Suspicious Message?</h3>
    <p>Unexpected prizes, urgent requests for money, and links asking for personal details can be warning signs.</p>
    <button onclick="alert('Do not share codes or passwords. Verify the sender independently. Block and report suspicious accounts when appropriate.')">View safety advice</button>
  </section>

  <footer>
    Independent educational prototype · Not affiliated with WhatsApp.
    <br>Checks are self-reported and do not scan your account.
  </footer>
</main>

<script>
let completed = 0;

function check(button) {
  if (button.dataset.done === "yes") return;

  button.dataset.done = "yes";
  button.textContent = "✓ Reviewed";
  button.style.background = "#526763";
  button.nextElementSibling.textContent =
    "Completed — remember to verify the setting in WhatsApp.";

  completed++;
  document.getElementById("score").textContent =
    Math.round(completed / 4 * 100) + "%";
  document.getElementById("progress").textContent =
    completed + " of 4 checks completed";
}
</script>
</body>
</html>