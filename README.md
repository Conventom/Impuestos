<html><head><base href="." /><title>Sistema de Control de Impuestos</title>
<style>
:root {
  --primary: #002B7F;      /* National blue */
  --secondary: #003399;    /* Slightly lighter blue */
  --success: #27ae60;      /* Keep success green */
  --danger: #c0392b;       /* Keep danger red */
  --warning: #f39c12;      /* Keep warning orange */
  --light: #E8F0FF;       /* Light blue tinted background */
}

* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
  font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
}

.menu-item i {
  margin-right: 8px;
}

body {
  background: var(--light);
}

#login-overlay {
  background: rgba(0, 0, 0, 0.8);
}

#login-overlay .modal {
  padding: 2rem;
  box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
}

#login-overlay input {
  width: 100%;
  padding: 0.75rem;
  border: 1px solid #ddd;
  border-radius: 4px;
  font-size: 1rem;
}

#login-overlay .btn-primary {
  margin-top: 1rem;
}

.navbar {
  display: flex;
  align-items: center;
  gap: 1rem;
  background: var(--primary);
  background: linear-gradient(to bottom, var(--primary), var(--secondary));
  padding: 1rem;
  color: white;
}

.logo-container {
  width: 60px;
  height: 60px;
  background: white;
  border-radius: 8px;
  padding: 5px;
  display: flex;
  align-items: center;
  justify-content: center;
}

.logo-container img {
  max-width: 100%;
  max-height: 100%;
  object-fit: contain;
}

.navbar-content {
  flex: 1;
}

.menu {
  display: flex;
  gap: 1rem;
}

.menu-dropdown {
  position: relative;
  display: inline-block;
}

.dropdown-content {
  display: none;
  position: absolute;
  background: var(--primary);
  min-width: 200px;
  box-shadow: 0 8px 16px rgba(0,0,0,0.2);
  z-index: 1;
  border-radius: 4px;
  margin-top: 4px;
}

.menu-dropdown:hover .dropdown-content {
  display: block;
}

.dropdown-item {
  color: white;
  padding: 0.5rem 1rem;
  text-decoration: none;
  display: flex;
  align-items: center;
  cursor: pointer;
}

.dropdown-item:hover {
  background: var(--secondary);
}

.dropdown-item i {
  margin-right: 8px;
}

.menu-item {
  background: var(--secondary);
  color: white;
  padding: 0.5rem 1rem;
  border-radius: 4px;
  cursor: pointer;
  transition: all 0.3s ease;
  display: flex;
  align-items: center;
}

.menu-item:hover {
  background: var(--primary);
}

.content {
  padding: 2rem;
}

.section {
  display: none;
  background: linear-gradient(to bottom, #F5F8FF, #FFFFFF);
  padding: 2rem;
  border-radius: 8px;
  box-shadow: 0 2px 4px rgba(0,0,0,0.1);
}

.section.active {
  display: block;
}

.form-group {
  margin-bottom: 1rem;
}

label {
  display: block;
  margin-bottom: 0.5rem;
  color: var(--primary);
}

input, select {
  width: 100%;
  padding: 0.5rem;
  border: 1px solid #ddd;
  border-radius: 4px;
}

button {
  background: var(--primary);
  color: white;
  border: none;
  padding: 0.5rem 1rem;
  border-radius: 4px;
  cursor: pointer;
}

button:hover {
  background: var(--secondary);
}

table {
  width: 100%;
  border-collapse: collapse;
  margin-top: 1rem;
}

th, td {
  padding: 0.75rem 1rem; /* Increased horizontal padding */
  border: 1px solid #ddd;
  text-align: left;
  white-space: nowrap; /* Prevent text wrapping */
}

th {
  background: var(--primary);
  color: white;
}

.status {
  padding: 0.25rem 0.5rem;
  border-radius: 4px;
  color: white;
}

.status.vencido {
  background: var(--danger);
}

.status.aldia {
  background: var(--success);
}

.estado-activo {
  color: var(--success);
  font-weight: bold;
}

.estado-inactivo {
  color: var(--danger);
  font-weight: bold;
}

.form-columns {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 2rem;
}

.column {
  display: flex;
  flex-direction: column;
  gap: 1rem;
}

.action-buttons {
  margin-bottom: 1rem;
  display: flex;
  gap: 1rem;
}

.modal-overlay {
  display: none;
  position: fixed;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  background: rgba(0, 0, 0, 0.5);
  z-index: 1000;
}

.modal {
  position: fixed;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  background: linear-gradient(to bottom, #F5F8FF, #FFFFFF);
  border: 2px solid var(--primary);
  padding: 2rem;
  border-radius: 8px;
  width: 95%; /* Increased from 90% */
  max-width: 1400px; /* Increased from 1200px */
  overflow-y: auto;
  z-index: 1001;
}

.modal-close {
  position: absolute;
  top: 1rem;
  right: 1rem;
  background: var(--danger);
  color: white;
  border: none;
  padding: 0.5rem 1rem;
  border-radius: 4px;
  cursor: pointer;
}

.section table {
  display: none;
}

.calendar-filters {
  display: flex;
  gap: 1rem;
  margin-bottom: 1rem;
}

.calendar-filters .form-group {
  flex: 1;
  max-width: 200px;
}

#calendario-table td {
  padding: 0.75rem;
}

#calendario-table tr:nth-child(even) {
  background-color: #f8f9fa;
}

#calendario-table tr:hover {
  background-color: #e9ecef;
}

.checkbox-group {
  border: 1px solid #ddd;
  padding: 10px;
  border-radius: 4px;
  max-height: 200px;
  overflow-y: auto;
}

.checkbox-item {
  display: flex;
  align-items: center;
  margin-bottom: 8px;
}

.checkbox-item input[type="checkbox"] {
  width: auto;
  margin-right: 8px;
}

.checkbox-item label {
  margin: 0;
  flex: 1;
}

.btn-primary {
  background: var(--primary);
  color: white;
  border: none;
  padding: 0.5rem 1rem;
  border-radius: 4px;
  cursor: pointer;
  display: flex;
  align-items: center;
  gap: 0.5rem;
}

.btn-primary:hover {
  background: var(--secondary);
}

.btn-primary i {
  font-size: 0.9em;
}

.calendario-mensual {
  width: 100%;
  border-collapse: collapse;
  margin-top: 1rem;
}

.calendario-mensual th,
.calendario-mensual td {
  padding: 0.75rem;
  border: 1px solid #ddd;
  text-align: left;
}

.calendario-mensual th {
  background: var(--primary);
  color: white;
}

.calendario-mensual tr:nth-child(even) {
  background-color: #f8f9fa;
}

.calendario-mensual tr:hover {
  background-color: #e9ecef;
}

.modal h3 {
  margin-bottom: 1rem;
  color: var(--primary);
}

.calendar-grid {
  display: grid;
  grid-template-columns: repeat(7, 1fr);
  gap: 1px;
  background: var(--secondary);
  padding: 1px;
  margin: 15px 0;
  max-width: 600px; /* Reduced from 800px */
}

