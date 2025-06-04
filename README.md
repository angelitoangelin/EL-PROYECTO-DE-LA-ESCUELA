<!DOCTYPE html>
<html lang="es">
  <head>
    <title>CBTis 272│portal de inscripciones</title>
  <style>
    :root {
      --vino: #800000;
      --crema: #fff8e7;
      --dorado: #cfa968;
      --gris: #f5f5f5;
    }

    body {
      margin: 0;
      font-family: 'Segoe UI', sans-serif;
      background-color: var(--crema);
      color: #333;
    }

    header {
      background-color: var(--vino);
      color: white;
      padding: 20px;
      text-align: center;
      position: relative;
    }

    .contenedor-inicio-sesion, .contenedor {
      max-width: 900px;
      margin: 40px auto;
      background-color: white;
      border: 2px solid var(--dorado);
      padding: 30px;
      border-radius: 10px;
      box-shadow: 0 0 15px rgba(0,0,0,0.1);
    }

    h2 {
      border-left: 6px solid var(--vino);
      padding-left: 10px;
      color: var(--vino);
      margin-top: 30px;
    }

    .grupo-formulario {
      display: flex;
      flex-direction: column;
      margin-bottom: 15px;
    }

    .grupo-formulario label {
      font-weight: bold;
    }

    .grupo-formulario input,
    .grupo-formulario select {
      padding: 8px;
      border-radius: 4px;
      border: 1px solid #ccc;
      margin-top: 5px;
    }

    .fila-formulario {
      display: flex;
      gap: 10px;
    }

    .fila-formulario .grupo-formulario {
      flex: 1;
    }

    .grupo-casillas label {
      font-weight: normal;
      display: block;
    }

    .nota {
      font-size: 0.9em;
      color: #555;
      margin-top: 20px;
    }

    button {
      background-color: var(--vino);
      color: white;
      padding: 10px 20px;
      font-weight: bold;
      border: none;
      border-radius: 5px;
      margin-top: 30px;
      cursor: pointer;
    }

    button:hover {
      background-color: #a00000;
    }

    .oculto {
      display: none;
    }
  </style>
</head>
<body>

<header>
  <h1>CBTis 272</h1>
  <p>Portal de Inscripciones y Reinscripciones</p>
</header>

<div class="contenedor-inicio-sesion" id="inicio-sesion">
  <h2>Bienvenido al Sistema</h2>
  <p>Por favor, inicia sesión para comenzar tu inscripción o reinscripción.</p>
  <div class="grupo-formulario">
    <label for="correo">Correo electrónico</label>
    <input type="email" id="correo" placeholder="NOMBRES,APELLIDOS@cbtis272.edu.mx">
  </div>
  <div class="grupo-formulario">
    <label for="contraseña">Contraseña</label>
    <input type="contraseña" id="contraseña" placeholder="Contraseña">
  </div>
  <button onclick="iniciarSesion()">Iniciar Sesión</button>
  <button onclick="registro()">Registro</button>
</div>

