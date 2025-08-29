<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="utf-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1" />
  
  <title>EMI Calculator – Fast & Simple</title>
  <meta name="description" content="Free EMI calculator for loans: home, car, personal. Calculate monthly EMI, total interest, and total payment instantly." />
  <meta name="keywords" content="EMI calculator, loan calculator, car loan, home loan, personal loan, interest calculator" />
  <meta name="author" content="EMI Calculator Online" />
  <meta name="robots" content="index, follow" />

  <!-- Open Graph (Facebook/LinkedIn) -->
  <meta property="og:title" content="EMI Calculator – Free Loan Calculator" />
  <meta property="og:description" content="Calculate monthly EMI, interest, and total payment instantly with our free EMI calculator." />
  <meta property="og:type" content="website" />
  <meta property="og:url" content="https://proraj894-oss.github.io/Fin-Solve/" />
  <meta property="og:image" content="https://proraj894-oss.github.io/Fin-Solve/preview.png" />

  <!-- Twitter Card -->
  <meta name="twitter:card" content="summary_large_image" />
  <meta name="twitter:title" content="EMI Calculator – Free Loan Calculator" />
  <meta name="twitter:description" content="Calculate your EMI instantly. Works for home, car, and personal loans." />
  <meta name="twitter:image" content="https://proraj894-oss.github.io/Fin-Solve/preview.png" />

  <!-- Favicon -->
  <link rel="icon" href="data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' viewBox='0 0 100 100'%3E%3Ccircle cx='50' cy='50' r='48' fill='%23007bff'/%3E%3Ctext x='50' y='60' font-size='46' text-anchor='middle' fill='white'%3E₹%3C/text%3E%3C/svg%3E" />

  <!-- Google Analytics (replace G-XXXXXXX with your real ID) -->
  <!--
  <script async src="https://www.googletagmanager.com/gtag/js?id=G-XXXXXXX"></script>
  <script>
    window.dataLayer = window.dataLayer || [];
    function gtag(){dataLayer.push(arguments);}
    gtag('js', new Date());
    gtag('config', 'G-XXXXXXX');
  </script>
  -->

  <style>
    /* Keep all your CSS here */
    body { font-family: Arial, sans-serif; margin: 0; padding: 0; background: #f7f9fc; }
    header { background: #0a66c2; color: white; padding: 20px; text-align: center; }
    h1 { margin: 0; }
    section { max-width: 800px; margin: 20px auto; background: white; padding: 20px; border-radius: 10px; box-shadow: 0 2px 6px rgba(0,0,0,0.1);}
    h2 { color: #0a66c2; }
    input, button { padding: 10px; margin: 5px 0; width: 100%; border: 1px solid #ccc; border-radius: 5px; }
    button { background: #0a66c2; color: white; cursor: pointer; }
    button:hover { background: #004080; }
    footer { text-align: center; padding: 15px; background: #0a66c2; color: white; margin-top: 20px; }
  </style>
  <meta name="google-adsense-account" content="ca-pub-8648198938608752">
</head>
<body>

  <header>
    <h1>Fin Solve</h1>
    <p>SIP • GST • Loan Eligibility • EMI Calculator</p>
  </header>

  <!-- SIP Calculator -->
  <section>
    <h2>SIP Calculator</h2>
    <label>Monthly Investment (₹)</label>
    <input type="number" id="sipAmount" placeholder="Enter amount">
    <label>Investment Period (years)</label>
    <input type="number" id="sipYears" placeholder="Enter years">
    <label>Expected Annual Return (%)</label>
    <input type="number" id="sipReturn" placeholder="Enter % return">
    <button onclick="calculateSIP()">Calculate SIP</button>
    <p id="sipResult"></p>
  </section>

  <!-- GST Calculator -->
  <section>
    <h2>GST Calculator</h2>
    <label>Amount (₹)</label>
    <input type="number" id="gstAmount" placeholder="Enter amount">
    <label>GST Rate (%)</label>
    <input type="number" id="gstRate" placeholder="Enter GST %">
    <button onclick="calculateGST()">Calculate GST</button>
    <p id="gstResult"></p>
  </section>

  <!-- Loan Eligibility -->
  <section>
    <h2>Loan Eligibility Calculator</h2>
    <label>Monthly Income (₹)</label>
    <input type="number" id="income" placeholder="Enter income">
    <label>Monthly Expenses (₹)</label>
    <input type="number" id="expenses" placeholder="Enter expenses">
    <button onclick="calculateLoan()">Check Eligibility</button>
    <p id="loanResult"></p>
  </section>

  <!-- EMI Calculator -->
  <section>
    <h2>EMI Calculator</h2>
    <label>Loan Amount (₹)</label>
    <input type="number" id="loanAmount" placeholder="Enter loan amount">
    <label>Annual Interest Rate (%)</label>
    <input type="number" id="interestRate" placeholder="Enter interest rate">
    <label>Loan Tenure (years)</label>
    <input type="number" id="loanYears" placeholder="Enter loan tenure">
    <button onclick="calculateEMI()">Calculate EMI</button>
    <p id="emiResult"></p>
  </section>

  <footer>
    <p>© 2025 Fin Solve | Designed with ❤️</p>
  </footer>

  <script>
    // SIP Calculator
    function calculateSIP() {
      let amount = parseFloat(document.getElementById("sipAmount").value);
      let years = parseFloat(document.getElementById("sipYears").value);
      let rate = parseFloat(document.getElementById("sipReturn").value) / 100 / 12;
      let months = years * 12;
      let maturity = amount * ((Math.pow(1 + rate, months) - 1) / rate) * (1 + rate);
      document.getElementById("sipResult").innerText = "Maturity Value: ₹" + maturity.toFixed(2);
    }

    // GST Calculator
    function calculateGST() {
      let amount = parseFloat(document.getElementById("gstAmount").value);
      let rate = parseFloat(document.getElementById("gstRate").value);
      let gst = (amount * rate) / 100;
      let total = amount + gst;
      document.getElementById("gstResult").innerText = "GST: ₹" + gst.toFixed(2) + " | Total: ₹" + total.toFixed(2);
    }

    // Loan Eligibility
    function calculateLoan() {
      let income = parseFloat(document.getElementById("income").value);
      let expenses = parseFloat(document.getElementById("expenses").value);
      let eligible = (income - expenses) * 60;
      document.getElementById("loanResult").innerText = "Eligible Loan Amount: ₹" + eligible.toFixed(2);
    }

    // EMI Calculator
    function calculateEMI() {
      let principal = parseFloat(document.getElementById("loanAmount").value);
      let annualRate = parseFloat(document.getElementById("interestRate").value) / 100;
      let years = parseFloat(document.getElementById("loanYears").value);
      let months = years * 12;
      let monthlyRate = annualRate / 12;
      let emi = (principal * monthlyRate * Math.pow(1 + monthlyRate, months)) / (Math.pow(1 + monthlyRate, months) - 1);
      let totalPayment = emi * months;
      let totalInterest = totalPayment - principal;
      document.getElementById("emiResult").innerText = 
        "Monthly EMI: ₹" + emi.toFixed(2) + 
        " | Total Interest: ₹" + totalInterest.toFixed(2) + 
        " | Total Payment: ₹" + totalPayment.toFixed(2);
    }
  </script>

</body>
</html>
