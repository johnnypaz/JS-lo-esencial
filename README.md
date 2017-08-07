<!DOCTYPE html>
<html>
  <head>
    <meta charset="utf-8">
    <meta name="viewport" content="width=device-width, user-scalable=no">
    <link rel="stylesheet" href="css/estilos.css">
    <title>JS Lo Esencial Proyecto Final</title>
  </head>
  <body>
    <div class="contenedor">
      <h1 id="titulodatos">Base de Datos (Notas/Alumnos)</h1>
      <hr>
      <div class="contenido">
        <table>
          <tr>
            <td><button class="boton" type="button" name="button" onclick="mostrartodo(estudiantes)">Mostrar Todos</button></td>
            <td><button class="boton" type="button" name="button" onclick="mostrarpromedio(estudiantes)">Calcular Promedio</button></td>
            <td><button class="boton" type="button" name="button" onclick="mostrarnotaalta(estudiantes)">Nota mas Alta</button></td>
            <td><button class="boton" type="button" name="button" onclick="mostrarnotabaja(estudiantes)">Nota mas Baja</button></td>
          </tr>
        </table>
      </div>
      <hr>
      <h2 class="tituloresultado">Resultado</h2>
      <p class="textomuestra" id="mostrar"></p>
      <p class="textomuestra" id="mostrar2"></p>
      <p class="textomuestra" id="mostrar3"></p>
      <p class="textomuestra" id="mostrar4"></p>

      <hr>
      <p class="textolegal">Los resultados son calculados, por nuestra plataforma web, son realizados gracias a funciones, metodos y eventos de javascript, gracias a nuestra base de datos creada con JSON podemos ver estos resultados</p>

    </div>

  </body>

  <script type="text/javascript">

  var estudiantes =[
    {"codigo":"001","nombre":"johnny","nota":4.0},
    {"codigo":"002","nombre":"Tatiana","nota":5},
    {"codigo":"003","nombre":"Berta","nota":3.5},
    {"codigo":"004","nombre":"Edison","nota":2.5},
    {"codigo":"005","nombre":"Mary","nota":3.2},
    {"codigo":"006","nombre":"John","nota":4.0},
    {"codigo":"007","nombre":"Johnatan","nota":3.8},
    {"codigo":"008","nombre":"Johnnier","nota":1.5},
    {"codigo":"009","nombre":"Perla","nota":2.5},
    {"codigo":"0010","nombre":"Zeus","nota":1.0}
  ];

  //funcion mostrar todos los estudiantes

  function mostrartodo(json) {
    var out="---Todas las Notas--- <br> <br>";
    var i;
    for (i=0; i < json.length; i++){
      out += ("Codigo: " + json[i].codigo + " - " + "Nombre: " + json[i].nombre + " - " + "Nota: " + json[i].nota + "<br>"+ "<br>");

    }
    document.getElementById('mostrar').innerHTML = out;
  }

  //funcion calcular promedio

  function mostrarpromedio(json) {
    var out="---Promedio--- <br> <br>";
    var nota =""
    var total=0;
    for (i= 0; i < json.length; i++){
      var nota = json[i].nota;
      total += nota;

    }
    document.getElementById('mostrar2').innerHTML = out + (total / 10);
  }


  //funcion mostrar nota mas alta

  function mostrarnotaalta(json) {
    var salida="---Nota mas Alta--- <br> <br>";
    var notaMayor = "";
    for(i=0; i < json.length; i++){
      if(json[i].nota > notaMayor){
        nombremayor=json[i].nombre;
        notaMayor= json[i].nota;
      }
    }
    document.getElementById('mostrar3').innerHTML = salida + (nombremayor + " - " + notaMayor);
  }

  //funcion mostrar nota mas baja

  function mostrarnotabaja(json) {
    var salida ="---Nota mas Baja--- <br> <br>";
    var notaBaja = "";

    for(i=0; i < json.length; i++){
      if(json[i].nota < 5){
        nombrebaja = json[i].nombre;
        notaBaja= json[i].nota;
      }
    }
    document.getElementById('mostrar4').innerHTML = salida + (nombrebaja + " - " + notaBaja);
  }





  </script>
</html>