.calendar-header {
  background: var(--primary);
  color: white;
  padding: 6px; /* Reduce padding */
  text-align: center;
  font-weight: bold;
  font-size: 0.9em; /* Reduce font size */
}

.calendar-day {
  background: #F5F8FF;
  min-height: 70px; /* Reduced from 80px */
  padding: 6px; /* Reduced from 8px */
  position: relative;
}

.day-number {
  position: absolute;
  top: 3px;
  left: 3px;
  font-weight: bold;
  color: var(--primary);
  font-size: 0.9em; /* Reduce font size */
}

.event-dots {
  position: absolute;
  bottom: 3px;
  left: 3px;
  display: flex;
  gap: 3px; /* Increased from 2px to give more space between larger dots */
}

.event-dot {
  width: 10px; /* Increased from 6px */
  height: 10px; /* Increased from 6px */
  border-radius: 50%;
  background: var(--primary); /* Changed to match primary color variable */
}

.events-list {
  margin-top: 15px;
  border-top: 2px solid var(--primary);
  padding-top: 15px;
  font-size: 0.9em; /* Reduce font size */
}

.event-day {
  margin: 15px 0;
  padding: 12px;
  background: white;
  border-radius: 6px;
  box-shadow: 0 2px 4px rgba(0,0,0,0.1);
}

.event-item {
  margin: 8px 0;
  padding: 12px;
  border-left: 3px solid var(--primary);
  background: #F5F8FF;
  border-radius: 6px;
}

.event-name {
  font-size: 1em; /* Reduce font size */
}

.event-desc {
  font-size: 0.9em; /* Reduce font size */
}

.calendario-anual {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  gap: 1.5rem;
  padding: 1rem;
}

.calendario-anual-mes {
  background: linear-gradient(to bottom, #F5F8FF, #FFFFFF);
  border: 1px solid var(--primary);
  padding: 1rem;
  box-shadow: 0 2px 4px rgba(0,0,0,0.1);
}

.calendario-anual-mes h3 {
  color: var(--primary);
  border-bottom: 2px solid var(--primary);
  padding-bottom: 0.5rem;
  margin-bottom: 1rem;
  text-align: center;
}

.evento-anual {
  border-left: 4px solid var(--primary);
  background: #F5F8FF;
  padding: 0.75rem;
  margin: 0.5rem 0;
  border-radius: 0 4px 4px 0;
}

.evento-anual-fecha {
  color: var(--primary);
  font-weight: bold;
  margin-bottom: 0.25rem;
}

.evento-anual-impuesto {
  font-weight: 500;
  margin-bottom: 0.25rem;
}

.evento-anual-desc {
  font-size: 0.9em;
  color: #666;
}

#contribuyentes-table {
  min-width: 100%;
  overflow-x: auto;
  display: block;
}

.tax-paid-checkbox {
  appearance: none;
  -webkit-appearance: none;
  width: 20px;
  height: 20px;
  border: 2px solid var(--primary);
  border-radius: 50%;
  margin: 0 4px;
  cursor: pointer;
  position: relative;
  vertical-align: middle;
  transition: all 0.3s ease;
}

.tax-paid-checkbox:checked {
  background-color: var(--success);
  border-color: var(--success);
}

.tax-paid-checkbox:checked::after {
  content: '✓';
  position: absolute;
  color: white;
  font-size: 12px;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
}

.tax-list {
  display: flex;
  flex-wrap: wrap;
  gap: 8px;
  align-items: center;
}

.tax-item {
  display: flex;
  align-items: center;
  background: #F5F8FF;
  padding: 4px 8px;
  border-radius: 4px;
  border: 1px solid #ddd;
}

.file-upload-zone {
  border: 2px dashed var(--primary);
  padding: 2rem;
  text-align: center;
  margin: 1rem 0;
  border-radius: 8px;
  background: #f8f9fa;
  transition: all 0.3s ease;
  cursor: pointer;
}

.file-upload-zone.dragover {
  background: #e3e8ff;
  border-color: var(--secondary);
}

.file-upload-zone i {
  font-size: 2rem;
  color: var(--primary);
  margin-bottom: 1rem;
}

.uploaded-file {
  display: flex;
  align-items: center;
  gap: 1rem;
  background: white;
  padding: 0.5rem 1rem;
  border-radius: 4px;
  margin-top: 1rem;
}

.uploaded-file i {
  color: var(--danger);
  cursor: pointer;
}

/* Add these styles for the form inputs in the payment modal */
.modal .form-group input {
  width: 100%;
  padding: 8px;
  margin-bottom: 15px;
  border: 1px solid #ddd;
  border-radius: 4px;
}

/* Add to existing CSS */
.modal .form-group input[type="date"] {
  width: 100%;
  padding: 8px;
  margin-bottom: 15px;
  border: 1px solid #ddd;
  border-radius: 4px;
}
</style>
<link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0/css/all.min.css">
<script src="https://cdnjs.cloudflare.com/ajax/libs/xlsx/0.18.5/xlsx.full.min.js"></script>
</head>
<body>
<div id="login-overlay" class="modal-overlay" style="display: block;">
  <div class="modal" style="max-width: 400px;">
    <h2>Iniciar Sesión</h2>
    <div id="login-form">
      <div class="form-group">
        <label>Usuario</label>
        <input type="text" id="username" placeholder="Ingrese su usuario">
      </div>
      <div class="form-group">
        <label>Contraseña</label>
        <input type="password" id="password" placeholder="Ingrese su contraseña">
      </div>
      <div style="text-align: right; margin-bottom: 1rem;">
        <a href="#" onclick="showRecoveryForm()" style="color: var(--primary); text-decoration: none;">
          ¿Olvidó su contraseña?
        </a>
      </div>
      <button onclick="login()" class="btn-primary" style="width: 100%;">
        <i class="fas fa-sign-in-alt"></i> Iniciar Sesión
      </button>
    </div>
    <div id="recovery-form" style="display: none;">
      <div class="form-group">
        <label>Usuario</label>
        <input type="text" id="recovery-username" placeholder="Ingrese su usuario">
      </div>
      <div class="form-group">
        <label>Pregunta de Seguridad</label>
        <p>¿Cuál es su número de identificación?</p>
        <input type="text" id="security-answer" placeholder="Ingrese su respuesta">
      </div>
      <div style="display: flex; gap: 1rem; margin-top: 1rem;">
        <button onclick="recoverPassword()" class="btn-primary" style="flex: 1;">
          <i class="fas fa-key"></i> Recuperar Contraseña
        </button>
        <button onclick="showLoginForm()" style="flex: 1; background: var(--secondary);">
          <i class="fas fa-arrow-left"></i> Volver
        </button>
      </div>
    </div>
  </div>
</div>

