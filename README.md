<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<style>
  body { font-family: 'Segoe UI', Arial, sans-serif; margin: 0; padding: 20px; background-color: #f4f7f6; }
  .container { max-width: 900px; margin: auto; background: white; padding: 25px; border-radius: 8px; box-shadow: 0 2px 10px rgba(0,0,0,0.1); }
  
  h2 { color: #2e7d32; border-bottom: 2px solid #2e7d32; padding-bottom: 10px; margin-top: 0; }
  
  /* Simple Search Bar */
  #formSearch { 
    width: 100%; 
    padding: 14px; 
    margin-bottom: 25px; 
    border: 2px solid #eee; 
    border-radius: 6px; 
    box-sizing: border-box; 
    font-size: 16px; 
    outline: none;
    transition: border-color 0.3s;
  }
  #formSearch:focus { border-color: #2e7d32; }

  /* Table Styling */
  table { width: 100%; border-collapse: collapse; }
  th { background: #2e7d32; color: white; text-align: left; padding: 15px; font-size: 14px; text-transform: uppercase; }
  td { padding: 15px; border-bottom: 1px solid #eee; vertical-align: middle; }
  tr:nth-child(even) { background-color: #fcfcfc; }
  tr:hover { background-color: #f1f8e9; } /* Subtle highlight on hover */

  .form-info { display: flex; flex-direction: column; }
  .form-name { font-weight: bold; color: #333; font-size: 15px; }
  .form-desc { font-size: 12px; color: #666; margin-top: 3px; }

  /* Action Button */
  .download-btn {
    background-color: #2097c3;
    color: white;
    padding: 10px 18px;
    text-decoration: none;
    border-radius: 4px;
    font-weight: bold;
    display: inline-block;
    font-size: 13px;
    text-align: center;
    min-width: 100px;
    transition: background 0.3s;
  }
  .download-btn:hover { background-color: #1a7fa5; }
</style>
</head>
<body>

<div class="container">
  <h2>Downloadable Forms</h2>
  
  <input type="text" id="formSearch" onkeyup="searchTable()" placeholder="🔍 Type to search (e.g., PDS, Work, Guide)...">

  <table id="formsTable">
    <thead>
      <tr>
        <th>Form Details</th>
        <th style="width: 120px; text-align: center;">Action</th>
      </tr>
    </thead>
    <tbody>
      <tr>
        <td>
          <div class="form-info">
            <span class="form-name">Personal Data Sheet (PDS)</span>
            <span class="form-desc">CS Form No. 212 Revised 2025 (Excel)</span>
          </div>
        </td>
        <td style="text-align: center;">
          <a href="https://depedph-my.sharepoint.com/:x:/g/personal/karylannmae_convicto_deped_gov_ph/IQAFBgeTNvk3Qrr2xwD3fZXQATlKVw2iXKHMmXcQd0nXlvw?download=1" class="download-btn">Download</a>
        </td>
      </tr>

      <tr>
        <td>
          <div class="form-info">
            <span class="form-name">Work Experience Sheet</span>
            <span class="form-desc">CS Form No. 212 Attachment (Word)</span>
          </div>
        </td>
        <td style="text-align: center;">
          <a href="https://depedph-my.sharepoint.com/:w:/g/personal/karylannmae_convicto_deped_gov_ph/IQAxvi4s1uPoQZyrX_461hBpARjWQYVKxEOF1GWImkY8Llw?download=1" class="download-btn">Download</a>
        </td>
      </tr>

      <tr>
        <td>
          <div class="form-info">
            <span class="form-name">Guide to Filling Up the PDS</span>
            <span class="form-desc">Instructional Attachment (PDF)</span>
          </div>
        </td>
        <td style="text-align: center;">
          <a href="https://depedph-my.sharepoint.com/:b:/g/personal/karylannmae_convicto_deped_gov_ph/IQA3NwjbHTdAS5c9ctwKZnqpAUCE6NvtPdSh5BIizfjsuiQ?download=1" class="download-btn">Download</a>
        </td>
      </tr>
    </tbody>
  </table>
</div>

<script>
function searchTable() {
  var input = document.getElementById("formSearch").value.toUpperCase();
  var tr = document.getElementById("formsTable").getElementsByTagName("tr");
  
  for (var i = 1; i < tr.length; i++) {
    var txtValue = tr[i].textContent || tr[i].innerText;
    if (txtValue.toUpperCase().indexOf(input) > -1) {
      tr[i].style.display = "";
    } else {
      tr[i].style.display = "none";
    }
  }
}
</script>

</body>
</html>
