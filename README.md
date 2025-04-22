<!DOCTYPE html>
<html lang="fr">
<head>
  <meta charset="UTF-8">
  <title>Gestion des Patients - Hôpital</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      background: #f8f9fa;
      padding: 40px;
    }

    h1 {
      color: #2c3e50;
    }

    table {
      width: 100%;
      border-collapse: collapse;
      background: white;
      margin-bottom: 30px;
    }

    th, td {
      padding: 12px;
      border: 1px solid #ddd;
      text-align: left;
    }

    th {
      background-color: #007BFF;
      color: white;
    }

    form {
      background-color: white;
      padding: 20px;
      border: 1px solid #ccc;
      width: 100%;
      max-width: 500px;
    }

    input[type="text"],
    input[type="date"] {
      width: 100%;
      padding: 10px;
      margin-bottom: 15px;
      border: 1px solid #ccc;
    }

    input[type="submit"] {
      padding: 10px 20px;
      background-color: #28a745;
      color: white;
      border: none;
      cursor: pointer;
    }

    input[type="submit"]:hover {
      background-color: #218838;
    }
  </style>
</head>
<body>

  <h1>Gestion des Patients</h1>

  <table id="patientsTable">
    <thead>
      <tr>
        <th>Nom</th>
        <th>Prénom</th>
        <th>Date de Naissance</th>
      </tr>
    </thead>
    <tbody>
      <!-- Les patients ajoutés s'afficheront ici -->
    </tbody>
  </table>

  <form id="addPatientForm">
    <h2>Ajouter un Patient</h2>
    <input type="text" id="nom" placeholder="Nom" required>
    <input type="text" id="prenom" placeholder="Prénom" required>
    <input type="date" id="dateNaissance" required>
    <input type="submit" value="Ajouter le patient">
  </form>

  <script>
    const form = document.getElementById('addPatientForm');
    const tableBody = document.querySelector('#patientsTable tbody');

    form.addEventListener('submit', function(event) {
      event.preventDefault();

      const nom = document.getElementById('nom').value;
      const prenom = document.getElementById('prenom').value;
      const dateNaissance = document.getElementById('dateNaissance').value;

      const row = document.createElement('tr');
      row.innerHTML = `<td>${nom}</td><td>${prenom}</td><td>${dateNaissance}</td>`;
      tableBody.appendChild(row);

      form.reset();
    });
  </script>

</body>
</html>
