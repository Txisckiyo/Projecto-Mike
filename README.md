
<!DOCTYPE html >
<html>
<head><meta charset="utf-8"/>
<script>

let objContador = (function (inicio) {
  let contador = 0;
  let peso = 10;
 
  return {
    incrementarcontador: function () {
      return contador++;
    },
      
    incrementarpeso: function (num) {
      peso = peso + num;
    },
      
     restarcontador: function () {
      contador = contador - 1;
    },
     
    restarpeso: function (num) {
      peso = peso - num;
    },
      
    salirpantalla: function () {
      let cadena = "Contador: " + contador + ". Peso: " + peso;
      document.getElementById("salida").innerHTML = cadena;
      this.dibujoTama()
      
    },
 
    dibujoTama: function () {   
    let dibujo= "XD </br> |";
    if (peso > 20){
         dibujo = "<img src='Images/tama_gordo.jpg'>"; 
        } 
    if (peso <= 10){
         dibujo = " o </br> | </br> |";   
        }
    document.getElementById("salida2").innerHTML = dibujo; 
    },
    
    resetcontador: function () {
      console.log( "contador antes de reset: " + contador );
      contador = 0;
    }
      
  };
})();
 
    
function programa(menu){   // programa(menu, aumento)  2 parametros
    switch (menu){
        case 1:
            objContador.incrementarcontador();
            break;
        case 2:
            objContador.restarcontador(); 
            break;
        case 3:
            objContador.resetcontador();
        case 4:
            objContador.incrementarpeso(5); 
            break;
        case 5:
            objContador.restarpeso(2);
    }       
    
    objContador.salirpantalla();
} 
    
</script>
</head>
<body>
 <div id="salida"></div>
 <input type="button" value="Sumar" onclick="programa(1)" >
 <input type="button" value="Resta" onclick="programa(2)" >
 <input type="button" value="Dar comer" onclick="programa(4)" >
 <input type="button" value="Jugar" onclick="programa(5)" >
 <input type="button" value="Reseteacontador" onclick="programa(3)" >
 <div id="salida2"></div>
</body>
</html>

