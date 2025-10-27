<html lang="es">
<head>
  <meta charset="UTF-8">
  <title>UMBERS</title>
  <style>
    * { margin: 0; padding: 0; box-sizing: border-box; }
    
    body {
      font-family: 'Segoe UI', Tahoma, Arial, sans-serif;
      background: #f5f5f5;
      padding: 20px;
      padding-bottom: 60px;
      color: #333;
    }

    .titulo {
      text-align: center;
      font-size: 2.8em;
      letter-spacing: 8px;
      font-weight: bold;
      color: #222;
      margin: 30px 0 40px 0;
    }

    .contenedor {
      max-width: 700px;
      margin: 0 auto;
      background: white;
      padding: 40px;
      border-radius: 12px;
      box-shadow: 0 2px 10px rgba(0,0,0,0.1);
    }

    .caja-texto {
      margin-bottom: 24px;
    }

    label {
      display: block;
      font-weight: bold;
      margin-bottom: 8px;
      font-size: 1.1em;
      color: #444;
    }

    input[type="number"] {
      width: 100%;
      padding: 14px;
      font-size: 1.1em;
      border: 2px solid #ddd;
      border-radius: 6px;
      transition: border-color 0.3s;
    }

    input[type="number"]:focus {
      border-color: #007bff;
      outline: none;
    }

    .btn {
      width: 100%;
      padding: 16px;
      font-size: 1.2em;
      font-weight: bold;
      color: white;
      border: none;
      border-radius: 8px;
      cursor: pointer;
      margin-top: 15px;
      transition: background-color 0.3s;
    }

    .btn-guardar {
      background: #28a745;
    }

    .btn-guardar:hover {
      background: #218838;
    }

    .btn-comparar {
      background: #dc3545;
    }

    .btn-comparar:hover {
      background: #c82333;
    }

    .btn-historial {
      background: #ffc107;
      color: #000;
    }

    .btn-historial:hover {
      background: #e0a800;
    }

    .mensaje-bienvenida {
      text-align: center;
      color: #111;
      font-size: 1.23em;
      font-weight: bold;
      letter-spacing: 1px;
      margin-top: 32px;
      margin-bottom: 8px;
    }

    .reloj-vivo {
      text-align: center;
      margin-top: 24px;
      padding: 16px;
      background: #f0f0f0;
      border-radius: 8px;
      font-size: 1.2em;
      color: #333;
      font-weight: 600;
      border: 2px solid #ddd;
    }

    .reloj-vivo .hora {
      font-size: 1.8em;
      color: #007bff;
      margin-bottom: 8px;
    }

    .reloj-vivo .fecha {
      font-size: 1em;
      color: #666;
    }

    .resultado, .comparativa, .historial {
      display: none;
      max-width: 800px;
      margin: 40px auto;
      background: white;
      padding: 40px;
      border-radius: 12px;
      box-shadow: 0 2px 10px rgba(0,0,0,0.1);
    }

    .historial {
      background: #e9ecef;
    }

    h2 {
      text-align: center;
      font-size: 2em;
      margin-bottom: 30px;
      color: #222;
    }

    .fecha-hora {
      text-align: center;
      font-size: 1em;
      color: #666;
      margin-bottom: 25px;
      padding-bottom: 15px;
      border-bottom: 2px solid #ddd;
    }

    .resultado-item {
      padding: 16px 20px;
      background: #f8f9fa;
      border-left: 5px solid #28a745;
      margin-bottom: 12px;
      border-radius: 6px;
      font-size: 1.15em;
    }

    .resultado-item strong {
      color: #28a745;
      margin-right: 10px;
    }

    .comparativa-item {
      padding: 16px 20px;
      background: #f8f9fa;
      border-left: 5px solid #007bff;
      margin-bottom: 12px;
      border-radius: 6px;
      font-size: 1.05em;
    }

    .diferencia {
      margin-top: 8px;
      padding: 8px;
      border-radius: 5px;
      text-align: center;
      font-weight: bold;
    }

    .positiva {
      background: #d4edda;
      color: #155724;
    }

    .negativa {
      background: #f8d7da;
      color: #721c24;
    }

    .igual {
      background: #fff3cd;
      color: #856404;
    }

    .collapsible {
      background-color: #007bff;
      color: white;
      cursor: pointer;
      padding: 16px;
      width: 100%;
      border: none;
      text-align: left;
      outline: none;
      font-size: 1.1em;
      border-radius: 6px;
      margin-top: 10px;
      font-weight: 600;
      transition: 0.3s;
    }

    .collapsible:hover, .active {
      background-color: #0056b3;
    }

    .content {
      padding: 0 18px;
      display: none;
      overflow: hidden;
      background-color: #f1f1f1;
      border-radius: 6px;
      margin-top: 5px;
    }

    .registro {
      padding: 15px;
      margin: 10px 0;
      background: white;
      border-left: 4px solid #28a745;
      border-radius: 5px;
    }

    .registro strong {
      color: #28a745;
    }

    .btn-reset {
      background: #6c757d;
      color: white;
      width: 50%;
      margin: 25px auto;
      display: block;
    }

    .btn-reset:hover {
      background: #5a6268;
    }

    .boton-volver {
      background: #6c757d;
      color: white;
      padding: 12px 30px;
      border: none;
      border-radius: 6px;
      font-size: 1.1em;
      font-weight: bold;
      cursor: pointer;
      display: block;
      margin: 30px auto 0;
    }

    .boton-volver:hover {
      background: #5a6268;
    }

    .footer {
      position: fixed;
      left: 0;
      bottom: 0;
      width: 100%;
      background-color: #343a40;
      color: white;
      text-align: center;
      padding: 10px 0;
      font-size: 0.9em;
      letter-spacing: 1px;
      z-index: 1000;
    }
  </style>
