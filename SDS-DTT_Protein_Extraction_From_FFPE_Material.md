### protocol_header
- Protocol: SDS-DTT Protein Extraction From FFPE Material
- Faculty: Cumming School of Medicine
- Institute: Charbonneau Cancer Institute
- Site: Arthur J.E. Child Comprehensive Cancer Center, YC
- Date: 5SEPT2024
- Version: 2
- Approver:

### authorization
- 

### hazards
-

### ppe
- Lab Coat
- Eye Protection
- Nitrile Gloves

### where
- 

### references
- 

### emergency
- 

### cleanup
- 

### waste
- 

### maintenance
- 

### before_starting
- 

### calculator
<!DOCTYPE html>
<html lang="en">
	<head>
		<meta name="viewport" content="width=device-width, initial-scale=1.0">
		<link rel="stylesheet" href="mahe-lab_style.css">
		<title>Working Solution Calculator</title>
	</head>
<body>
<!---configure reagent prep details here, with calculations based on the table inputs below--->
<table id="table0">
	<tr><td>Scan/enter the specimen accession numbers:</td><td></tr>
</table>
<table id="table1">
	<tr><td><input type="text" size="10px" id="00"/></td><td><input type="text" size="10px" id="01"/></td><td><input type="text" size="10px" id="02"/></td><td><input type="text" size="10px" id="03"/></td></tr>
	<tr><td><input type="text" size="10px" id="10"/></td><td><input type="text" size="10px" id="11"/></td><td><input type="text" size="10px" id="12"/></td><td><input type="text" size="10px" id="13"/></td></tr>
</table>
<br>
<button type="button" onclick="addRows()">Add Rows</button>
<br>
<!--- insert the necessary calculations here.--->
<table id="table2">
	<tr><td></td><td></td></tr>
	<tr><td>Working Solution Preparation</td><td></td></tr>
	<tr><td>Volume of required Working Solution Assuming ~10 mg of tissue per sample (uL):</td>
	<td><input readonly type="text" size="10px" id="TotalVol"/></td></tr>
<!--- calculation: --->
	<td>Volume of 10x SDS-Tris Stock Required for Working Solution (uL):</td></tr>
	<tr><td><input readonly type="text" size="10px" id="calc1"/></td>
<!--- calculation: --->
	<td>Volume of 1M DTT Required for Working Solution (uL):</td></tr>
	<tr><td><input readonly type="text" size="10px" id="calc2"/></td>
<!--- calculation: --->
	<td>Volume of ddH2O Required for Working Solution (uL):</td></tr>
	<tr><td><input readonly type="text" size="10px" id="calc3"/></td>
</table>
<br>
<button type="button" onclick="calculate()">Calculate</button>
<script type='text/javascript'>
function addRows() {
    var table = document.getElementById('table1');
    var trows = table.rows.length;
    var tcols = table.rows[0].cells.length;
    var row = table.insertRow(trows);
    for (var i=0;i<tcols;i++) {
	var txt = document.createElement('input')
	txt.setAttribute('type','text');
	txt.setAttribute('size','10px');
	txt.setAttribute('id',`${trows}${i}`);
	var col = row.insertCell(i);
	col.appendChild(txt);
    }
}	
function calculate() {
    var count = 0;
    var table = document.getElementById('table1');
    var trows = table.rows.length;
    var tcols = table.rows[0].cells.length;
    for (var i=0;i<trows;i++) {
        for (var j=0;j<tcols;j++) {
            var txtcontent = document.getElementById(`${i}${j}`).value;
            if(txtcontent != '') {
                count++;
            }
        }
    }
    //console.log(count)
    if(count>0) {
	document.getElementById('TotalVol').value = (110 * (count)).toFixed(1);
        document.getElementById('calc1').value = (11 * (count)).toFixed(1);
        document.getElementById('calc2').value = (11 * (count)).toFixed(1);
        document.getElementById('calc3').value = (88 * (count)).toFixed(1);
    }
}
</script>
</body>
</html>
### procedures
1. 