<nav class="navbar">
  <div class="logo-container">
    <img src="" alt="Logo de la empresa" id="logo-img">
  </div>
  <div class="navbar-content">
    <h1>Sistema de Control de Impuestos</h1>
    <div class="menu">
      <div class="menu-item" onclick="showSection('contribuyentes')">
        <i class="fas fa-users"></i>
        Contribuyentes
      </div>
      <div class="menu-item" onclick="showSection('tipos-impuestos')">
        <i class="fas fa-file-invoice-dollar"></i>
        Tipos de Impuestos
      </div>
      <div class="menu-item" onclick="showSection('calendario-tributario')">
        <i class="fas fa-calendar-alt"></i>
        Calendario Tributario
      </div>
      <div class="menu-item" onclick="showSection('impuestos-pagados')">
        <i class="fas fa-check-double"></i>
        Impuestos Pagados
      </div>
      <div class="menu-dropdown">
        <div class="menu-item">
          <i class="fas fa-ellipsis-h"></i>
          Otros
        </div>
        <div class="dropdown-content">
          <div class="dropdown-item" onclick="showSection('impuestos-vencidos')">
            <i class="fas fa-clock"></i>
            Impuestos Vencidos
          </div>
          <div class="dropdown-item" onclick="showSection('impuestos-aldia')">
            <i class="fas fa-check-circle"></i>
            Impuestos al Día
          </div>
        </div>
      </div>
    </div>
  </div>
</nav>

<div class="content">
  <!-- Sección Contribuyentes -->
  <div id="contribuyentes" class="section">
    <h2>Gestión de Contribuyentes</h2>
    <div class="action-buttons">
      <button onclick="showListadoContribuyentes()">Ver Listado de Contribuyentes</button>
      <button onclick="importarExcel()" class="btn-primary">
        <i class="fas fa-file-upload"></i> Importar desde Excel
      </button>
    </div>
    <form id="contribuyente-form">
      <div class="form-columns">
        <div class="column">
          <div class="form-group">
            <label>NIT</label>
            <input type="text" id="dni" required>
          </div>
          <div class="form-group">
            <label>Nombre/Razón Social</label>
            <input type="text" id="nombre" required>
          </div>
          <div class="form-group">
            <label>Fecha de Nacimiento</label>
            <input type="date" id="fechaNacimiento" required>
          </div>
          <div class="form-group">
            <label>Contraseña A.V.</label>
            <input type="text" id="contrasenaAV" required>
          </div>
          <div class="form-group">
            <label>Contraseña Para Certificar</label>
            <input type="text" id="contrasenaCertificar" required>
          </div>
        </div>
        <div class="column">
          <div class="form-group">
            <label>Régimen Tributario</label>
            <select id="regimenTributario" required>
              <option value="">Seleccione un régimen</option>
              <option value="pequeno">Pequeño Contribuyente</option>
              <option value="simplificado">Régimen Simplificado</option>
              <option value="general">Régimen General</option>
              <option value="especial">Régimen Especial</option>
            </select>
          </div>
          <div class="form-group">
            <label>Estado</label>
            <select id="estado" required>
              <option value="activo">Activo</option>
              <option value="inactivo">Inactivo</option>
            </select>
          </div>
          <div class="form-group">
            <label>Fecha de Activación</label>
            <input type="date" id="fechaActivacion">
          </div>
          <div class="form-group">
            <label>Fecha de Inactivación</label>
            <input type="date" id="fechaInactivacion">
          </div>
        </div>
        <!-- Add this new column to the form-columns div in the contribuyentes section -->
        <div class="column">
          <div class="form-group">
            <label>Impuestos Asignados</label>
            <div id="impuestos-asignados" class="checkbox-group">
              <!-- Will be populated dynamically -->
            </div>
          </div>
        </div>
      </div>
      <div style="display: flex; gap: 1rem; margin-top: 1rem;">
        <button type="submit">Registrar Contribuyente</button>
        <button type="button" onclick="cancelarFormContribuyente()" style="background: var(--danger);">Cancelar</button>
      </div>
    </form>
    <table id="contribuyentes-table">
      <thead>
        <tr>
          <th>NIT</th>
          <th>Nombre</th>
          <th>Fecha Nacimiento</th>
          <th>Régimen Tributario</th>
          <th>Estado</th>
          <th>Contraseña A.V.</th>
          <th>Contraseña Para Certificar</th>
          <th>Impuestos Asignados</th>
          <th>Acciones</th>
        </tr>
      </thead>
      <tbody></tbody>
    </table>
  </div>

  <!-- Sección Tipos de Impuestos -->
  <div id="tipos-impuestos" class="section">
    <h2>Tipos de Impuestos</h2>
    <div class="action-buttons">
      <button onclick="showListadoImpuestos()">Ver Listado de Tipos de Impuestos</button>
    </div>
    <form id="impuesto-form">
      <div class="form-group">
        <label>Código</label>
        <input type="text" id="codigo" required>
      </div>
      <div class="form-group">
        <label>Nombre del Impuesto</label>
        <input type="text" id="nombre-impuesto" required>
      </div>
      <div class="form-group">
        <label>Periodicidad</label>
        <select id="periodicidad">
            <option value="findemes">Fin de mes siguiente</option>
            <option value="primeros13dias">Primeros 13 días hábiles del siguiente mes</option>
            <option value="trimestral">Trimestral fin del mes siguiente</option>
            <option value="primeros24dias">Primeros 24 días hábiles del siguiente mes</option>
            <option value="semestral">Semestral fin de mes siguiente</option>
            <option value="anual">31 de Marzo del siguiente año</option>
            <option value="primeros10dias">Primeros 10 días hábiles del siguiente mes</option>
            <option value="primeros20dias">Primeros 20 días hábiles del siguiente mes</option>
        </select>
      </div>
      <button type="submit">Registrar Impuesto</button>
    </form>
    <table id="impuestos-table">
      <thead>
        <tr>
          <th>Código</th>
          <th>Nombre</th>
          <th>Periodicidad</th>
          <th>Acciones</th>
        </tr>
      </thead>
      <tbody></tbody>
    </table>
  </div>

  <!-- Sección Impuestos Vencidos -->
  <div id="impuestos-vencidos" class="section">
    <h2>Impuestos Vencidos</h2>
    <div class="action-buttons">
      <button onclick="showListadoVencidos()">Ver Listado de Impuestos Vencidos</button>
    </div>
    <table id="vencidos-table">
      <thead>
        <tr>
          <th>Contribuyente</th>
          <th>Impuesto</th>
          <th>Fecha Vencimiento</th>
          <th>Días Vencido</th>
          <th>Monto</th>
        </tr>
      </thead>
      <tbody></tbody>
    </table>
  </div>

  <!-- Sección Impuestos al Día -->
  <div id="impuestos-aldia" class="section">
    <h2>Impuestos al Día</h2>
    <div class="action-buttons">
      <button onclick="showListadoAlDia()">Ver Listado de Impuestos al Día</button>
    </div>
    <table id="aldia-table">
      <thead>
        <tr>
          <th>Contribuyente</th>
          <th>Impuesto</th>
          <th>Último Pago</th>
          <th>Próximo Vencimiento</th>
        </tr>
      </thead>
      <tbody></tbody>
    </table>
  </div>

  <!-- Sección Calendario Tributario -->
  <div id="calendario-tributario" class="section">
    <h2>Calendario Tributario</h2>
    <div class="action-buttons">
      <button onclick="showCalendarioTributario()">Asignar Fecha de Declaración</button>
    </div>
    <div class="calendar-filters">
      <div class="form-group">
        <label>Año</label>
        <select id="calendar-year" onchange="actualizarCalendarioTributario()">
          <!-- Will be populated dynamically -->
        </select>
      </div>
      <div class="form-group">
        <label>Tipo de Impuesto</label>
        <select id="calendar-tax-type" onchange="actualizarCalendarioTributario()">
          <option value="todos">Todos los impuestos</option>
        </select>
      </div>
      <!-- New button -->
      <div class="form-group">
        <label>&nbsp;</label>
        <button onclick="mostrarCalendarioMensual()" class="btn-primary">
          <i class="fas fa-calendar-day"></i> Ver Calendario Mensual
        </button>
      </div>
      <div class="form-group">
        <label>&nbsp;</label>
        <button onclick="mostrarCalendarioAnual()" class="btn-primary">
          <i class="fas fa-calendar"></i> Ver Calendario Anual
        </button>
      </div>
    </div>
    <table id="calendario-table">
      <thead>
        <tr>
          <th>Mes</th>
          <th>Tipo de Impuesto</th>
          <th>Periodicidad</th>
          <th>Fecha Límite</th>
          <th>Descripción</th>
          <th>Acciones</th>
        </tr>
      </thead>
      <tbody></tbody>
    </table>
  </div>
  
  <!-- Sección Impuestos Pagados -->
  <div id="impuestos-pagados" class="section">
    <h2>Impuestos Pagados</h2>
    <div class="action-buttons">
      <button onclick="showListadoPagados()">Ver Listado de Impuestos Pagados</button>
    </div>
    <table id="pagados-table">
      <thead>
        <tr>
          <th>Contribuyente</th>
          <th>Impuesto</th>
          <th>Formulario SAT</th>
          <th>Número de Acceso</th>
          <th>Fecha de Pago</th>
          <th>Acciones</th>
        </tr>
      </thead>
      <tbody></tbody>
    </table>
  </div>
