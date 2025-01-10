
### protocol
- Protocol: QIACUBE RNA Extraction from Cell Pellet Materials (including RBC-Lysed Blood/Marrow)
- Faculty: Cumming School of Medicine
- Institute: Charbonneau Cancer Institute
- Site: Arthur J.E. Child Comprehensive Cancer Center, YC083402
- Version: 1
- Version Date: 20MAY2024
- Approver: ermahe@ucalgary.ca

### authorization
- Requires Completion of Safety Training
- Requires Pre-Authorization by PI

### hazards
- Ethanol, and buffers RLT, RW1 and RPE are toxic, volatile, flammable, and/or poisonous.

### ppe
- Lab Coat
- Eye Protection
- Nitrile Gloves

### where
- Fumehood
- Pre-PCR bench

### references
- QIACUBE Manual: 
- QIACUBE RNeasy Protocol Sheet: 

### emergency
- Use spill kit to clean up small spills; Contact maintenance and log incident for large spills
- If skin/eye contact with chemicals, flush aggressively and continuously with water using an eyewash, sink or shower
- Contact emergency services and log any injuries

### cleanup
- Wipe down work surfaces with 70% isopropanol

### waste
- Tips/Tubes should be disposed of in yellow biohazard bag
- Reagent/flow through disposal in aqueous chemical waste container

### maintenance
- Wipe down work surfaces with 70% isopropanol

### before_starting
- This protocol requires that the QIACUBE be loaded with the correct reagent solutions, tips, and spin cartridges (with RNEasy columns, QIAShredder columns and collection tubes)
- A maximum of 12 specimens can be processed per run
- Ensure that sufficient tube labels are available (each collection tube should be labelled)
-  
- DNase on column DNA digestion is performed, and requires the following:
- DNase 1 stock solution (from QIAGEN DNase 1 kit): Dissolve lyophilized DNase 1 (1500 Kunitz units) in 550 μl RNase-free water (stock DNaseI can be stored at -20C for several months)
-  
- Enter specimen accession numbers below and use the calculator to calculate the required reagent volumes

### calculator
~~~~
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
  <tr><td><input type="text" size="10px" id="20"/></td><td><input type="text" size="10px" id="21"/></td><td><input type="text" size="10px" id="22"/></td><td><input type="text" size="10px" id="23"/></td></tr>
</table>
<br>
<!--- insert the necessary calculations here.--->
<table id="table2">
	<tr><td>DNase Working Solution:</td><td></td></tr>
	<tr><td>Volume of DNase booster buffer required (uL):</td>
	<td><input readonly type="text" size="10px" id="calc1"/></td></tr>
	<tr><td>Volume of DNase I stock solution required (uL):</td>
	<td><input readonly type="text" size="10px" id="calc2"/></td></tr>
</table>
<br>
<button type="button" class="button" onclick="calculate()">Calculate</button>
<script type='text/javascript'>
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
	      document.getElementById('calc1').value = (11 * (count)).toFixed(1);
        document.getElementById('calc2').value = (77 * (count)).toFixed(1);
        
    }
}
</script>
</body>
</html>
~~~~

### procedures
1. Ensure that cell lysis steps are complete (ie buffer RLT and beta-mercaptoethanol have been added to a cell pellet/lysis, with total volume ~600 uL)
2. 
21. Proceed to RNA quantification & store specimen in -20C freezer
