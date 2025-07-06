<html lang="hi">
<head>
  <meta charset="UTF-8">
  <title>Shri Ganesh Motors Bill</title>
  <style>
    body {
      font-family: 'Courier New', monospace;
      background: #eee;
      display: flex;
      flex-direction: column;
      align-items: center;
      padding: 20px;
    }
    .container {
      background: white;
      width: 380px;
      padding: 15px;
      border: 1px solid #000;
    }
    h2, h3 {
      text-align: center;
      margin: 5px 0;
    }
    label {
      display: block;
      margin-top: 8px;
      font-size: 13px;
    }
    input {
      width: 100%;
      padding: 4px;
      font-size: 13px;
    }
    table {
      width: 100%;
      margin-top: 10px;
      font-size: 12px;
      border-collapse: collapse;
    }
    th, td {
      border: 1px solid #aaa;
      padding: 4px;
      text-align: left;
    }
    .btn {
      margin-top: 10px;
      padding: 6px 10px;
      background: green;
      color: white;
      border: none;
      cursor: pointer;
      font-size: 13px;
    }
    .invoice-section {
      display: none;
      background: white;
      width: 300px;
      padding: 10px;
      margin-top: 20px;
      border: 1px solid #000;
    }
    .footer {
      margin-top: 20px;
      font-size: 12px;
      text-align: center;
    }
    .signature {
      margin-top: 40px;
      text-align: right;
      font-size: 13px;
      padding-right: 20px;
    }
    @media print {
      body * {
        visibility: hidden;
      }
      .invoice-section, .invoice-section * {
        visibility: visible;
      }
      .invoice-section {
        position: absolute;
        top: 0;
        left: 0;
      }
    }
  </style>
</head>
<body>
<div class="container">
  <h2>Shri Ganesh Motors, Borunda</h2>
  <p style="text-align:center">342604 | 6376978548 | shriganeshmotors734@gmail.com</p>

  <label>Invoice Number:</label><input type="text" id="invoice">
  <label>Date:</label><input type="date" id="date">
  <label>Customer Name:</label><input type="text" id="customer">
  <label>Mobile:</label><input type="text" id="mobile">
  <label>Address:</label><input type="text" id="address">
  <label>Frame No:</label><input type="text" id="frame">
  <label>Registration No:</label><input type="text" id="regis">
  <label>Model Name:</label><input type="text" id="model">
  <label>Service Type:</label><input type="text" id="service">

  <h3>Parts Details</h3>
  <table id="parts-table">
    <thead>
      <tr><th>Sr.</th><th>Parts Name</th><th>Qty</th><th>Amount</th><th>Remark</th><th>Action</th></tr>
    </thead>
    <tbody></tbody>
  </table>
  <button class="btn" onclick="addRow('parts')">Add Parts Row</button>

  <h3>Labour Details</h3>
  <table id="labour-table">
    <thead>
      <tr><th>Sr.</th><th>Charge Name</th><th>Amount</th><th>Action</th></tr>
    </thead>
    <tbody></tbody>
  </table>
  <button class="btn" onclick="addRow('labour')">Add Labour Row</button>

  <h3>Total Amount: ₹<span id="total">0</span></h3>

  <button class="btn" onclick="generateInvoice()">Generate Invoice</button>
</div>

<div class="invoice-section" id="invoice-section">
  <h2>Shri Ganesh Motors</h2>
  <p style="text-align:center">Near Bus Stand, Bilara Road, Borunda - 342604</p>
  <p style="text-align:center">Mobile: 6376978548 | Email: shriganeshmotors734@gmail.com</p>
  <table>
    <tr><td>Invoice No:</td><td id="out-invoice"></td></tr>
    <tr><td>Date:</td><td id="out-date"></td></tr>
    <tr><td>Customer:</td><td id="out-customer"></td></tr>
    <tr><td>Mobile:</td><td id="out-mobile"></td></tr>
    <tr><td>Address:</td><td id="out-address"></td></tr>
    <tr><td>Frame No:</td><td id="out-frame"></td></tr>
    <tr><td>Regis No:</td><td id="out-regis"></td></tr>
    <tr><td>Model:</td><td id="out-model"></td></tr>
    <tr><td>Service:</td><td id="out-service"></td></tr>
  </table>
  <h3>Parts Details</h3>
  <table id="out-parts-table">
    <thead>
      <tr><th>Sr.</th><th>Parts Name</th><th>Qty</th><th>Amount</th><th>Remark</th></tr>
    </thead>
    <tbody></tbody>
  </table>
  <h3>Labour Details</h3>
  <table id="out-labour-table">
    <thead>
      <tr><th>Sr.</th><th>Charge Name</th><th>Amount</th></tr>
    </thead>
    <tbody></tbody>
  </table>
  <h3>Total: ₹<span id="out-total"></span></h3>
  <div class="signature">Authorised Signatory</div>
  <div class="footer">Thank you for choosing Shri Ganesh Motors. We value your trust and support.</div>