</div>

<script>
let contribuyentes = [];
let tiposImpuestos = [];
let contribuyentesImpuestos = [];
let pagosImpuestos = [];

document.addEventListener('DOMContentLoaded', () => {
  document.getElementById('login-overlay').style.display = 'block';
  showSection('contribuyentes');
  
  // Set default activation date to current date
  const today = new Date().toISOString().split('T')[0];
  document.getElementById('fechaActivacion').value = today;
  
  populateImpuestosCheckboxes();
  actualizarSelectAnios(); // Add this line

  // Add logo upload functionality
  const logoImg = document.getElementById('logo-img');
  
  // Create a hidden file input
  const fileInput = document.createElement('input');
  fileInput.type = 'file';
  fileInput.accept = 'image/*';
  fileInput.style.display = 'none';
  document.body.appendChild(fileInput);

  // Make the logo container clickable to trigger file selection
  const logoContainer = document.querySelector('.logo-container');
  logoContainer.style.cursor = 'pointer';
  logoContainer.title = 'Haga clic para cargar un logo';
  logoContainer.addEventListener('click', () => fileInput.click());

  // Handle file selection
  fileInput.addEventListener('change', (e) => {
    const file = e.target.files[0];
    if (file) {
      const reader = new FileReader();
      reader.onload = (event) => {
        logoImg.src = event.target.result;
        // Store in localStorage to persist across page reloads
        localStorage.setItem('companyLogo', event.target.result);
      };
      reader.readAsDataURL(file);
    }
  });

  // Load saved logo if exists
  const savedLogo = localStorage.getItem('companyLogo');
  if (savedLogo) {
    logoImg.src = savedLogo;
  }

  document.getElementById('contribuyente-form').addEventListener('submit', (e) => {
    e.preventDefault();
    const impuestosSeleccionados = Array.from(document.querySelectorAll('#impuestos-asignados input[type="checkbox"]:checked'))
      .map(checkbox => checkbox.value);
    
    const contribuyente = {
      dni: document.getElementById('dni').value,
      nombre: document.getElementById('nombre').value,
      fechaNacimiento: document.getElementById('fechaNacimiento').value,
      contrasenaAV: document.getElementById('contrasenaAV').value,
      contrasenaCertificar: document.getElementById('contrasenaCertificar').value,
      regimenTributario: document.getElementById('regimenTributario').value,
      estado: document.getElementById('estado').value,
      impuestosAsignados: impuestosSeleccionados,
      impuestosPagados: {}
    };
    
    contribuyentes.push(contribuyente);
    actualizarTablaContribuyentes();
    e.target.reset();
  });

  document.getElementById('impuesto-form').addEventListener('submit', (e) => {
    e.preventDefault();
    const impuesto = {
      codigo: document.getElementById('codigo').value,
      nombre: document.getElementById('nombre-impuesto').value,
      periodicidad: document.getElementById('periodicidad').value
    };
    tiposImpuestos.push(impuesto);
    actualizarTablaImpuestos();
    e.target.reset();
  });

  actualizarSelectTiposImpuestos();
  actualizarCalendarioTributario();
});

function login() {
  const username = document.getElementById('username').value;
  const password = document.getElementById('password').value;

  if (username === 'Maynor' && password === '1977362013') {
    document.getElementById('login-overlay').style.display = 'none';
  } else {
    alert('Usuario o contraseña incorrectos');
  }
}

function showRecoveryForm() {
  document.getElementById('login-form').style.display = 'none';
  document.getElementById('recovery-form').style.display = 'block';
}

function showLoginForm() {
  document.getElementById('login-form').style.display = 'block';
  document.getElementById('recovery-form').style.display = 'none';
}

function recoverPassword() {
  const username = document.getElementById('recovery-username').value;
  const securityAnswer = document.getElementById('security-answer').value;

  if (username === 'Maynor' && securityAnswer === '1977362013') {
    alert('Su contraseña es: 1977362013');
    showLoginForm();
  } else {
    alert('Los datos ingresados no son correctos');
  }
}

// Add this to ensure login screen shows on page load
document.addEventListener('DOMContentLoaded', () => {
  document.getElementById('login-overlay').style.display = 'block';
});

// Add this to hide content until logged in
function showSection(sectionId) {
  // Check if logged in
  if (document.getElementById('login-overlay').style.display !== 'none') {
    return; // Don't show sections if not logged in
  }
  
  document.querySelectorAll('.section').forEach(section => {
    section.classList.remove('active');
  });
  document.getElementById(sectionId).classList.add('active');
}

function actualizarSelectAnios() {
  const selectYear = document.getElementById('calendar-year');
  const currentYear = new Date().getFullYear();
  const startYear = currentYear - 2;
  const endYear = currentYear + 10;
  
  selectYear.innerHTML = '';
  
  for(let year = startYear; year <= endYear; year++) {
    const option = document.createElement('option');
    option.value = year;
    option.textContent = year;
    if(year === currentYear) {
      option.selected = true;
    }
    selectYear.appendChild(option);
  }
}

function populateImpuestosCheckboxes() {
  const container = document.getElementById('impuestos-asignados');
  container.innerHTML = tiposImpuestos.map(impuesto => `
    <div class="checkbox-item">
      <input type="checkbox" id="impuesto-${impuesto.codigo}" value="${impuesto.codigo}">
      <label for="impuesto-${impuesto.codigo}">${impuesto.nombre}</label>
    </div>
  `).join('');
}