<div class="contenedor oculto" id="formulario">
  <h2>Datos del Alumno</h2>
  <div class="fila-formulario">
    <div class="grupo-formulario"><label>Primer Apellido</label><input type="texto"></div>
    <div class="grupo-formulario"><label>Segundo Apellido</label><input type="texto"></div>
    <div class="grupo-formulario"><label>Nombre(s)</label><input type="texto"></div>
  </div>
  <div class="fila-formulario">
    <div class="grupo-formulario"><label>Periodo</label><input type="texto" value="2024-2025-1"></div>
    <div class="grupo-formulario"><label>Semestre</label><input type="numero" value="1"></div>
    <div class="grupo-formulario"><label>Grupo</label><input type="texto"></div>
  </div>
  <div class="fila-formulario">
    <div class="grupo-formulario"><label>Turno</label><input type="texto"></div>
    <div class="grupo-formulario"><label>Carrera</label><input type="texto"></div>
  </div>
  <div class="fila-formulario">
    <div class="grupo-formulario"><label>CURP</label><input type="texto"></div>
    <div class="grupo-formulario"><label>Fecha de Nacimiento</label><input type="fecha"></div>
    <div class="grupo-formulario"><label>Edad</label><input type="numero"></div>
    <div class="grupo-formulario"><label>Sexo</label>
      <select><option>H</option><option>M</option></select>
    </div>
  </div>
  <div class="fila-formulario">
    <div class="grupo-formulario"><label>Estado de Nacimiento</label><input type="texto"></div>
    <div class="grupo-formulario"><label>Municipio</label><input type="texto"></div>
    <div class="grupo-formulario"><label>Ciudad</label><input type="texto"></div>
  </div>
  <div class="grupo-formulario">
    <label>Estado Civil</label>
    <select>
      <option>Soltero</option><option>Casado</option><option>Unión Libre</option><option>Otro</option>
    </select>
  </div>

  <h2>Datos Generales</h2>
  <div class="fila-formulario">
    <div class="grupo-formulario"><label>Colonia o Región</label><input type="texto"></div>
    <div class="grupo-formulario"><label>Domicilio (Calle y Número)</label><input type="texto"></div>
    <div class="grupo-formulario"><label>Código Postal</label><input type="texto"></div>
  </div>
  <div class="fila-formulario">
    <div class="grupo-formulario"><label>Teléfono</label><input type="telefono"></div>
    <div class="grupo-formulario"><label>Correo Electrónico</label><input type="correo electronico"></div>
  </div>
  <div class="fila-formulario">
    <div class="grupo-formulario"><label>Tipo de Sangre</label><input type="texto"></div>
    <div class="grupo-formulario"><label>En caso de accidente avisar a</label><input type="texto"></div>
    <div class="grupo-formulario"><label>Teléfono</label><input type="telefono"></div>
  </div>
  <div class="fila-formulario">
    <div class="grupo-formulario"><label>¿Habla lengua indígena?</label>
      <select><option>No</option><option>Sí</option></select>
    </div>
    <div class="grupo-formulario"><label>¿Cuál?</label><input type="texto"></div>
  </div>

  <h2>Datos Médicos</h2>
  <div class="fila-formulario">
    <div class="grupo-formulario"><label>Número de Seguro Social</label><input type="texto"></div>
    <div class="grupo-formulario"><label>UMF Correspondiente</label>
      <select><option>#13</option><option>#14</option><option>#15</option><option>#16</option><option>#19</option></select>
    </div>
  </div>
  <div class="fila-formulario">
    <div class="grupo-formulario"><label>¿Padece alguna enfermedad o alergia crónica?</label>
      <select><option>No</option><option>Sí</option></select>
    </div>
    <div class="grupo-formulario"><label>Especificar</label><input type="texto"></div>
  </div>
  <div class="grupo-formulario grupo-casillas">
    <label>¿Presenta alguna discapacidad o condición de salud?</label>
    <label><input type="checkbox"> Motriz</label>
    <label><input type="checkbox"> Habla</label>
    <label><input type="checkbox"> Auditiva</label>
    <label><input type="checkbox"> Visual</label>
    <label><input type="checkbox"> Otros</label>
  </div>

  <h2>Datos de la Secundaria de Origen</h2>
  <div class="grupo-formulario"><label>Nombre de la Secundaria</label><input type="texto"></div>
  <div class="fila-formulario">
    <div class="grupo-formulario"><label>Régimen</label>
      <select><option>Pública</option><option>Privada</option></select>
    </div>
    <div class="grupo-formulario"><label>Promedio General</label><input type="texto"></div>
  </div>
  <div class="grupo-formulario">
    <label>Modalidad</label>
    <select>
      <option>General</option><option>Técnica</option><option>Abierta</option><option>INEA</option>
      <option>Telesecundaria</option><option>Ceneval</option><option>Modular</option>
    </select>
  </div>

  <h2>Datos del Padre o Tutor</h2>
  <div class="fila-formulario">
    <div class="grupo-formulario"><label>Padre</label><input type="texto"></div>
    <div class="grupo-formulario"><label>Teléfono</label><input type="telefono"></div>
  </div>
  <div class="fila-formulario">
    <div class="grupo-formulario"><label>Madre</label><input type="texto"></div>
    <div class="grupo-formulario"><label>Teléfono</label><input type="telefono"></div>
  </div>
  <div class="grupo-formulario">
    <label>Vive con</label>
    <select>
      <option>Padres</option><option>Mamá</option><option>Papá</option>
      <option>Abuelos</option><option>Tíos</option><option>Otro</option>
    </select>
  </div>
  <div class="fila-formulario">
    <div class="grupo-formulario"><label>Persona Autorizada</label><input type="texto"></div>
    <div class="grupo-formulario"><label>Parentesco</label><input type="texto"></div>
    <div class="grupo-formulario"><label>Teléfono</label><input type="telefono"></div>
  </div>

  <div class="nota">
    <p><strong>NOTA:</strong> Proporcionar copia del INE de los padres y 3era persona autorizada.</p>
    <p><strong>NOTA:</strong> Los datos proporcionados en el presente documento se tomarán para la gestión de becas, por lo que no se deberán modificar.</p>
  </div>

  <h2>Autorización</h2>
  <div class="fila-formulario">
    <div class="grupo-formulario"><label>Nombre y Firma del Padre o Tutor</label><input type="texto"></div>
    <div class="grupo-formulario"><label>Firma y Sello Oficina de Control Escolar</label><input type="texto"></div>
    <div class="grupo-formulario"><label>Firma y Sello Comité Escolar</label><input type="texto"></div>
  </div>

  <button>Guardar Inscripción</button>
</div>

<script>
  function iniciarSesion() {
    document.getElementById('inicio-sesion').classList.add('oculto');
    document.getElementById('formulario').classList.remove('oculto');
  }
</script>

</body>
</html>

