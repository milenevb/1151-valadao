<!DOCTYPE html>
<html lang="pt-br">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Medidor de idade</title>
</head>
<body>
    <main>
        <h1>Medidor de idade para a quantidade de pessoas</h1>
        <p>Selecione a quantidade de pessoas que você deseja cadastrar:</p>
        <form action="salvar.php" method="get" onsubmit="return calcular()">
            <input type="number" name="total" id="total" min="1" max="10" value="5">
            <input type="submit" value="Medir">
        </form>
        <p id="resultado">O resultado vai aparecer aqui...</p>
    </main>
    <script>
        function calcular(){
            let res= document.getElementById("resultado")
            let total = Number(document.getElementById("total").value)

            let idade = 0
            let soma = 0
            
            let c = 1
            while (c<=total){
                idade = Number(prompt(`Digite a idade da ${c} pessoa:`))
                soma += idade
                c++
            }
            let media = soma/total
            res.innerHTML = ` O total de ${total} pessoas cadastradas, a média de idade é de ${media.toFixed(2)} anos `

            return false
        }
    </script>
</body>
</html>