function actualizarTablaContribuyentes() {
  const tbody = document.querySelector('#contribuyentes-table tbody');
  tbody.innerHTML = '';
  contribuyentes.forEach(c => {
    const impuestosAsignadosHTML = c.impuestosAsignados
      .map(codigo => {
        const impuesto = tiposImpuestos.find(i => i.codigo === codigo);
        // Skip if the tax is already paid
        if (!impuesto || (c.impuestosPagados && c.impuestosPagados[codigo])) return '';
        return `
          <div class="tax-item" id="tax-item-${c.dni}-${codigo}">
            <input type="checkbox" 
                   class="tax-paid-checkbox" 
                   id="paid-${c.dni}-${codigo}"
                   onchange="marcarImpuestoPagado('${c.dni}', '${codigo}', this.checked)">
            <label for="paid-${c.dni}-${codigo}">${impuesto.nombre}</label>
          </div>
        `;
      })
      .filter(html => html !== '') // Remove empty strings
      .join('');
      
    const tr = document.createElement('tr');
    tr.innerHTML = `
      <td>${c.dni}</td>
      <td>${c.nombre}</td>
      <td>${c.fechaNacimiento}</td>
      <td>${c.regimenTributario}</td>
      <td class="${c.estado === 'activo' ? 'estado-activo' : 'estado-inactivo'}">${c.estado}</td>
      <td>${c.contrasenaAV}</td>
      <td>${c.contrasenaCertificar}</td>
      <td><div class="tax-list">${impuestosAsignadosHTML}</div></td>
      <td>
        <button onclick="editarContribuyente('${c.dni}')">Editar</button>
        <button onclick="eliminarContribuyente('${c.dni}')">Eliminar</button>
      </td>
    `;
    tbody.appendChild(tr);
  });
}

function marcarImpuestoPagado(dni, codigoImpuesto, checked) {
  if (checked) {
    // Get current date to determine previous month (since payments are for previous period)
    const currentDate = new Date();
    const previousMonth = currentDate.getMonth() === 0 ? 11 : currentDate.getMonth() - 1;
    const previousMonthYear = currentDate.getMonth() === 0 ? currentDate.getFullYear() - 1 : currentDate.getFullYear();
    const meses = [
      'Enero', 'Febrero', 'Marzo', 'Abril', 'Mayo', 'Junio',
      'Julio', 'Agosto', 'Septiembre', 'Octubre', 'Noviembre', 'Diciembre'
    ];

    const modalContent = `
      <div class="form-group">
        <label>Número de Formulario SAT</label>
        <input type="text" id="numero-formulario-sat" required 
               placeholder="Ingrese el número de formulario SAT">
      </div>
      <div class="form-group">
        <label>Número de Acceso</label>
        <input type="text" id="numero-acceso" required 
               placeholder="Ingrese el número de acceso">
      </div>
      <div class="form-group">
        <label>Fecha de Pago</label>
        <input type="date" id="fecha-pago" required>
      </div>
      <div class="form-group">
        <label>Periodo que corresponde al pago:</label>
        <p style="color: var(--primary); font-weight: bold; margin: 10px 0;">
          ${meses[previousMonth]} ${previousMonthYear}
        </p>
      </div>
      <div class="form-group">
        <label>Documento PDF del Formulario</label>
        <div id="dropzone" class="file-upload-zone">
          <i class="fas fa-file-pdf"></i>
          <p>Arrastre aquí el documento PDF o haga clic para seleccionarlo</p>
          <input type="file" id="pdf-file" accept=".pdf" style="display: none;">
        </div>
        <div id="uploaded-files"></div>
      </div>
      <button onclick="confirmarPagoImpuesto('${dni}', '${codigoImpuesto}', '${meses[previousMonth]}', '${previousMonthYear}')" class="btn-primary">
        Confirmar Pago
      </button>
    `;
    showModal(modalContent, 'Registro de Pago de Impuesto');
    
    // Set default date to today
    document.getElementById('fecha-pago').valueAsDate = new Date();
    
    // Add dropzone functionality
    const dropzone = document.getElementById('dropzone');
    const fileInput = document.getElementById('pdf-file');
    const uploadedFiles = document.getElementById('uploaded-files');
    
    dropzone.onclick = () => fileInput.click();
    
    fileInput.onchange = (e) => handleFileUpload(e.target.files[0]);
    
    dropzone.ondragover = (e) => {
      e.preventDefault();
      dropzone.classList.add('dragover');
    };
    
    dropzone.ondragleave = () => dropzone.classList.remove('dragover');
    
    dropzone.ondrop = (e) => {
      e.preventDefault();
      dropzone.classList.remove('dragover');
      const file = e.dataTransfer.files[0];
      if (file && file.type === 'application/pdf') {
        handleFileUpload(file);
      } else {
        alert('Por favor, seleccione un archivo PDF');
      }
    };
  }
}

// Update confirmarPagoImpuesto to include month and year
function confirmarPagoImpuesto(dni, codigoImpuesto, mes, anio) {
  const numeroFormulario = document.getElementById('numero-formulario-sat').value;
  const numeroAcceso = document.getElementById('numero-acceso').value;
  const fechaPago = document.getElementById('fecha-pago').value;
  const pdfFile = document.getElementById('pdf-file').files[0];
  
  if (numeroFormulario && numeroAcceso && fechaPago) {
    if (!pdfFile) {
      if (!confirm('No ha adjuntado el documento PDF. ¿Desea continuar sin él?')) {
        return;
      }
    }
    
    const contribuyente = contribuyentes.find(c => c.dni === dni);
    if (contribuyente) {
      if (!contribuyente.impuestosPagados) {
        contribuyente.impuestosPagados = {};
      }
      
      // Convert PDF file to base64 for storage
      if (pdfFile) {
        const reader = new FileReader();
        reader.onload = function(e) {
          contribuyente.impuestosPagados[codigoImpuesto] = {
            pagado: true,
            numeroFormulario,
            numeroAcceso,
            fechaPago,
            periodoMes: mes,
            periodoAnio: anio,
            documentoPDF: {
              nombre: pdfFile.name,
              tipo: pdfFile.type,
              datos: e.target.result
            }
          };
          
          // Hide the tax item
          const taxItem = document.querySelector(`#tax-item-${dni}-${codigoImpuesto}`);
          if (taxItem) {
            taxItem.style.display = 'none';
          }
          
          actualizarTablaPagados();
          closeModal(document.querySelector('.modal-close'));
        };
        reader.readAsDataURL(pdfFile);
      } else {
        contribuyente.impuestosPagados[codigoImpuesto] = {
          pagado: true,
          numeroFormulario,
          numeroAcceso,
          fechaPago,
          periodoMes: mes,
          periodoAnio: anio,
          documentoPDF: null
        };
        
        const taxItem = document.querySelector(`#tax-item-${dni}-${codigoImpuesto}`);
        if (taxItem) {
          taxItem.style.display = 'none';
        }
        
        actualizarTablaPagados();
        closeModal(document.querySelector('.modal-close'));
      }
    }
  } else {
    alert('Por favor complete todos los campos requeridos');
  }
}

