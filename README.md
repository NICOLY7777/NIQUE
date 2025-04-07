<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Lista de tarefas </title>
    <link rel="stylesheet" href="./style.css">
</head>
<body>
    <div class="container">
        <div  class ="header">
            <img src="./lista.pmg" alt="icone de tarefas">
            <h1> Lista de tarefas</h1>
        </div>
        <input type="text" id="tarefaInput" aria-placeholder="Digite uma tefefa">
        <button class="adicionarTarefa" onclick="adicionarTarefa()" > Adicionar</button>
        <ul id="listasTarefas"></ul>
    </div>

   <script>
     let tarefas= [];

     function adicionarTarefa(){
        const input = document.getElementById('tarefaInput')
        const tarefa = input.value.trim();

          if(tarefa){
            tarefas.push(tarefa);
            input.value = '';
            atualizarLista();
          }
    }

      function removerTarefa(index){
        tarefas.splice(index,1);
        atualizarLista();
      }

      function atualizarLista(){
        const lista = document.getElementById('listasTarefas');
        lista.innerHTML = '';
        tarefas.forEach((tarefa, index)=>{
            const  li = document.createElement('li');

            li.innerHTML =` ${tarefa}<button class ="removerTarefa" onclick ="removerTarefas(${index})">Remover</button>`;
            
            lista.appendChild(li);
        }) 

        }

    
    </script>     
</body>
</html>
