<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>DCES Downloadable Forms</title>
<style>
  /* Global Modern Styles */
  body { 
    font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif; 
    margin: 0; 
    padding: 20px; 
    background-color: #f4f7f6; 
    color: #333;
  }
  
  .container {
    max-width: 1000px;
    margin: auto;
  }

  /* Search Bar Styling */
  .search-container { 
    margin-bottom: 25px; 
    position: relative; 
    max-width: 500px; 
  }
  
  #formSearch {
    width: 100%;
    padding: 14px 45px 14px 20px;
    font-size: 16px;
    border: 2px solid #2e7d32; /* School Green */
    border-radius: 30px;
    outline: none;
    box-shadow: 0 4px 6px rgba(0,0,0,0.05);
    transition: 0.3s;
  }
  
  #formSearch:focus {
    box-shadow: 0 4px 12px rgba(46, 125, 50, 0.2);
    border-color: #1b5e20;
  }

  .search-icon { 
    position: absolute; 
    right: 20px; 
    top: 15px; 
    color: #2e7d32; 
    font-size: 18px;
  }

  /* Table Container */
  .table-wrapper { 
    background: white; 
    border-radius: 12px; 
    overflow: hidden; 
    box-shadow: 0 10px 25px rgba(0,0,0,0.1); 
    border: 1px solid #e0e0e0;
  }

  table { width: 100%; border-collapse: collapse; }
  
  thead { background-color: #2e7d32; color: white; }
  
  th { 
    padding: 18px 20px; 
    text-transform: uppercase; 
    font-size: 13px; 
    letter-spacing: 1px; 
  }
  
  td { padding: 15px 20px; border-bottom: 1px solid #f0f0f0; }
  
  tr:last-child td { border-bottom: none; }
  tr:hover { background-color: #f9fff9; }
  
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
    display: inline-block;
  }

  /* Action Button */
  .download-link {
    background-color: #2097c3; /* School Blue */
    color: white;
    padding: 10px 20px;
    text-decoration: none;
    border-radius: 6px;
    font-size: 13px;
    font-weight: bold;
    display: inline-block;
    transition: transform 0.2s, background 0.3s;
  }
  
  .download-link:hover { 
    background-color: #166d8e; 
    transform: scale(1.05);
  }

  /* Responsive Design */
  @media screen and (max-width: 768px) {
    .hide-mobile { display: none; }
    #formSearch { font-size: 14px; }
    th, td { padding: 12px 15px; }
  }
</style>
</head>
<body>

<div class="container">
  <div class="search-container">
    <input type="text" id="formSearch" onkeyup="searchTable()" placeholder="Type to search forms (e.g. 'Leave', 'SF10')...">
    <span class="search-icon">🔍</span>
  </div>

  <div class="table-wrapper">
    <table id="formsTable">
      <thead>
        <tr>
          <th style="text-align: left;">Form Details</th>
          <th class="hide-mobile" style="text-align: left;">Category</th>
          <th style="text-align: center;">Action</th>
        </tr>
      </thead>
      <tbody id="tableBody">
        <tr>
          <td>
            <span class="form-title">Personal Data Sheet (PDS)</span>
            <span class="form-subtitle">CS Form 212 (Revised 2017)</span>
          </td>
          <td class="hide-mobile"><span class="category-tag">HR</span></td>
          <td style="text-align: center;"><a href="YOUR_LINK_HERE" class="download-link">Download</a></td>
        </tr>
        <tr>
          <td>
            <span class="form-title">Application for Leave</span>
            <span class="form-subtitle">Form 6</span>
          </td>
          <td class="hide-mobile"><span class="category-tag">Personnel</span></td>
          <td style="text-align: center;"><a href="YOUR_LINK_HERE" class="download-link">Download</a></td>
        </tr>
        <tr>
          <td>
            <span class="form-title">SF10 - Learner's Permanent Record</span>
            <span class="form-subtitle">Formerly Form 137</span>
          </td>
          <td class="hide-mobile"><span class="category-tag">Registrar</span></td>
          <td style="text-align: center;"><a href="YOUR_LINK_HERE" class="download-link">Download</a></td>
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