// Update actualizarTablaPagados to show period information
function actualizarTablaPagados() {
  const tbody = document.querySelector('#pagados-table tbody');
  tbody.innerHTML = '';
  
  contribuyentes.forEach(c => {
    if (c.impuestosPagados) {
      Object.entries(c.impuestosPagados).forEach(([codigoImpuesto, pago]) => {
        const impuesto = tiposImpuestos.find(i => i.codigo === codigoImpuesto);
        if (impuesto && pago.pagado) {
          const tr = document.createElement('tr');
          tr.innerHTML = `
            <td>${c.nombre}</td>
            <td>${impuesto.nombre}<br>
                <small style="color: var(--primary)">
                  Periodo: ${pago.periodoMes} ${pago.periodoAnio}
                </small>
            </td>
            <td>${pago.numeroFormulario}</td>
            <td>${pago.numeroAcceso}</td>
            <td>${pago.fechaPago}</td>
            <td>
              <div style="display: flex; gap: 8px;">
                <a href="https://declaraguate.sat.gob.gt/declaraguate-web/formularios/buscarFormulario.iface" 
                   target="_blank" 
                   class="btn-primary"
                   style="text-decoration: none;">
                  <i class="fas fa-external-link-alt"></i> Ver en SAT
                </a>
                ${pago.documentoPDF ? `
                  <button onclick="verPDF('${c.dni}', '${codigoImpuesto}')" class="btn-primary">
                    <i class="fas fa-file-pdf"></i> Ver PDF
                  </button>
                ` : ''}
              </div>
            </td>
          `;
          tbody.appendChild(tr);
        }
      });
    }
  });
}

function verPDF(dni, codigoImpuesto) {
  const contribuyente = contribuyentes.find(c => c.dni === dni);
  if (contribuyente && contribuyente.impuestosPagados[codigoImpuesto]?.documentoPDF) {
    const pdfData = contribuyente.impuestosPagados[codigoImpuesto].documentoPDF;
    
    // Create modal content with PDF viewer
    const modalContent = `
      <div style="height: 80vh; width: 100%;">
        <object
          data="${pdfData.datos}"
          type="application/pdf"
          width="100%"
          height="100%"
        >
          <p>Tu navegador no puede mostrar el PDF directamente. 
             <a href="${pdfData.datos}" target="_blank" download="${pdfData.nombre}">
               Haz clic aquí para descargar el archivo
             </a>
          </p>
        </object>
      </div>
    `;
    
    showModal(modalContent, `Visualización de ${pdfData.nombre}`);
  } else {
    alert('No se encontró el documento PDF asociado.');
  }
}

function showListadoPagados() {
  const table = document.querySelector('#pagados-table').cloneNode(true);
  showModal(table.outerHTML, 'Listado de Impuestos Pagados');
}

function actualizarTablaImpuestos() {
  const tbody = document.querySelector('#impuestos-table tbody');
  tbody.innerHTML = '';
  tiposImpuestos.forEach(i => {
    const tr = document.createElement('tr');
    tr.innerHTML = `
      <td>${i.codigo}</td>
      <td>${i.nombre}</td>
      <td>${i.periodicidad}</td>
      <td>
        <button onclick="editarImpuesto('${i.codigo}')">Editar</button>
        <button onclick="eliminarImpuesto('${i.codigo}')">Eliminar</button>
      </td>
    `;
    tbody.appendChild(tr);
  });
  actualizarSelectTiposImpuestos();
  populateImpuestosCheckboxes();
  actualizarCalendarioTributario();
}

function editarContribuyente(dni) {
  const contribuyente = contribuyentes.find(c => c.dni === dni);
  if (contribuyente) {
    document.getElementById('dni').value = contribuyente.dni;
    document.getElementById('nombre').value = contribuyente.nombre;
    document.getElementById('fechaNacimiento').value = contribuyente.fechaNacimiento;
    document.getElementById('contrasenaAV').value = contribuyente.contrasenaAV;
    document.getElementById('contrasenaCertificar').value = contribuyente.contrasenaCertificar;
    document.getElementById('regimenTributario').value = contribuyente.regimenTributario;
    document.getElementById('estado').value = contribuyente.estado;
    
    // Check the corresponding tax checkboxes
    document.querySelectorAll('#impuestos-asignados input[type="checkbox"]')
      .forEach(checkbox => {
        checkbox.checked = contribuyente.impuestosAsignados.includes(checkbox.value);
      });
  }
}

function eliminarContribuyente(dni) {
  contribuyentes = contribuyentes.filter(c => c.dni !== dni);
  actualizarTablaContribuyentes();
}

function editarImpuesto(codigo) {
  const impuesto = tiposImpuestos.find(i => i.codigo === codigo);
  if (impuesto) {
    document.getElementById('codigo').value = impuesto.codigo;
    document.getElementById('nombre-impuesto').value = impuesto.nombre;
    document.getElementById('periodicidad').value = impuesto.periodicidad;
  }
}

function eliminarImpuesto(codigo) {
  tiposImpuestos = tiposImpuestos.filter(i => i.codigo !== codigo);
  actualizarTablaImpuestos();
}

function generarDatosEjemplo() {
  const fechaActual = new Date();
  const impuestosVencidos = [
    {
      contribuyente: 'Juan Pérez',
      impuesto: 'Impuesto Predial',
      fechaVencimiento: '2023-10-15',
      diasVencido: 30,
      monto: 1500
    }
  ];

  const impuestosAlDia = [
    {
      contribuyente: 'María García',
      impuesto: 'Impuesto Vehicular',
      ultimoPago: '2023-11-15',
      proximoVencimiento: '2023-12-15'
    }
  ];

  actualizarTablaVencidos(impuestosVencidos);
  actualizarTablaAlDia(impuestosAlDia);
}

function actualizarTablaVencidos(datos) {
  const tbody = document.querySelector('#vencidos-table tbody');
  tbody.innerHTML = datos.map(d => `
    <tr>
      <td>${d.contribuyente}</td>
      <td>${d.impuesto}</td>
      <td>${d.fechaVencimiento}</td>
      <td>${d.diasVencido}</td>
      <td>$${d.monto}</td>
    </tr>
  `).join('');
}

function actualizarTablaAlDia(datos) {
  const tbody = document.querySelector('#aldia-table tbody');
  tbody.innerHTML = datos.map(d => `
    <tr>
      <td>${d.contribuyente}</td>
      <td>${d.impuesto}</td>
      <td>${d.ultimoPago}</td>
      <td>${d.proximoVencimiento}</td>
    </tr>
  `).join('');
}

