<!DOCTYPE html>
<html lang="pt-br">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Briefing Projeto Residencial</title>

<style>
*{box-sizing:border-box;}

body{
font-family: system-ui, Arial;
margin:0;
background:#f3f4f6;
}

.container{
max-width:700px;
margin:auto;
padding:20px;
}

.card{
background:white;
padding:25px;
border-radius:14px;
box-shadow:0 4px 12px rgba(0,0,0,0.08);
}

h1{
text-align:center;
margin-bottom:20px;
}

h2{
margin-top:30px;
font-size:18px;
}

label{
margin-top:15px;
display:block;
font-weight:500;
}

input, textarea, select{
width:100%;
padding:14px;
margin-top:5px;
border-radius:10px;
border:1px solid #ddd;
font-size:16px;
}

button{
width:100%;
margin-top:30px;
padding:16px;
border:none;
border-radius:12px;
background:#2563eb;
color:white;
font-size:18px;
font-weight:bold;
}

button:active{
transform:scale(.98);
}
</style>
</head>

<body>

<div class="container">
<div class="card">

<h1>Briefing Residencial</h1>

<form id="form">

<h2>👤 Dados do Cliente</h2>

<label>Nome</label>
<input name="nome">

<label>Telefone</label>
<input name="telefone">

<label>Email</label>
<input name="email">

<label>Quantas pessoas irão morar?</label>
<input type="number" name="moradores">

<label>Idade dos moradores</label>
<input name="idades">

<label>Possui crianças?</label>
<select name="criancas">
<option>Não</option>
<option>Sim</option>
</select>

<label>Possui idosos?</label>
<select name="idosos">
<option>Não</option>
<option>Sim</option>
</select>

<label>Pets</label>
<input name="pets">

<h2>📍 Dados do Terreno</h2>

<label>Endereço</label>
<input name="endereco">

<label>Área do lote</label>
<input name="area_lote">

<label>Topografia</label>
<select name="topografia">
<option>Plano</option>
<option>Aclive</option>
<option>Declive</option>
</select>

<label>Terreno em condomínio?</label>
<select name="condominio">
<option>Não</option>
<option>Sim</option>
</select>

<h2>🏠 Casa</h2>

<label>Quantidade de quartos</label>
<input type="number" name="quartos">

<label>Quantidade de suítes</label>
<input type="number" name="suites">

<label>Banheiros</label>
<input type="number" name="banheiros">

<label>Garagem (carros)</label>
<input type="number" name="garagem">

<label>Ambientes extras</label>
<textarea name="extras"></textarea>

<h2>🎨 Estilo</h2>

<label>Estilo desejado</label>
<input name="estilo">

<label>O que não gosta</label>
<textarea name="nao_gosta"></textarea>

<h2>💰 Orçamento</h2>

<label>Valor estimado</label>
<input name="orcamento">

<button type="submit">Salvar Respostas</button>

</form>

</div>
</div>

<script>

// salvar temporariamente enquanto digita
const form = document.getElementById("form");

if(localStorage.dadosForm){
const dados = JSON.parse(localStorage.dadosForm);
Object.keys(dados).forEach(key=>{
if(form[key]) form[key].value = dados[key];
});
}

form.addEventListener("input", ()=>{
let dados={};
[...form.elements].forEach(e=>{
if(e.name) dados[e.name]=e.value;
});
localStorage.dadosForm=JSON.stringify(dados);
});

// baixar respostas como arquivo
form.addEventListener("submit", e=>{
e.preventDefault();

let dados={};
[...form.elements].forEach(e=>{
if(e.name) dados[e.name]=e.value;
});

const blob=new Blob([JSON.stringify(dados,null,2)],{type:"application/json"});
const url=URL.createObjectURL(blob);

const a=document.createElement("a");
a.href=url;
a.download="briefing_residencial.json";
a.click();

alert("Respostas salvas!");
localStorage.removeItem("dadosForm");
});

</script>

</body>
</html>
