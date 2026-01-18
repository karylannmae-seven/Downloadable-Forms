<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<style>
  /* Base styles to remove margins for a clean embed */
  body { 
    font-family: 'Segoe UI', Arial, sans-serif; 
    margin: 0; 
    padding: 10px; 
    background-color: transparent; 
  }
  
  .container { width: 100%; margin: 0 auto; }

  /* Top Search Bar */
  .search-container { 
    margin-bottom: 20px; 
    position: relative; 
    max-width: 400px; 
  }
  
  #formSearch {
    width: 100%;
    padding: 10px 40px 10px 20px;
    font-size: 15px;
    border: 2px solid #2e7d32; /* School Green */
    border-radius: 25px;
    outline: none;
    box-sizing: border-box;
    color: #666;
  }

  .search-icon { 
    position: absolute; 
    right: 15px; 
    top: 10px; 
    color: #2097c3; /* Blue search icon */
    font-size: 16px;
  }

  /* Main Table Wrapper */
  .table-wrapper { 
    background: white; 
    border-radius: 8px; 
    overflow: hidden; 
    box-shadow: 0 4px 12px rgba(0,0,0,0.1); 
    border: 1px solid #eee;
  }

  table { width: 100%; border-collapse: collapse; }
  
  /* Solid Green Header */
  thead { background-color: #2e7d32; color: white; }
  
  th { 
    padding: 15px 20px; 
    text-align: left; 
    font-size: 14px; 
    font-weight: bold; 
  }
  
  td { padding: 15px 20px; border-bottom: 1px solid #f2f2f2; vertical-align: middle; }
  
  /* Form Text Styling */
  .form-title { font-weight: bold; color: #333; font-size: 15px; display: block; }
  .form-subtitle { color: #666; font-size: 12px; margin-top: 2px; display: block; }
  
  /* Category Tags */
  .category-tag { 
    font-size: 11px; 
    text-transform: uppercase; 
    background: #e8f5e9; 
    color: #2e7d32; 
    padding: 4px 10px; 
    border-radius: 4px; 
    font-weight: bold;
    display: inline-block;
  }

  /* Blue Action Buttons */
  .download-btn {
    background-color: #2097c3; 
    color: white;
    padding: 8px 25px;
    text-decoration: none;
    border-radius: 4px;
    font-size: 13px;
    font-weight: bold;
    display: inline-block;
    transition: background 0.3s;
  }
  
  .download-btn:hover { background-color: #1a7fa5; }

  @media screen and (max-width: 600px) {
    .hide-mobile { display: none; }
  }
</style>
</head>
<body>

<div class="container">
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
          <th style="text-align: center;">Action</th>
        </tr>
      </thead>
      <tbody>
        <tr>
          <td>
            <span class="form-title">Personal Data Sheet (PDS)</span>
            <span class="form-subtitle">CS Form 212 (Revised 2017)</span>
          </td>
          <td class="hide-mobile"><span class="category-tag">HR</span></td>
          <td style="text-align: center;"><a href="#" class="download-btn">Download</a></td>
        </tr>
        <tr>
          <td>
            <span class="form-title">Application for Leave</span>
            <span class="form-subtitle">Form 6</span>
          </td>
          <td class="hide-mobile"><span class="category-tag">PERSONNEL</span></td>
          <td style="text-align: center;"><a href="#" class="download-btn">Download</a></td>
        </tr>
        <tr>
          <td>
            <span class="form-title">SF10 - Learner's Permanent Record</span>
            <span class="form-subtitle">Formerly Form 137</span>
          </td>
          <td class="hide-mobile"><span class="category-tag">REGISTRAR</span></td>
          <td style="text-align: center;"><a href="#" class="download-btn">Download</a></td>
        </tr>
        <tr>
          <td>
            <span class="form-title">SALN Form</span>
            <span class="form-subtitle">Statement of Assets, Liabilities, and Networth</span>
          </td>
          <td class="hide-mobile"><span class="category-tag">HR</span></td>
          <td style="text-align: center;"><a href="#" class="download-btn">Download</a></td>
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