function generarCalendarioTributario(year) {
  const meses = [
    'Enero', 'Febrero', 'Marzo', 'Abril', 'Mayo', 'Junio',
    'Julio', 'Agosto', 'Septiembre', 'Octubre', 'Noviembre', 'Diciembre'
  ];
  
  const calendario = [];
  
  tiposImpuestos.forEach(impuesto => {
    switch(impuesto.periodicidad) {
      case 'findemes':
        meses.forEach((mes, index) => {
          const nextMonth = (index + 2) > 12 ? 1 : (index + 2);
          const nextYear = (index + 2) > 12 ? parseInt(year) + 1 : year;
          const lastDay = new Date(nextYear, nextMonth, 0).getDate();
          
          calendario.push({
            mes: mes,
            impuesto: impuesto.nombre,
            periodicidad: 'Fin de mes siguiente',
            fechaLimite: `${nextYear}-${String(nextMonth).padStart(2, '0')}-${lastDay}`,
            descripcion: `Declaración y pago al fin del mes siguiente de ${impuesto.nombre}`
          });
        });
        break;
      case 'trimestral':
        [3, 6, 9, 12].forEach(month => {
          const nextMonth = month === 12 ? 1 : month + 1;
          const nextYear = month === 12 ? parseInt(year) + 1 : year;
          const lastDay = new Date(nextYear, nextMonth, 0).getDate();
          
          calendario.push({
            mes: meses[month - 1],
            impuesto: impuesto.nombre,
            periodicidad: 'Trimestral fin del mes siguiente',
            fechaLimite: `${nextYear}-${String(nextMonth).padStart(2, '0')}-${lastDay}`,
            descripcion: `Declaración y pago trimestral de ${impuesto.nombre}`
          });
        });
        break;

      case 'primeros13dias':
        meses.forEach((mes, index) => {
          const nextMonth = (index + 2) > 12 ? 1 : (index + 2);
          const nextYear = (index + 2) > 12 ? parseInt(year) + 1 : year;
          
          calendario.push({
            mes: mes,
            impuesto: impuesto.nombre,
            periodicidad: 'Primeros 13 días hábiles del siguiente mes',
            fechaLimite: `${nextYear}-${String(nextMonth).padStart(2, '0')}-13`,
            descripcion: `Declaración y pago dentro de los primeros 13 días hábiles del siguiente mes de ${impuesto.nombre}`
          });
        });
        break;

      case 'primeros24dias':
        meses.forEach((mes, index) => {
          const nextMonth = (index + 2) > 12 ? 1 : (index + 2);
          const nextYear = (index + 2) > 12 ? parseInt(year) + 1 : year;
          
          calendario.push({
            mes: mes,
            impuesto: impuesto.nombre,
            periodicidad: 'Primeros 24 días hábiles del siguiente mes',
            fechaLimite: `${nextYear}-${String(nextMonth).padStart(2, '0')}-24`,
            descripcion: `Declaración y pago dentro de los primeros 24 días hábiles del siguiente mes de ${impuesto.nombre}`
          });
        });
        break;

      case 'semestral':
        [6, 12].forEach(month => {
          const nextMonth = month === 12 ? 1 : month + 1;
          const nextYear = month === 12 ? parseInt(year) + 1 : year;
          const lastDay = new Date(nextYear, nextMonth, 0).getDate();
          
          calendario.push({
            mes: meses[month - 1],
            impuesto: impuesto.nombre,
            periodicidad: 'Semestral fin del mes siguiente',
            fechaLimite: `${nextYear}-${String(nextMonth).padStart(2, '0')}-${lastDay}`,
            descripcion: `Declaración y pago semestral de ${impuesto.nombre}`
          });
        });
        break;

      case 'anual':
        calendario.push({
          mes: 'Marzo',
          impuesto: impuesto.nombre,
          periodicidad: 'Anual - 31 de Marzo',
          fechaLimite: `${parseInt(year) + 1}-03-31`,
          descripcion: `Declaración y pago anual de ${impuesto.nombre}`
        });
        break;
    }
  });
  
  return calendario;
}

function actualizarCalendarioTributario() {
  const year = document.getElementById('calendar-year').value;
  const taxType = document.getElementById('calendar-tax-type').value;
  
  let calendario = generarCalendarioTributario(year);
  
  if (taxType !== 'todos') {
    calendario = calendario.filter(item => item.impuesto === taxType);
  }
  
  const tbody = document.querySelector('#calendario-table tbody');
  tbody.innerHTML = calendario.map(item => `
    <tr>
      <td>${item.mes}</td>
      <td>${item.impuesto}</td>
      <td>${item.periodicidad}</td>
      <td>${item.fechaLimite}</td>
      <td>${item.descripcion}</td>
      <td>
        <button onclick="asignarFechaPago('${item.mes}', '${item.impuesto}')" class="btn-primary">
          <i class="fas fa-calendar-plus"></i> Asignar Fecha de Pago
        </button>
      </td>
    </tr>
  `).join('');
}

function asignarFechaPago(mes, impuesto) {
  const modalContent = `
    <div class="form-group">
      <label>Fecha de Pago para ${impuesto} - ${mes}</label>
      <input type="date" id="fecha-pago-impuesto" required>
    </div>
    <button onclick="guardarFechaPago('${mes}', '${impuesto}')" class="btn-primary">Guardar Fecha de Pago</button>
  `;
  showModal(modalContent, 'Asignar Fecha de Pago');
}

function guardarFechaPago(mes, impuesto) {
  const fechaPago = document.getElementById('fecha-pago-impuesto').value;
  if (fechaPago) {
    alert(`Fecha de pago guardada para ${impuesto} - ${mes}: ${fechaPago}`);
    const modalOverlay = document.querySelector('.modal-overlay');
    if (modalOverlay) {
      modalOverlay.remove();
    }
  }
}

function actualizarSelectTiposImpuestos() {
  const select = document.getElementById('calendar-tax-type');
  select.innerHTML = '<option value="todos">Todos los impuestos</option>';
  tiposImpuestos.forEach(impuesto => {
    select.innerHTML += `<option value="${impuesto.nombre}">${impuesto.nombre}</option>`;
  });
}

