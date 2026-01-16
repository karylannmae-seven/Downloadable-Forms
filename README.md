<!DOCTYPE html>
<html>
<head>
<style>
  body { font-family: 'Segoe UI', Arial, sans-serif; margin: 0; padding: 20px; background: transparent; }
  
  /* Search Bar Styling */
  .search-container { margin-bottom: 20px; position: relative; max-width: 400px; }
  #formSearch {
    width: 100%;
    padding: 12px 40px 12px 15px;
    font-size: 16px;
    border: 2px solid #2e7d32; /* Theme Green */
    border-radius: 25px;
    outline: none;
    box-sizing: border-box;
  }
  .search-icon { position: absolute; right: 15px; top: 12px; color: #2e7d32; }

  /* Table Styling */
  .table-wrapper { 
    background: white; 
    border-radius: 8px; 
    overflow: hidden; 
    box-shadow: 0 4px 10px rgba(0,0,0,0.1); 
    border: 1px solid #ddd;
  }
  table { width: 100%; border-collapse: collapse; text-align: left; }
  
  thead { background-color: #2e7d32; color: white; }
  th, td { padding: 15px; border-bottom: 1px solid #eee; }
  
  tr:hover { background-color: #f9f9f9; }
  
  .form-title { font-weight: bold; color: #333; }
  .category-tag { 
    font-size: 11px; 
    text-transform: uppercase; 
    background: #e8f5e9; 
    color: #2e7d32; 
    padding: 4px 8px; 
    border-radius: 4px; 
    font-weight: bold;
  }

  /* Download Button Style */
  .download-link {
    background-color: #2097c3; /* Theme Blue */
    color: white;
    padding: 8px 15px;
    text-decoration: none;
    border-radius: 4px;
    font-size: 13px;
    font-weight: bold;
    display: inline-block;
    transition: 0.3s;
  }
  .download-link:hover { background-color: #166d8e; }

  @media screen and (max-width: 600px) {
    .hide-mobile { display: none; }
  }
</style>
</head>
<body>

<div class="search-container">
  <input type="text" id="formSearch" onkeyup="searchTable()" placeholder="Search for a form name or category...">
  <span class="search-icon">🔍</span>
</div>

<div class="table-wrapper">
  <table id="formsTable">
    <thead>
      <tr>
        <th>Form Name</th>
        <th class="hide-mobile">Category</th>
        <th>Action</th>
      </tr>
    </thead>
    <tbody>
      <tr>
        <td><span class="form-title">Personal Data Sheet (PDS)</span><br><small>CS Form 212 (Revised 2017)</small></td>
        <td class="hide-mobile"><span class="category-tag">HR</span></td>
        <td><a href="#" class="download-link">Download</a></td>
      </tr>
      <tr>
        <td><span class="form-title">Application for Leave</span><br><small>Form 6</small></td>
        <td class="hide-mobile"><span class="category-tag">Personnel</span></td>
        <td><a href="#" class="download-link">Download</a></td>
      </tr>
      <tr>
        <td><span class="form-title">SF10 - Learner's Permanent Record</span><br><small>Formerly Form 137</small></td>
        <td class="hide-mobile"><span class="category-tag">Registrar</span></td>
        <td><a href="#" class="download-link">Download</a></td>
      </tr>
      <tr>
        <td><span class="form-title">SALN Form</span><br><small>Statement of Assets, Liabilities, and Networth</small></td>
        <td class="hide-mobile"><span class="category-tag">HR</span></td>
        <td><a href="#" class="download-link">Download</a></td>
      </tr>
    </tbody>
  </table>
</div>

<script>
function searchTable() {
  var input, filter, table, tr, td, i, txtValue;
  input = document.getElementById("formSearch");
  filter = input.value.toUpperCase();
  table = document.getElementById("formsTable");
  tr = table.getElementsByTagName("tr");

  for (i = 1; i < tr.length; i++) {
    tr[i].style.display = "none";
    td = tr[i].getElementsByTagName("td");
    for (var j = 0; j < td.length; j++) {
      if (td[j]) {
        txtValue = td[j].textContent || td[j].innerText;
        if (txtValue.toUpperCase().indexOf(filter) > -1) {
          tr[i].style.display = "";
          break;
        }
      }
    }
  }
}
</script>

</body>
</html>
