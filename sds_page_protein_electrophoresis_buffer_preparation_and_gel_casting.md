
### protocol
- Protocol: SDS Page Protein Electrophoresis Preparation and Gel Casting
- Faculty: Cumming School of Medicine
- Institute: Charbonneau Cancer Institute
- Site: Arthur J.E. Child Comprehensive Cancer Center, YC
- Version: 1
- Version Date: 9SEPT2024
- Approver: ermahe@ucalgary.ca

### authorization
- Requires Completion of Safety Training
- Requires Pre-Authorization by PI

### hazards
- Acrylamide is a potent neurotoxin and is absorbed through the skin. Powdered and stock liquid acrylamide solutions should be handled in the fumehood
- 2-mercaptoethanol is toxic and very pungent in smell. handle in the fumehood
- TEMED (N,N,N',N'-tetramethylethylenediamine) is flammable/ volitile and toxic, handle in the fumehood
- APS is highly reactive/flammable and is an oxidizer; handle gently, and dispense only a small amount
- Care must be taken during electrophoresis to avoid electric shock

### ppe
- Lab Coat
- Eye Protection
- Nitrile Gloves

### where
- Fumehood
- Pre-PCR Bench (casting and electrophoreis only)

### references
- ADD

### emergency
- See SDS
- If skin/eye contact with chemicals, flush aggressively and continuously with water using an eyewash, sink or shower
- Use spill kit to clean up small spills; Contact maintenance and log incident for large spills
- Contact emergency services and log any injuries

### cleanup
- Wipe down work surfaces with 70% isopropanol
- NOTE: Do not use isopropanol on instruments

### waste
- Tips/Tubes should be disposed of in yellow biohazard bag/tub

### maintenance
- rinse equipment with distilled water after use
- DO NOT USE UNIVERSAL CLEANER ON GEL APARATUS (This will cause caustic damage)
- Can wipe down glass plates with isopropanol to remove debris and ensure re-use without leaks

### before_starting
- Prepare 0.5M Tris (pH 6.8): in a beaker, dissolve 6g Tris base in 60mL ddH2O (heat/stir) and adjust pH 6.8 with 12 M HCL (slowly, as an overshoot is not salvageable); pout into 100mL graduated cylinder and top off to 100mL with ddH2O, sore in a labled 100mL bottle at 4°C
- Prepare 1.5M Tris (pH 8.8):  in a beaker, dissolve 18.15g Tris base in 60mL ddH2O (heat/stir) and adjust pH 8.8 with 12 M HCL (slowly, as an overshoot is not salvageable); pout into 100mL graduated cylinder and top off to 100mL with ddH2O, sore in a labled 100mL bottle at 4°C
- Prepare 10% w/v SDS:

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
<button type="button" onclick="addRows()">Add Rows</button>
<br>
<!--- insert the necessary calculations here.--->
<table id="table2">
	<tr><td></td><td></td></tr>
	<tr><td>Reagent/Input Calculations:</td><td></td></tr>
	<tr><td>Total volume of required Working Solution (mL):</td>
<!--- calculation: --->
	<td><input readonly type="text" size="10px" id="calc1"/></td></tr>
	<tr><td>Volume of *** reagent (uL) to make Working Solution:</td>
<!--- calculation: --->
	<td><input readonly type="text" size="10px" id="calc2"/></td></tr>
	<tr><td>Volume of *** reagent (uL) to make Working Solution:</td>
<!--- calculation: --->
	<td><input readonly type="text" size="10px" id="calc3"/></td></tr>
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
        // uncomment and adjust here with correct calculations for the correct text boxes above:
        //
        // document.getElementById('calc1').value = (0.22 * ( 2 + count )).toFixed(1);
        
        // document.getElementById('calc2').value = (1.1 * ( 2 + count )).toFixed(1);

        // document.getElementById('calc3').value = (218.9 * ( 2 + count )).toFixed(1);
    }
}
</script>
</body>
</html>
~~~~
### procedures
1. add