function mostrarCalendarioMensual() {
  const currentDate = new Date();
  const currentMonth = currentDate.getMonth();
  const currentYear = currentDate.getFullYear();
  const meses = [
    'Enero', 'Febrero', 'Marzo', 'Abril', 'Mayo', 'Junio',
    'Julio', 'Agosto', 'Septiembre', 'Octubre', 'Noviembre', 'Diciembre'
  ];

  // Get previous month
  const previousMonth = currentMonth === 0 ? 11 : currentMonth - 1;
  const previousMonthYear = currentMonth === 0 ? currentYear - 1 : currentYear;

  // Get first day of month and number of days
  const firstDay = new Date(currentYear, currentMonth, 1).getDay();
  const daysInMonth = new Date(currentYear, currentMonth + 1, 0).getDate();
  
  let calendario = generarCalendarioTributario(currentYear);
  calendario = calendario.filter(item => item.mes === meses[currentMonth]);
  
  // Create map of dates with events
  const eventDates = {};
  calendario.forEach(item => {
    const day = new Date(item.fechaLimite).getDate();
    if (!eventDates[day]) {
      eventDates[day] = [];
    }
    eventDates[day].push(item);
  });

  let calendarHTML = `
    <h3>${meses[currentMonth]} ${currentYear}</h3>
    <div class="calendar-grid">
      <div class="calendar-header">Domingo</div>
      <div class="calendar-header">Lunes</div>
      <div class="calendar-header">Martes</div>
      <div class="calendar-header">Miércoles</div>
      <div class="calendar-header">Jueves</div>
      <div class="calendar-header">Viernes</div>
      <div class="calendar-header">Sábado</div>
  `;

  // Add empty cells for days before start of month
  for (let i = 0; i < firstDay; i++) {
    calendarHTML += '<div class="calendar-day empty"></div>';
  }

  // Add days with events
  for (let day = 1; day <= daysInMonth; day++) {
    const events = eventDates[day] || [];
    const hasEvents = events.length > 0;
    
    calendarHTML += `
      <div class="calendar-day ${hasEvents ? 'has-events' : ''}">
        <span class="day-number">${day}</span>
        ${hasEvents ? `
          <div class="event-dots">
            ${events.map(event => `
              <div class="event-dot" title="${event.impuesto}: ${event.descripcion}"></div>
            `).join('')}
          </div>
        ` : ''}
      </div>
    `;
  }

  calendarHTML += '</div>';
  
  // Add event list below calendar with previous month reference
  if (Object.keys(eventDates).length > 0) {
    calendarHTML += `
      <div class="events-list">
        <h4>Eventos del mes:</h4>
        ${Object.entries(eventDates).map(([day, events]) => `
          <div class="event-day">
            <strong>${day} de ${meses[currentMonth]} - Fecha límite de pago:</strong>
            ${events.map(event => `
              <div class="event-item">
                <span class="event-name">${event.impuesto}</span>
                <span class="event-desc">
                  <strong>Descripción:</strong> Corresponde a la declaración de ${meses[previousMonth]} de ${previousMonthYear}
                </span>
              </div>
            `).join('')}
          </div>
        `).join('')}
      </div>
    `;
  }

  showModal(calendarHTML, 'Calendario Tributario Mensual');
}

function mostrarCalendarioAnual() {
  const year = document.getElementById('calendar-year').value;
  const calendario = generarCalendarioTributario(year);
  
  const meses = [
    'Enero', 'Febrero', 'Marzo', 'Abril', 'Mayo', 'Junio',
    'Julio', 'Agosto', 'Septiembre', 'Octubre', 'Noviembre', 'Diciembre'
  ];

  let calendarHTML = '<div class="calendario-anual">';
  
  meses.forEach(mes => {
    const eventosDelMes = calendario.filter(item => item.mes === mes);
    
    if (eventosDelMes.length > 0) {
      calendarHTML += `
        <div class="calendario-anual-mes">
          <h3>${mes} ${year}</h3>
          ${eventosDelMes.map(evento => `
            <div class="evento-anual">
              <div class="evento-anual-fecha">${evento.fechaLimite}</div>
              <div class="evento-anual-impuesto">${evento.impuesto}</div>
              <div class="evento-anual-desc">${evento.descripcion}</div>
            </div>
          `).join('')}
        </div>
      `;
    }
  });
  
  calendarHTML += '</div>';
  
  showModal(calendarHTML, `Calendario Tributario Anual ${year}`);
}

function showCalendarioTributario() {
  const table = document.querySelector('#calendario-table').cloneNode(true);
  showModal(table.outerHTML, 'Calendario Tributario');
}

function showModal(content, title) {
  const modalOverlay = document.createElement('div');
  modalOverlay.className = 'modal-overlay';
  
  const modal = document.createElement('div');
  modal.className = 'modal';
  
  modal.innerHTML = `
    <h2>${title}</h2>
    <button class="modal-close" onclick="closeModal(this)">Cerrar</button>
    ${content}
  `;
  
  modalOverlay.appendChild(modal);
  document.body.appendChild(modalOverlay);
  modalOverlay.style.display = 'block';
}

function closeModal(button) {
  const modalOverlay = button.closest('.modal-overlay');
  modalOverlay.remove();
}

function showListadoContribuyentes() {
  const table = document.querySelector('#contribuyentes-table').cloneNode(true);
  showModal(table.outerHTML, 'Listado de Contribuyentes');
}

function showListadoImpuestos() {
  const table = document.querySelector('#impuestos-table').cloneNode(true);
  showModal(table.outerHTML, 'Listado de Tipos de Impuestos');
}

function showListadoVencidos() {
  const table = document.querySelector('#vencidos-table').cloneNode(true);
  showModal(table.outerHTML, 'Listado de Impuestos Vencidos');
}

function showListadoAlDia() {
  const table = document.querySelector('#aldia-table').cloneNode(true);
  showModal(table.outerHTML, 'Listado de Impuestos al Día');
}

function cancelarFormContribuyente() {
  document.getElementById('contribuyente-form').reset();
  document.querySelectorAll('#impuestos-asignados input[type="checkbox"]')
    .forEach(checkbox => checkbox.checked = false);
}

function importarExcel() {
  const modalContent = `
    <div class="form-group">
      <label>Seleccione archivo Excel (.xlsx, .xls)</label>
      <input type="file" id="excel-file" accept=".xlsx, .xls" class="form-control">
    </div>
    <div class="form-group">
      <button onclick="procesarArchivoExcel()" class="btn-primary">
        <i class="fas fa-upload"></i> Importar Datos
      </button>
    </div>
  `;
  showModal(modalContent, 'Importar Contribuyentes desde Excel');
}

function procesarArchivoExcel() {
  const fileInput = document.getElementById('excel-file');
  const file = fileInput.files[0];
  
  if (!file) {
    alert('Por favor seleccione un archivo Excel');
    return;
  }

  const reader = new FileReader();
  reader.onload = function(e) {
    const data = new Uint8Array(e.target.result);
    const workbook = XLSX.read(data, {type: 'array'});
    
    // Assume first sheet contains data
    const firstSheetName = workbook.SheetNames[0];
    const worksheet = workbook.Sheets[firstSheetName];
    
    // Convert to JSON
    const jsonData = XLSX.utils.sheet_to_json(worksheet);
    
    // Process each row
    jsonData.forEach(row => {
      const contribuyente = {
        dni: row.NIT || row.dni || '',
        nombre: row.Nombre || row['Razón Social'] || row.nombre || '',
        fechaNacimiento: row['Fecha de Nacimiento'] || row.fechaNacimiento || '',
        contrasenaAV: row['Contraseña AV'] || row.contrasenaAV || '',
        contrasenaCertificar: row['Contraseña Para Certificar'] || row.contrasenaCertificar || '',
        regimenTributario: row['Régimen Tributario'] || row.regimenTributario || '',
        estado: row.Estado || row.estado || 'activo',
        impuestosAsignados: (row['Impuestos Asignados'] || '').split(',').map(i => i.trim()).filter(i => i),
        impuestosPagados: {}
      };
      
      // Add only if DNI is not empty and not duplicate
      if (contribuyente.dni && !contribuyentes.find(c => c.dni === contribuyente.dni)) {
        contribuyentes.push(contribuyente);
      }
    });
    
    actualizarTablaContribuyentes();
    alert('Importación completada exitosamente');
    closeModal(document.querySelector('.modal-close'));
  };
  
  reader.readAsArrayBuffer(file);
}

generarDatosEjemplo();
</script>
</body></html>
