<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<title>Shri Ganesh Motors - Invoice</title>

<style>
body{
    font-family: Arial, sans-serif;
    background:#f4f6f8;
    padding:20px;
}

.invoice-box{
    max-width:900px;
    margin:auto;
    background:#fff;
    padding:20px;
    border:1px solid #000;
}

.header{
    text-align:center;
}
.header h1{
    margin:0;
    font-size:28px;
    font-weight:bold;
}
.header p{
    margin:3px 0;
    font-size:13px;
}

.section{
    margin-top:20px;
}

.section-title{
    font-weight:bold;
    font-size:18px;
    border-bottom:2px solid #000;
    padding-bottom:5px;
    margin-bottom:10px;
}

.grid{
    display:grid;
    grid-template-columns: repeat(4, 1fr);
    gap:10px;
}

.grid input, .grid select{
    width:100%;
    padding:6px;
}

/* ===== TABLE BASE ===== */
table{
    width:100%;
    border-collapse:collapse;
    margin-top:10px;
    table-layout:fixed;   /* 🔴 IMPORTANT */
}

table th, table td{
    border:1px solid #000;
    padding:6px;
    text-align:center;
    font-size:13px;
    word-wrap:break-word;
}

table input{
    width:100%;
    box-sizing:border-box;
}

/* ===== PARTS TABLE COLUMN FIX ===== */
#partsTable th:nth-child(1),
#partsTable td:nth-child(1){ width:5%; }

#partsTable th:nth-child(2),
#partsTable td:nth-child(2){ width:25%; }

#partsTable th:nth-child(3),
#partsTable td:nth-child(3){ width:8%; }

#partsTable th:nth-child(4),
#partsTable td:nth-child(4){ width:12%; }

#partsTable th:nth-child(5),
#partsTable td:nth-child(5){ width:35%; }  /* Remark */

#partsTable th:nth-child(6),
#partsTable td:nth-child(6){ width:10%; }  /* Action */

/* ===== BUTTONS ===== */
.add-btn{
    margin-top:5px;
    padding:6px 12px;
}

.delete-btn{
    background:red;
    color:white;
    border:none;
    padding:4px 6px;
    cursor:pointer;
    font-size:12px;
}

/* ===== TOTAL ===== */
.total-box{
    margin-top:20px;
    width:300px;
    float:right;
}

.total-box table td{
    text-align:right;
}

.buttons{
    text-align:center;
    margin-top:30px;
}

/* ===== FOOTER ===== */
.footer{
    margin-top:70px;
    font-size:12px;
}

.sign-box{
    width:45%;
    display:inline-block;
    text-align:center;
}

.line{
    border-top:1px solid #000;
    margin:40px 20px 5px;
}

.thanks{
    text-align:center;
    margin-top:30px;
    font-style:italic;
}

/* ===== A4 PRINT ===== */
@page{
    size:A4;
    margin:15mm;
}

@media print{
    body{
        background:#fff;
    }

    .buttons,
    .add-btn,
    .delete-btn,
    table th:last-child,
    table td:last-child{
        display:none !important;
    }

    table{
        page-break-inside:avoid;
    }
}
</style>
</head>

<body>

<div class="invoice-box">

<!-- HEADER -->
<div class="header">
    <h1>SHRI GANESH MOTORS</h1>
    <p>Near Dharm Kanta, Bilara Road, Borunda, Jodhpur, Raj. (342604)</p>
    <p>📞 6376978548, 9929209414 | ✉ shriganeshmotors734@gmail.com</p>
</div>

<!-- CUSTOMER DETAILS -->
<div class="section">
    <div class="grid">
        <input type="date">
        <input placeholder="Invoice Number">
        <input placeholder="Customer Name">
        <input placeholder="Mobile">

        <input placeholder="Address">
        <input placeholder="Frame No">
        <input placeholder="Registration No">
        <input placeholder="Model Name">
    </div>

    <div style="margin-top:10px;">
        <select>
            <option>Service Type</option>
            <option>FSC 1</option>
            <option>FSC 2</option>
            <option>FSC 3</option>
            <option>FSC 4</option>
            <option>FSC 5</option>
            <option>PAID SERVICE</option>
            <option>GENERAL CHECKUP</option>
            <option>OTHER</option>
        </select>
    </div>
