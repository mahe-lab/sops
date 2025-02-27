### protocol
- Protocol: Protein Qubit Quantification
- Faculty: Cumming School of Medicine
- Institute: Charbonneau Cancer Institute
- Site: Arthur J.E. Child Comprehensive Cancer Center, YC
- Version: 2
- Version Date: 1MAY2024
- Approver: ermahe@ucalgary.ca

### authorization
- Requires Completion of Safety Training
- Requires Pre-Authorization by PI

### hazards
- Qubit Protein Assay Reagent: https://assets.thermofisher.com/TFS-Assets/LSG/SDS/Q33212COMPONENTA_MTR-NALT_EN.pdf
- Qubit Protein Buffer: https://assets.thermofisher.com/TFS-Assets/LSG/SDS/Q33212COMPONENTB_MTR-NALT_EN.pdf
- Qubit Protein Standard 1: https://assets.thermofisher.com/TFS-Assets/LSG/SDS/Q33212COMPONENTC_MTR-NALT_EN.pdf
- Qubit Protein Standard 2: https://assets.thermofisher.com/TFS-Assets/LSG/SDS/Q33212COMPONENTD_MTR-NALT_EN.pdf
- Qubit Protein Standard 3: https://assets.thermofisher.com/TFS-Assets/LSG/SDS/Q33212COMPONENTE_MTR-NALT_EN.pdf

### ppe
- Lab Coat
- Eye Protection
- Nitrile Gloves

### where
- Pre-PCR Bench

### references
- Qubit 4.0 Manual: https://assets.thermofisher.com/TFS-Assets/LSG/manuals/MAN0017209_Qubit_4_Fluorometer_UG.pdf
- Qubit Protein Assay Full Manufacturer Protocol: https://assets.thermofisher.com/TFS-Assets/LSG/manuals/Qubit_Protein_Assay_UG.pdf

### emergency
- See SDS

### cleanup
- Wipe down work surfaces with 70% isopropanol
- NOTE: Do not use isopropanol on instruments

### waste
- Tips/Tubes should be disposed of in yellow biohazard bag/tub

### maintenance
- If required, clean the surface of the Qubit instrument with a damp cloth. DO NOT USE DETERGENT

### before_starting
- Identify the specimens requiring Qubit assay quantification and obtain sufficient Qubit tubes 
- NOTE: ONLY Qubit tubes can be used with the Qubit instrument
- NOTE: ONLY label Qubit tubes on the top cap
- NOTE: new standards need to be read whenever a new batch of working solution is made
- NOTE: ensure that the correct Qubit reagent and Qubit buffer are used (i.e. Qubit Protein)

### calculator
~~~~
<!DOCTYPE html>
<html lang="en">
	<head>
		<meta name="viewport" content="width=device-width, initial-scale=1.0">
		<link rel="stylesheet" href="mahe-lab_style.css">
		<title>MAHELAB SOP Calculator</title>
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
<button type="button" class="button" onclick="addRows()">Add Rows</button>
<br>
<!--- insert the necessary calculations here.--->
<table id="table2">
	<tr><td></td><td></td></tr>
	<tr><td>Reagent/Input Calculations:</td><td></td></tr>
	<tr><td>Volume of required Working Solution (mL):</td>
<!--- calculation: --->
	<td><input readonly type="text" size="10px" id="calc1"/></td></tr>
	<tr><td>Volume of required Qubit Reagent (uL) to make Working Solution:</td>
<!--- calculation: --->
	<td><input readonly type="text" size="10px" id="calc2"/></td></tr>
	<tr><td>Volume of required Qubit Buffer (uL) to make Working Solution:</td>
<!--- calculation: --->
	<td><input readonly type="text" size="10px" id="calc3"/></td></tr>
</table>
<br>
<button type="button" class="button" onclick="calculate()">Calculate</button>
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
        document.getElementById('calc1').value = (0.22 * ( 3 + count )).toFixed(1);
        document.getElementById('calc2').value = (1.1 * ( 3 + count )).toFixed(1);
        document.getElementById('calc3').value = (218.9 * ( 3 + count )).toFixed(1);
    }
}
</script>
</body>
</html>
~~~~
### procedures
1. Add 10 uL of standard 1 to 190 uL working solution
2. Add 10 uL of standard 2 to 190 uL working solution
3. Add 10 uL of Standard 3 to 190 uL working solution
4. Add 5 uL of each query specimen to 195 uL working solution
5. Vortex each tube x 5 seconds; incubate the tubes at room temperature x 2 minutes
6. Tap to wake the Qubit; select the appropriate specimen and assay type
7. Read the standards
8. Read each query specimen one at a time, ensuring that specimen volume is set accordingly (ie at 5 uL); record the concentrations (in ng/uL)
9. Update the specimen database with the concentrations
10. Any leftover working solution should be stored in the 4C fridge
