<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Formulário</title>
    <link rel="stylesheet" href="style.css">
</head>
<body>
  function Enviar() {
    var table = document.querySelector("table")
    
    var pront, name, email, data, per, extras, sat, cursos;
    pront = document.frmDados.pront.value;
    name = document.frmDados.name.value;
    email = document.frmDados.email.value;
    data = document.frmDados.data.value;
    if (document.frmDados.per.value == "m") { man = "X"} else {man = ""}
    if (document.frmDados.per.value == "t") { tar = "X"} else {tar = ""}
    if (document.frmDados.per.value == "n") { noi = "X"} else {noi = ""}
    cursos = document.frmDados.curso.value;
    extras = "";
    extras += (document.frmDados.interesse1.checked?document.frmDados.interesse1.value:"");
    extras += ((document.frmDados.interesse2.checked&&extras!="")?", ":"");
    extras += (document.frmDados.interesse2.checked?document.frmDados.interesse2.value:"");
    extras += ((document.frmDados.interesse3.checked&&extras!="")?", ":"");
    extras += (document.frmDados.interesse3.checked?document.frmDados.interesse3.value:"");
    sat = document.frmDados.sat.value;

    var form = document.querySelector("form")
    form.innerHTML = ""

        table.innerHTML = `
    
        <tr>
        <td><img src="https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcSrvKGiIoFhd9ndV_aTGUuU__tBcAwAmG9llG6HkV5L&s"></td>
        <td colspan="2"></td>
        </tr>
        <tr>
        <td colspan="2">Prontuário: ${pront}</td>
        <td>Satisfação<br>${sat}%</td>
        </tr>
        <tr>
        <td colspan="3">Nome: ${name}</td>
        </tr>
        <tr>
        <td colspan="3">Email: ${email}</td>
        </tr>
        <tr>
        <td colspan="2">Curso: ${cursos}</td>
        <td>Ingresso: ${data}</td>
        </tr>
        <tr>
        <td colspan="3">Periodo: </td>
        </tr>
        <tr>
        
        <td>(${man}) Manhã</td>
        <td>(${tar}) Tarde</td>
        <td>(${noi}) Noite</td>
        </tr>
        <tr>
        <td rowspan="2" colspan="3">
        Atividades Extras:
        ${extras}
        </td>
        </tr>
        `
    
    
} 

* {
    margin: 0;
    padding: 0;
}

td {
    padding: 8px;
    border: 2px solid rgb(0, 0, 0);
    text-align: center;
}

img {
    height: 50px;
    width: 50px;

}
body{
    background-image: url(https://imagizer.imageshack.com/img924/9752/4a54gS.jpg);
    background-size: 450px;
    background-repeat: no-repeat;
    background-position: center center; 
    background-color: #000; 
    color: #000000; 
    margin: 0;
    padding: 0;
    display: flex;
    justify-content: center; 
    align-items: center;
    height: 100vh;
}
    <form name="frmDados">
        <h1>Um pouco sobre você..</h1>
        <br>

        <label for="pront">Prontuário: </label>
        <input type="text" id="pront" name="pront">
        <br><br>

        <label for="name">Nome: </label>
        <input type="text" id="name" name="name">
        <br><br>

        <label for="email">E-mail Institucional: </label>
        <input type="email" name="" id="email" name="email">
        <br><br>

        <select name="" id="curso" name="curso">
            <option value="Informática Básica">Informática Básica</option>
            <option value="Técnico em Eletrônica">Técnico em Eletrônica</option>
            <option value="Técnico em Automação Industrial">Técnico em Automação Industrial</option>
            <option value="Técnico em Eventos">Técnico em Eventos</option>
            <option value="Técnico em Informática">Técnico em Informática</option>
        </select>
        <br><br>

        <label for="">Período: </label><br>
        <input type="radio" name="per" id="man"  value="m">
        <label for="man">Manhã </label>
        <input type="radio" name="per" id="tar"  value="t">
        <label for="tar">Tarde </label>
        <input type="radio" name="per" id="noi"  value="n">
        <label for="noi">Noite </label>
        <br><br>

        <label for="data">Data ingresso: </label>
        <input type="date" id="data">
        <br><br>

        <label for="">Extensão</label><br>
        <input type="checkbox" name="interesse1" value="música" id="mus">
        <label for="mus">Música</label><br>
        <input type="checkbox" name="interesse2" value="pintura" id="pin">
        <label for="pin">Pintura</label><br>
        <input type="checkbox" name="interesse3" value="teatro" id="tea">
        <label for="tea">Teatro</label>
        <br><br>

        <label for="est">Nível de satisfação: </label>
        <input type="range" name="sat" id="sat">
        <br><br>
        <input type="button" value="Enviar" onclick="Enviar()">
        <input type="reset" value="Limpar">
    </form>
    <table></table>
    <script src="script.js"></script>
</body>
</html>
