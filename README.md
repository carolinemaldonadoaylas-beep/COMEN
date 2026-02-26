# COMEN
Registro de Oportunidades
<!DOCTYPE html>
<html lang="es">
<head>
<meta charset="UTF-8" />
<meta name="viewport" content="width=device-width, initial-scale=1.0" />
<title>Registro de Oportunidades</title>
<style>
  body{
    font-family: Arial, sans-serif;
    background:#f4f6f9;
    margin:0;
    padding:20px;
  }
  .container{
    max-width:900px;
    margin:auto;
    background:#fff;
    padding:30px;
    border-radius:10px;
    box-shadow:0 4px 10px rgba(0,0,0,.1);
  }
  h2{
    text-align:center;
    color:#2c3e50;
    margin:0 0 20px 0;
  }
  label{
    font-weight:bold;
    display:block;
    margin-top:18px;
  }
  textarea, input[type="text"], input[type="date"]{
    width:100%;
    padding:10px;
    margin-top:6px;
    border-radius:6px;
    border:1px solid #cfcfcf;
    font-size:14px;
    box-sizing:border-box;
  }
  textarea{ resize:vertical; }
  /* Sombra (placeholder) */
  textarea::placeholder, input::placeholder{
    color:#9aa4af;
  }
  .checkbox-group{
    margin-top:8px;
    padding:10px 12px;
    border:1px solid #e1e6ee;
    border-radius:8px;
    background:#fbfcfe;
  }
  .checkbox-group label{
    font-weight:normal;
    margin-top:6px;
  }
  .other-input{
    display:none;
    margin-top:8px;
  }
  input[type="file"]{
    margin-top:10px;
  }
  /* Cuadro final Enviar registro */
  .submit-box{
    margin-top:24px;
    padding:18px;
    border:2px dashed #2c3e50;
    border-radius:10px;
    background:#f8fafc;
    text-align:center;
  }
  .submit-box button{
    padding:12px 28px;
    background:#2c3e50;
    color:#fff;
    border:none;
    border-radius:8px;
    cursor:pointer;
    font-size:16px;
  }
  .submit-box button:hover{
    background:#1a252f;
  }
</style>
<script>
  function toggleOther(idCheckbox, idInput){
    const checkbox = document.getElementById(idCheckbox);
    const input = document.getElementById(idInput);
    input.style.display = checkbox.checked ? "block" : "none";
    if(!checkbox.checked) input.value = "";
  }
</script>
</head>
<body>
  <div class="container">
    <h2>REGISTRO DE OPORTUNIDADES</h2>
    <form id="formRegistro">
      <label>1. Nombre del proyecto</label>
      <textarea rows="4"
        placeholder='Ejemplo del nombre del proyecto: "Proyecto para la implementación de ventiladores neonatales en la UCIN del Hospital XXX. Actualmente en levantamiento de requerimientos técnicos y validación de presupuesto."'></textarea>
      <label>2. ¿Qué necesita de Comen? (Puede marcar varias respuestas)</label>
      <div class="checkbox-group">
        <label><input type="checkbox"> Solicitar Especificaciones técnicas de los equipos de Comen</label>
        <label><input type="checkbox"> Revisión de Especificaciones técnicas del cliente</label>
        <label><input type="checkbox"> Solicitar Cotización de los equipos</label>
        <label>
          <input type="checkbox" id="otrosComen" onclick="toggleOther('otrosComen','inputOtrosComen')"> Otros
        </label>
        <input type="text" id="inputOtrosComen" class="other-input" placeholder="Especifique (Otros)">
      </div>
      <label>3. Nombre del Cliente o Clínica u Hospital que comprará y donde se instalará</label>
      <textarea rows="3"
        placeholder="Ejemplo: Comprador: GORE Arequipa - IREN SUR. Ejemplo: Essalud - Varios Hospitales, Maternidad-Maternidad"></textarea>
      <label>4. Etapa del Proyecto (Puede marcar varias respuestas)</label>
      <div class="checkbox-group">
        <label><input type="checkbox"> Estudio de mercado del sector público</label>
        <label><input type="checkbox"> Estudio de mercado del sector privado</label>
        <label><input type="checkbox"> Licitación en curso</label>
        <label><input type="checkbox"> Etapa final de negociación con cliente privado</label>
        <label>
          <input type="checkbox" id="otrosEtapa" onclick="toggleOther('otrosEtapa','inputOtrosEtapa')"> Otros
        </label>
        <input type="text" id="inputOtrosEtapa" class="other-input" placeholder="Especifique (Otros)">
      </div>
      <label>5. Fecha estimada para ganar la buena pro y/o la orden del cliente final</label>
      <input type="date">
      <label>6. Adjuntar los documentos para ser analizados</label>
      <input type="file" multiple accept=".png,.pdf,.jpg,.jpeg">
      <div class="submit-box">
        <button type="submit">Enviar registro</button>
      </div>
    </form>
  </div>
</body>
</html>