</div>

<!-- PARTS DETAILS -->
<div class="section">
    <div class="section-title">Parts Details</div>
    <table id="partsTable">
        <tr>
            <th>Sr.</th>
            <th>Part Name</th>
            <th>Qty</th>
            <th>Amount</th>
            <th>Remark</th>
            <th>Action</th>
        </tr>
    </table>
    <button class="add-btn" onclick="addPart()">+ Add Part</button>
</div>

<!-- LABOUR DETAILS -->
<div class="section">
    <div class="section-title">Labour Details</div>
    <table id="labourTable">
        <tr>
            <th>Sr.</th>
            <th>Labour Name</th>
            <th>Amount</th>
            <th>Action</th>
        </tr>
    </table>
    <button class="add-btn" onclick="addLabour()">+ Add Labour</button>
</div>

<!-- TOTAL -->
<div class="total-box">
    <table>
        <tr>
            <td>Parts Total</td>
            <td id="partsTotal">0</td>
        </tr>
        <tr>
            <td>Labour Total</td>
            <td id="labourTotal">0</td>
        </tr>
        <tr>
            <th>Grand Total</th>
            <th id="grandTotal">0</th>
        </tr>
    </table>
</div>

<div style="clear:both;"></div>

<!-- PRINT BUTTON -->
<div class="buttons">
    <button onclick="window.print()">Generate & Print Invoice</button>
</div>

<!-- FOOTER -->
<div class="footer">
    <div class="sign-box">
        <p>Customer Signature</p>
        <div class="line"></div>
    </div>

    <div class="sign-box" style="float:right;">
        <p>For Shri Ganesh Motors</p>
        <div class="line"></div>
        <p><b>Authorized Signatory</b></p>
    </div>

    <div style="clear:both;"></div>

    <p class="thanks">Thank you for choosing Shri Ganesh Motors. Visit Again.</p>
</div>

</div>

<script>
let partCount = 0;
let labourCount = 0;

function addPart(){
    partCount++;
    let row = document.getElementById("partsTable").insertRow();
    row.innerHTML = `
        <td>${partCount}</td>
        <td><input></td>
        <td><input type="number" value="1" oninput="calculateTotal()"></td>
        <td><input type="number" value="0" oninput="calculateTotal()"></td>
        <td><input></td>
        <td><button class="delete-btn" onclick="this.parentElement.parentElement.remove(); calculateTotal()">X</button></td>
    `;
}

function addLabour(){
    labourCount++;
    let row = document.getElementById("labourTable").insertRow();
    row.innerHTML = `
        <td>${labourCount}</td>
        <td><input></td>
        <td><input type="number" value="0" oninput="calculateTotal()"></td>
        <td><button class="delete-btn" onclick="this.parentElement.parentElement.remove(); calculateTotal()">X</button></td>
    `;
}

function calculateTotal(){
    let partsTotal = 0;
    document.querySelectorAll("#partsTable tr").forEach((row,i)=>{
        if(i>0){
            let qty = row.cells[2].children[0].value || 0;
            let amt = row.cells[3].children[0].value || 0;
            partsTotal += qty * amt;
        }
    });

    let labourTotal = 0;
    document.querySelectorAll("#labourTable tr").forEach((row,i)=>{
        if(i>0){
            labourTotal += Number(row.cells[2].children[0].value || 0);
        }
    });

    document.getElementById("partsTotal").innerText = partsTotal;
    document.getElementById("labourTotal").innerText = labourTotal;
    document.getElementById("grandTotal").innerText = partsTotal + labourTotal;
}
</script>

</body>
</html>
