<!DOCTYPE html>
<html>
<head>
<meta charset="UTF-8">
<title>Fraktionsverwaltung</title>

<style>
body{
font-family: Arial;
background:#1e1e1e;
color:white;
text-align:center;
}

.container{
width:600px;
margin:auto;
margin-top:40px;
background:#2a2a2a;
padding:20px;
border-radius:10px;
}

input,select,button{
padding:10px;
margin:5px;
border:none;
border-radius:5px;
}

button{
background:#3a7cff;
color:white;
cursor:pointer;
}

.member{
background:#3a3a3a;
margin:10px;
padding:10px;
border-radius:5px;
}
</style>

</head>

<body>

<div class="container">

<h1>Fraktionsverwaltung</h1>

<input id="name" placeholder="Spielername">

<select id="rang">
<option>Rekrut</option>
<option>Officer</option>
<option>Sergeant</option>
<option>Lieutenant</option>
<option>Commander</option>
<option>Boss</option>
</select>

<button onclick="addMember()">Hinzufügen</button>

<h2>Mitglieder</h2>

<div id="memberList"></div>

</div>

<script>

let members = JSON.parse(localStorage.getItem("members")) || [];

function save(){
localStorage.setItem("members", JSON.stringify(members));
}

function render(){

let list = document.getElementById("memberList");
list.innerHTML="";

members.forEach((m,i)=>{

let div = document.createElement("div");
div.className="member";

div.innerHTML =
"<b>"+m.name+"</b> | "+m.rang+
" <button onclick='removeMember("+i+")'>Entfernen</button>";

list.appendChild(div);

});

}

function addMember(){

let name = document.getElementById("name").value;
let rang = document.getElementById("rang").value;

if(name === "") return;

members.push({
name:name,
rang:rang
});

save();
render();

}

function removeMember(i){

members.splice(i,1);
save();
render();

}

render();

</script>

</body>
</html>
