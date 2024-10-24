
### protocol
- Protocol: RNA Extraction from Cell Pellet Materials (including RBC-Lysed Blood/Marrow)
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
- ...insert details here...

### emergency
- Use spill kit to clean up small spills; Contact maintenance and log incident for large spills
- If skin/eye contact with chemicals, flush aggressively and continuously with water using an eyewash, sink or shower
- Contact emergency services and log any injuries

### cleanup
- Wipe down work surfaces with 70% isopropanol

### waste
- Tips/Tubes should be disposed of in yellow biohazard bag/tub
- ...insert details here...

### maintenance
- Wipe down work surfaces with 70% isopropanol

### before_starting
- This protocol requires 70% Ethanol, DNase booster buffer, DNase I stock solution, buffer RW1, buffer RPE and RNase-free (DEPC) water
- DNase 1 stock solution (from QIAGEN DNase 1 kit): Dissolve lyophilized DNase 1 (1500 Kunitz units) in 550 μl RNase-free water
- DNase 1 stock solution can be kept for 9+ months at -20C
-
- RNeasy columns, collection and specimen (elution) tubes are required
- Enter specimen accession numbers below and use the calculator to calculate the 

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
</table>
<br>
<button type="button" class="button" onclick="addRows()">Add Rows</button>
<br>
<!--- insert the necessary calculations here.--->
<table id="table2">
	<tr><td>DNase Working Solution:</td><td></td></tr>
<!--- calculation: --->
	<tr><td>Volume of DNase booster buffer required (uL):</td>
	<td><input readonly type="text" size="10px" id="calc1"/></td></tr>
<!--- calculation: --->
	<tr><td>Volume of DNase I stock solution required (uL):</td>
	<td><input readonly type="text" size="10px" id="calc2"/></td></tr>
<tr><td></td><td></td></tr>
<tr><td>Volume of 70% Ethanol required (uL):</td>
	<td><input readonly type="text" size="10px" id="calc3"/></td></tr>
<!--- calculation: --->
	<tr><td>Volume of buffer RW1 required (uL):</td>
	<td><input readonly type="text" size="10px" id="calc4"/></td></tr>
  <tr><td>Volume of buffer RPE required (uL):</td>
	<td><input readonly type="text" size="10px" id="calc5"/></td></tr>
   <tr><td>Volume of RNase-free water equired (uL):</td>
	<td><input readonly type="text" size="10px" id="calc6"/></td></tr>

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
	      document.getElementById('calc1').value = (11 * (count)).toFixed(1);
        document.getElementById('calc2').value = (77 * (count)).toFixed(1);
        document.getElementById('calc3').value = (660 * (count)).toFixed(1);
        document.getElementById('calc4').value = (770 * (count)).toFixed(1);
        document.getElementById('calc5').value = (550 * (count)).toFixed(1);
        document.getElementById('calc6').value = (33 * (count)).toFixed(1);
    }
}
</script>
</body>
</html>
~~~~

### procedures
1. Ensure that cell lysis steps are complete (ie buffer RLT and beta-mercaptoethanol have been added to a cell pellet/lysis, with total volume ~600 uL)
2. Add one volume (~600 uL) 70% ethanol; mix by pipetting up and down gently
3. Prepare an appropriately labelled RNeasy Column (these will come packaged with a 2 mL waste collection tube)
4. Transfer ~600 uL of the specimen from step 1 to the column
5. Centrifuge 15 sec at 10,000 rpm
6. Discard flow-through in liquid waste
7. Repeat steps 4-6 until all the materials from step 1 are passed through the column
8. Add 350 μl Buffer RW1 to the RNeasy spin column. Close the lid gently, and centrifuge for 15 s at 10,000 rpm
9. Discard the flow-through.
10.	Add 80 uL of DNase working solution to the column (aim directly for the membrane); let stand on the bench for 15 min.
11.	Add 350 μl Buffer RW1 to the RNeasy spin column. Close the lid gently, and centrifuge for 15 s at 10,000 rpm
12.	Discard flow-through
13.	Add 500 μl Buffer RPE to the RNeasy spin column
14.	Centrifuge for 15 s at 10,000 rpm
15.	Discard flow-through
16.	Repeat steps 12-14
17.	Centrifuge for 2 min at 10,000 rpm to dry the membrane
18.	Carefully transfer the column to a new labelled specimen tube (be sure not to get the column wet with the flow-through)
19.	Carefully add 30 uL RNase-free water to the CENTER of the column. Avoid touching the walls/sides of the column with pipette tip
20.	Centrifuge for 1 min at full speed to elute the RNA
21.	Proceed to RNA quantification & store specimen in -20C freezer