</head>
<body>
  <h1 class="titulo">UMBERS</h1>

  <div class="contenedor" id="formulario">
    <div class="caja-texto">
      <label>ANTONIO</label>
      <input type="number" id="antonio">
    </div>
    <div class="caja-texto">
      <label>CONSTANZA</label>
      <input type="number" id="constanza">
    </div>
    <div class="caja-texto">
      <label>KARELIS</label>
      <input type="number" id="karelis">
    </div>
    <div class="caja-texto">
      <label>SANDRA</label>
      <input type="number" id="sandra">
    </div>
    <div class="caja-texto">
      <label>FRANK</label>
      <input type="number" id="frank">
    </div>
    <div class="caja-texto">
      <label>IGNACIO</label>
      <input type="number" id="ignacio">
    </div>
    <div class="caja-texto">
      <label>ROBERTO</label>
      <input type="number" id="roberto">
    </div>

    <button class="btn btn-guardar" onclick="guardarYOrdenar()">GUARDAR</button>
    <button class="btn btn-comparar" onclick="compararDias()">COMPARAR REGISTROS</button>
    <button class="btn btn-historial" onclick="mostrarHistorial()">HISTORIAL</button>

    <div class="mensaje-bienvenida">
      BIENVENIDO/A A MI PROYECTO
    </div>

    <div class="reloj-vivo">
      <div class="hora" id="hora">00:00:00</div>
      <div class="fecha" id="fecha">Cargando fecha...</div>
    </div>
  </div>

  <div class="resultado" id="resultado">
    <h2>RESULTADOS ORDENADOS</h2>
    <div class="fecha-hora" id="fechaHoraResultado"></div>
    <div id="lista-ordenada"></div>
    <button class="boton-volver" onclick="volverAlFormulario()">VOLVER</button>
  </div>

  <div class="comparativa" id="comparativa">
    <h2>COMPARATIVA ENTRE DOS REGISTROS</h2>
    <div id="listaComparativa"></div>
    <button class="boton-volver" onclick="volverAlFormulario()">VOLVER</button>
  </div>

  <div class="historial" id="historial">
    <h2>HISTORIAL DE REGISTROS</h2>
    <div id="historial-lista"></div>
    <button class="btn btn-reset" onclick="resetHistorial()">RESET</button>
    <button class="boton-volver" onclick="volverAlFormulario()">VOLVER</button>
  </div>

  <div class="footer">
    WEB Y DESARROLLO DE CÓDIGO POR ANTONIO 😎
  </div>

  <script>
    let historial = [];
    const meses = ["ENERO","FEBRERO","MARZO","ABRIL","MAYO","JUNIO","JULIO","AGOSTO","SEPTIEMBRE","OCTUBRE","NOVIEMBRE","DICIEMBRE"];
    const formatearCLP = valor => new Intl.NumberFormat('es-CL', { style: 'currency', currency: 'CLP', maximumFractionDigits: 0 }).format(valor);
    const obtenerFechaHora = () => new Date().toLocaleString('es-CL', { dateStyle: 'full', timeStyle: 'medium' });

    // RELOJ EN VIVO
    function actualizarReloj() {
      const ahora = new Date();
      const horas = String(ahora.getHours()).padStart(2, '0');
      const minutos = String(ahora.getMinutes()).padStart(2, '0');
      const segundos = String(ahora.getSeconds()).padStart(2, '0');
      document.getElementById('hora').innerText = `${horas}:${minutos}:${segundos}`;
      const opciones = { weekday: 'long', year: 'numeric', month: 'long', day: 'numeric' };
      const fechaFormato = ahora.toLocaleDateString('es-CL', opciones);
      document.getElementById('fecha').innerText = fechaFormato;
    }
    setInterval(actualizarReloj, 1000);
    actualizarReloj();

    function cargarHistorial() {
      const guardado = localStorage.getItem('umbersHistorial');
      historial = guardado ? JSON.parse(guardado) : [];
    }
    function guardarHistorial() {
      localStorage.setItem('umbersHistorial', JSON.stringify(historial));
    }
    function ocultarTodo() {
      document.getElementById('resultado').style.display = 'none';
      document.getElementById('comparativa').style.display = 'none';
      document.getElementById('historial').style.display = 'none';
      document.getElementById('formulario').style.display = 'none';
    }
    function guardarYOrdenar() {
      const ids = ['antonio','constanza','karelis','sandra','frank','ignacio','roberto'];
      const datos = ids.map(id => ({ nombre: id.toUpperCase(), valor: document.getElementById(id).value }));
      const datosValidos = datos.filter(d => d.valor.trim() && !isNaN(parseFloat(d.valor)));
      if (!datosValidos.length) {
        alert('Por favor, ingresa valores numéricos.');
        return;
      }
      cargarHistorial();
      const fecha = new Date();
      const registro = {
        fecha: fecha.toISOString(),
        formato: obtenerFechaHora(),
        mes: meses[fecha.getMonth()],
        año: fecha.getFullYear(),
        datos: datosValidos.map(d => ({ nombre: d.nombre, valor: parseInt(d.valor) }))
      };
      historial.push(registro);
      guardarHistorial();
      datosValidos.sort((a, b) => b.valor - a.valor);
      document.getElementById('lista-ordenada').innerHTML = datosValidos.map(d => 
        `<div class="resultado-item"><strong>${d.nombre}:</strong> ${formatearCLP(d.valor)}</div>`
      ).join('');
      document.getElementById('fechaHoraResultado').innerText = registro.formato;
      ocultarTodo();
      document.getElementById('resultado').style.display = 'block';
    }
    function compararDias() {
      cargarHistorial();
      if (historial.length < 2) {
        alert('Se necesitan al menos 2 registros para comparar.');
        return;
      }
      const ultimo = historial[historial.length - 1];
      const anterior = historial[historial.length - 2];
      let html = `<div class="fecha-hora"><strong>Comparando:</strong><br>${anterior.formato}<br>vs<br>${ultimo.formato}</div>`;
      const comparacion = ['ANTONIO','CONSTANZA','KARELIS','SANDRA','FRANK','IGNACIO','ROBERTO'].map(n => {
        const v1 = anterior.datos.find(d => d.nombre === n)?.valor || 0;
        const v2 = ultimo.datos.find(d => d.nombre === n)?.valor || 0;
        let clase = 'igual', texto = 'Sin cambio';
        if (v2 > v1) {
          clase = 'positiva';
          texto = `+${formatearCLP(v2 - v1)}`;
        } else if (v2 < v1) {
          clase = 'negativa';
          texto = `-${formatearCLP(v1 - v2)}`;
        }
        return { nombre: n, v1, v2, clase, texto };
      }).sort((a, b) => b.v2 - a.v2);
      comparacion.forEach(item => {
        html += `<div class="comparativa-item">
          <strong>${item.nombre}:</strong> ${formatearCLP(item.v1)} → ${formatearCLP(item.v2)}
          <div class="diferencia ${item.clase}">${item.texto}</div>
        </div>`;
      });
      document.getElementById('listaComparativa').innerHTML = html;
      ocultarTodo();
      document.getElementById('comparativa').style.display = 'block';
    }
    function mostrarHistorial() {
      cargarHistorial();
      if (!historial.length) {
        alert('No hay registros guardados.');
        return;
      }
      const agrupado = {};
      historial.forEach(r => {
        const clave = `${r.año}-${r.mes}`;
        if (!agrupado[clave]) agrupado[clave] = [];
        agrupado[clave].push(r);
      });
      let html = '';
      Object.keys(agrupado).forEach(clave => {
        html += `<button class="collapsible">${clave.replace('-', ' ')}</button>
                 <div class="content">`;
        agrupado[clave].forEach(reg => {
          const datosOrdenados = [...reg.datos].sort((a, b) => b.valor - a.valor);
          html += `<div class="registro">
            <strong>${reg.formato}</strong><br>
            ${datosOrdenados.map(d => `${d.nombre}: ${formatearCLP(d.valor)}`).join('<br>')}
          </div>`;
        });
        html += '</div>';
      });
      document.getElementById('historial-lista').innerHTML = html;
      document.querySelectorAll('.collapsible').forEach(btn => {
        btn.onclick = function() {
          this.classList.toggle('active');
          const content = this.nextElementSibling;
          content.style.display = content.style.display === 'block' ? 'none' : 'block';
        };
      });
      ocultarTodo();
      document.getElementById('historial').style.display = 'block';
    }
    function resetHistorial() {
      if (confirm('¿Seguro que quieres eliminar todos los registros? Esta acción no se puede deshacer.')) {
        localStorage.removeItem('umbersHistorial');
        historial = [];
        document.getElementById('historial-lista').innerHTML = '<p style="text-align:center;padding:20px;"><strong>Todos los registros fueron eliminados.</strong></p>';
      }
    }
    function volverAlFormulario() {
      document.querySelectorAll('input[type=number]').forEach(i => i.value = '');
      ocultarTodo();
      document.getElementById('formulario').style.display = 'block';
    }
    cargarHistorial();
  </script>
</body>
</html>