</div>

<button class="btn" onclick="window.print()" style="margin-top: 20px">Print Invoice</button>

<script>
function addRow(type) {
  const table = document.getElementById(type + '-table').getElementsByTagName('tbody')[0];
  const row = table.insertRow();
  const sr = table.rows.length;
  if (type === 'parts') {
    row.innerHTML = `
      <td>${sr}</td>
      <td><input type="text" oninput="updateTotal()"></td>
      <td><input type="number" value="1" oninput="updateTotal()"></td>
      <td><input type="number" value="0" oninput="updateTotal()"></td>
      <td><input type="text"></td>
      <td><button onclick="removeRow(this)">Remove</button></td>
    `;
  } else {
    row.innerHTML = `
      <td>${sr}</td>
      <td><input type="text" oninput="updateTotal()"></td>
      <td><input type="number" value="0" oninput="updateTotal()"></td>
      <td><button onclick="removeRow(this)">Remove</button></td>
    `;
  }
  updateTotal();
}

function removeRow(btn) {
  const row = btn.parentNode.parentNode;
  row.parentNode.removeChild(row);
  updateTotal();
}

function updateTotal() {
  let total = 0;
  document.querySelectorAll('#parts-table tbody tr').forEach(row => {
    const qty = parseFloat(row.cells[2].children[0].value) || 0;
    const amt = parseFloat(row.cells[3].children[0].value) || 0;
    total += qty * amt;
  });
  document.querySelectorAll('#labour-table tbody tr').forEach(row => {
    const amt = parseFloat(row.cells[2].children[0].value) || 0;
    total += amt;
  });
  document.getElementById('total').innerText = total.toFixed(2);
}

function generateInvoice() {
  document.getElementById('out-invoice').innerText = document.getElementById('invoice').value;
  document.getElementById('out-date').innerText = document.getElementById('date').value;
  document.getElementById('out-customer').innerText = document.getElementById('customer').value;
  document.getElementById('out-mobile').innerText = document.getElementById('mobile').value;
  document.getElementById('out-address').innerText = document.getElementById('address').value;
  document.getElementById('out-frame').innerText = document.getElementById('frame').value;
  document.getElementById('out-regis').innerText = document.getElementById('regis').value;
  document.getElementById('out-model').innerText = document.getElementById('model').value;
  document.getElementById('out-service').innerText = document.getElementById('service').value;
  document.getElementById('out-total').innerText = document.getElementById('total').innerText;

  const partsOutTable = document.getElementById('out-parts-table').getElementsByTagName('tbody')[0];
  partsOutTable.innerHTML = "";
  document.querySelectorAll('#parts-table tbody tr').forEach((row, index) => {
    const partRow = partsOutTable.insertRow();
    partRow.innerHTML = `
      <td>${index + 1}</td>
      <td>${row.cells[1].children[0].value}</td>
      <td>${row.cells[2].children[0].value}</td>
      <td>${row.cells[3].children[0].value}</td>
      <td>${row.cells[4].children[0].value}</td>
    `;
  });

  const labourOutTable = document.getElementById('out-labour-table').getElementsByTagName('tbody')[0];
  labourOutTable.innerHTML = "";
  document.querySelectorAll('#labour-table tbody tr').forEach((row, index) => {
    const labourRow = labourOutTable.insertRow();
    labourRow.innerHTML = `
      <td>${index + 1}</td>
      <td>${row.cells[1].children[0].value}</td>
      <td>${row.cells[2].children[0].value}</td>
    `;
  });

  document.getElementById('invoice-section').style.display = 'block';
}
</script>
</body>
</html>
