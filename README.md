<!DOCTYPE html>
<html>
<head>
<meta charset="UTF-8">
<title>Lacag Aruurin System</title>
<style>
body { font-family: Arial; text-align: center; padding: 20px; }
input { padding: 8px; margin: 5px; }
button { padding: 8px 15px; }
.card { border:1px solid #ccc; padding:20px; margin-top:20px; display:inline-block; }
</style>
</head>
<body>

<h2>Lacag Aruurin System</h2>

<!-- LOGIN -->
<div id="login">
    <h3>Gali ID-gaaga</h3>
    <input type="text" id="studentId" placeholder="Enter ID">
    <button onclick="login()">Login</button>
</div>

<!-- STUDENT DATA -->
<div id="studentPage" style="display:none;">
    <div class="card">
        <h3 id="name"></h3>
        <p><b>ID:</b> <span id="id"></span></p>
        <p><b>Semester:</b> <span id="semester"></span></p>
        <p><b>Monthly:</b> $2</p>
        <p><b>Total (2 years):</b> $48</p>
        <p><b>Paid:</b> $<span id="paid"></span></p>
        <p><b>Remaining:</b> $<span id="remaining"></span></p>
    </div>
</div>

<script>
const monthly = 2;
const months = 24;

let students = [
{ name:"Abdihalim Adam Abdi", id:"HS231429", semester:"Five", paid:0 },
{ name:"Abdikani Ahmed Kassim", id:"HS231483", semester:"Five", paid:0 },
{ name:"Abdikani Ibrahim Mohamud", id:"HS231484", semester:"Five", paid:0 },
{ name:"Abdinasir Adam Ibrahim", id:"HS231488", semester:"Five", paid:0 },
{ name:"Abdinasir Kerow Adam", id:"HS231490", semester:"Five", paid:0 }
];

function login() {
    let inputId = document.getElementById("studentId").value.trim();

    let student = students.find(s => s.id === inputId);

    if (student) {
        let total = monthly * months;
        let remaining = total - student.paid;

        document.getElementById("login").style.display = "none";
        document.getElementById("studentPage").style.display = "block";

        document.getElementById("name").innerText = student.name;
        document.getElementById("id").innerText = student.id;
        document.getElementById("semester").innerText = student.semester;
        document.getElementById("paid").innerText = student.paid;
        document.getElementById("remaining").innerText = remaining;
    } else {
        alert("ID ma saxna!");
    }
}
</script>

</body>
</html>
