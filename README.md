<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<style>
  /* Remove page margins so it fits perfectly in the Google Site embed */
  body { 
    font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif; 
    margin: 0; 
    padding: 10px; 
    background-color: transparent; /* Allows Google Site background to show through */
  }
  
  .container {
    width: 100%; /* Occupies full width */
    max-width: 100%; 
    margin: 0;
  }

  /* Search Bar Styling */
  .search-container { 
    margin-bottom: 20px; 
    position: relative; 
    width: 100%; 
  }
  
  #formSearch {
    width: 100%;
    padding: 14px 20px;
    font-size: 16px;
    border: 2px solid #2e7d32; 
    border-radius: 30px;
    outline: none;
    box-sizing: border-box; /* Ensures padding doesn't break width */
  }

  /* Full-Width Table Container */
  .table-wrapper { 
    background: white; 
    border-radius: 12px; 
    overflow: hidden; 
    box-shadow: 0 4px 15px rgba(0,0,0,0.1); 
    border: 1px solid #e0e0e0;
    width: 100%;
  }

  table { width: 100%; border-collapse: collapse; }
  
  thead { background-color: #2e7d32; color: white; }
  
  th { padding: 18px 20px; text-transform: uppercase; font-size: 13px; letter-spacing: 1px; }
  
  td { padding: 15px 20px; border-bottom: 1px solid #f0f0f0; }
  
  .form-title { font-weight: bold; color: #2e7d32; display: block; margin-bottom: 2px; }
  .form-subtitle { color: #666; font-size: 12px; }
  
  .category-tag { 
    font-size: 11px; 
    text-transform: uppercase; 
    background: #e8f5e9; 
    color: #2e7d32; 
    padding: 5px 10px; 
    border-radius: 20px; 
    font-weight: bold;
  }

  /* Download Button */
  .download-link {
    background-color: #2097c3; 
    color: white;
    padding: 10px 20px;
    text-decoration: none;
    border-radius: 6px;
    font-size: 13px;
    font-weight: bold;
    display: inline-block;
  }
</style>
</head>
<body>

<div class="container">
  <div class="search-container">
    <input type="text" id="formSearch" onkeyup="searchTable()" placeholder="Type to search forms...">
  </div>

  <div class="table-wrapper">
    <table id="formsTable">
      <thead>
        <tr>
          <th style="text-align: left;">Form Details</th>
          <th style="text-align: left;">Category</th>
          <th style="text-align: center;">Action</th>
        </tr>
      </thead>
      <tbody>
        <tr>
          <td>
            <span class="form-title">Personal Data Sheet (PDS)</span>
            <span class="form-subtitle">CS Form 212 (Revised 2017)</span>
          </td>
          <td><span class="category-tag">HR</span></td>
          <td style="text-align: center;"><a href="#" class="download-link">Download</a></td>
        </tr>
        <tr>
          <td>
            <span class="form-title">Application for Leave</span>
            <span class="form-subtitle">Form 6</span>
          </td>
          <td><span class="category-tag">PERSONNEL</span></td>
          <td style="text-align: center;"><a href="#" class="download-link">Download</a></td>
        </tr>
        <tr>
          <td>
            <span class="form-title">SF10 - Learner's Permanent Record</span>
            <span class="form-subtitle">Formerly Form 137</span>
          </td>
          <td><span class="category-tag">REGISTRAR</span></td>
          <td style="text-align: center;"><a href="#" class="download-link">Download</a></td>
        </tr>
      </tbody>
    </table>
  </div>
</div>

<script>
function searchTable() {
  let input = document.getElementById("formSearch");
  let filter = input.value.toUpperCase();
  let table = document.getElementById("formsTable");
  let tr = table.getElementsByTagName("tr");

  for (let i = 1; i < tr.length; i++) {
    let rowContent = tr[i].textContent || tr[i].innerText;
    tr[i].style.display = rowContent.toUpperCase().indexOf(filter) > -1 ? "" : "none";
  }
}
</script>

</body>
</html>
