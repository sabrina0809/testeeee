# testeeee

<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
    <link href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.3/dist/css/bootstrap.min.css" rel="stylesheet" integrity="sha384-QWTKZyjpPEjISv5WaRU9OFeRpok6YctnYmDr5pNlyT2bRjXh0JMhjY6hW+ALEwIH" crossorigin="anonymous">
</head>
<body>

    <form action="" class="container">
        <div class="mb-3" id="nome">
            <label for="formGroupExampleInput" class="form-label">Nome</label>
            <input type="text" class="form-control" id="formGroupExampleInput" placeholder="Nome completo">
          </div>
          <div class="mb-3" id="idade">
            <label for="formGroupExampleInput2" class="form-label">idade</label>
            <input type="text" class="form-control" id="formGroupExampleInput2" placeholder="idade">
          </div>
          <div class="form-floating" style="margin-bottom: 20px;" id="sexo">
            <select class="form-select" id="floatingSelect" aria-label="Floating label select example">
              <option selected>Sexo</option>
              <option value="Masculino">Masculino</option>
              <option value="Feminino">Feminino</option>
              <option value="outro">outro</option>
            </select>
            <label for="floatingSelect">Sexo</label>
          </div>
          <div>
            <button type="button" class="btn btn-success" onclick="adicionar()" > adicionar </button>
          </div>
    </form>
    <hr>
    <form action="", class="container">
    <div class="mb-3">
        <label for="formGroupExampleInput" class="form-label">index</label>
        <input type="text" class="form-control" id="formGroupExampleInput" placeholder="index">
    </div>
    <div>
        <button type="button" class="btn btn-danger" onclick="remover()">Remove</button>
    </div>
    </form>
    <hr>
    <form action="", class="container">
        <div class="mb-3">
            <label for="formGroupExampleInput" class="form-label">nome</label>
            <input type="text" class="form-control" id="formGroupExampleInput" placeholder="index">
        </div>
        <div>
            <button type="button" class="btn btn-primary" onclick="buscar()">buscar</button>
        </div>
    </form>

    
    <script src="script.js"></script>
</body>
</html>





-----------------------------------------------------------------------------------------------------
     *NO SCRIPT.JS*



     let pessoas = [{'nome': "lucas", 'idade': 1, 'sexo': 'masculino'}];

var btnCadastrar = document.getElementById("btnCadastrar");
var nome = document.getElementById("nome");
var idade = document.getElementById("idade");
var sexo = document.getElementById("sexo");
var index = document.getElementById("index");

function adicionar() {
    
    let novoNome = nome.value;
    let novaIdade = idade.value;
    let novoSexo = sexo.value;

    
    pessoas.push({'nome': novoNome, 'idade': novaIdade, 'sexo': novoSexo});

    
    console.log(pessoas);
}

function remover() {
    
    let indexValue = parseInt(index.value);
    
    
    if (indexValue >= 0 && indexValue < pessoas.length) {
        
        pessoas.splice(indexValue, 1);
        console.log(pessoas);

    } else {
        
        console.log("Índice inválido!");
    }
}

function buscar() {
    
    let nomeBusca = nome.value.toLowerCase();
    
    
    let resultadoBusca = pessoas.filter(pessoa => pessoa.nome.toLowerCase() === nomeBusca);
    
    
    console.log(resultadoBusca);
}

console.log(pessoas);
