<!DOCTYPE html>
<html lang="es">
<head>
<meta charset="UTF-8" />
<meta name="viewport" content="width=device-width, initial-scale=1.0" />
<title>Panel del Administrador de Empresas</title>
<style>
  * { box-sizing: border-box; margin: 0; padding: 0; font-family: "Segoe UI", sans-serif; }
  body { display: flex; min-height: 100vh; background: #f4f6f8; }

  /* Sidebar */
  .sidebar {
    width: 230px; background: #1a237e; color: #fff; display: flex; flex-direction: column;
    justify-content: space-between; padding: 20px;
  }
  .sidebar h2 { text-align: center; margin-bottom: 30px; }
  .sidebar ul { list-style: none; }
  .sidebar li {
    margin: 15px 0; cursor: pointer; padding: 10px; border-radius: 8px;
    transition: 0.3s; text-align: left;
  }
  .sidebar li:hover { background: #3949ab; }
  .sidebar footer { text-align: center; font-size: 13px; opacity: 0.7; }

  /* Main */
  main {
    flex: 1; padding: 25px; background: #f4f6f8;
  }

  header {
    display: flex; justify-content: space-between; align-items: center; margin-bottom: 25px;
  }
  header h1 { color: #1a237e; }
  header button {
    padding: 8px 15px; border: none; background: #1a237e; color: white;
    border-radius: 6px; cursor: pointer;
  }

  /* Cards */
  .cards {
    display: grid; grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
    gap: 15px; margin-bottom: 30px;
  }
  .card {
    background: white; padding: 15px; border-radius: 10px;
    box-shadow: 0 2px 5px rgba(0,0,0,0.1);
  }
  .card h3 { color: #1a237e; margin-bottom: 5px; }
  .card p { font-size: 22px; font-weight: bold; }

  /* Tables */
  table {
    width: 100%; border-collapse: collapse; background: white; border-radius: 10px;
    box-shadow: 0 2px 5px rgba(0,0,0,0.1);
  }
  th, td {
    padding: 10px; text-align: left; border-bottom: 1px solid #ddd;
  }
  th { background: #e8eaf6; color: #1a237e; }
  tr:hover { background: #f1f1f1; }
</style>
</head>
<body>

  <!-- Sidebar -->
  <div class="sidebar">
    <div>
      <h2>AdminEmp</h2>
      <ul>
        <li onclick="showSection('dashboard')">🏠 Inicio</li>
        <li onclick="showSection('clientes')">👥 Clientes</li>
        <li onclick="showSection('empleados')">💼 Empleados</li>
        <li onclick="showSection('finanzas')">💰 Finanzas</li>
      </ul>
    </div>
    <footer>© 2025 AdminEmp</footer>
  </div>

  <!-- Main content -->
  <main>
    <header>
      <h1>Panel Administrativo</h1>
      <button>Salir</button>
    </header>

    <!-- Dashboard -->
    <section id="dashboard">
      <div class="cards">
        <div class="card"><h3>Clientes</h3><p>56</p></div>
        <div class="card"><h3>Empleados</h3><p>12</p></div>
        <div class="card"><h3>Ingresos</h3><p>Gs. 12.450.000</p></div>
        <div class="card"><h3>Gastos</h3><p>Gs. 4.320.000</p></div>
      </div>
    </section>

    <!-- Clientes -->
    <section id="clientes" style="display:none;">
      <h2>Listado de Clientes</h2><br>
      <table>
        <thead><tr><th>Nombre</th><th>Empresa</th><th>Teléfono</th><th>Email</th></tr></thead>
        <tbody>
          <tr><td>Ana López</td><td>Distribuidora PY</td><td>0981 555-123</td><td>ana@py.com</td></tr>
          <tr><td>Juan Gómez</td><td>Servicios GO</td><td>0982 222-789</td><td>juan@go.com</td></tr>
        </tbody>
      </table>
    </section>

    <!-- Empleados -->
    <section id="empleados" style="display:none;">
      <h2>Empleados</h2><br>
      <table>
        <thead><tr><th>Nombre</th><th>Cargo</th><th>Salario</th></tr></thead>
        <tbody>
          <tr><td>María Torres</td><td>Contadora</td><td>Gs. 3.500.000</td></tr>
          <tr><td>Carlos Rojas</td><td>Vendedor</td><td>Gs. 2.800.000</td></tr>
        </tbody>
      </table>
    </section>

    <!-- Finanzas -->
    <section id="finanzas" style="display:none;">
      <h2>Resumen Financiero</h2><br>
      <table>
        <thead><tr><th>Fecha</th><th>Concepto</th><th>Tipo</th><th>Monto</th></tr></thead>
        <tbody>
          <tr><td>01/10/2025</td><td>Venta de productos</td><td>Ingreso</td><td>Gs. 5.000.000</td></tr>
          <tr><td>03/10/2025</td><td>Pago de servicios</td><td>Gasto</td><td>Gs. 1.200.000</td></tr>
        </tbody>
      </table>
    </section>

  </main>

<script>
function showSection(section) {
  document.querySelectorAll("main section").forEach(s => s.style.display = "none");
  document.getElementById(section).style.display = "block";
}
</script>

</body>
</html>

