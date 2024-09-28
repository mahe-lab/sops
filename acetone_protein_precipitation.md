
### protocol
- Protocol: Acetone Protein Precipitation
- Faculty: Cumming School of Medicine
- Institute: Charbonneau Cancer Institute
- Site: Arthur J.E. Child Comprehensive Cancer Center, YC
- Version: 1
- Version Date: 8SEP2024
- Approver: ermahe@ucalgary.ca

### authorization
- Requires Completion of Safety Training
- Requires Pre-Authorization by PI

### hazards
- Acetone is volatile, flammable and toxic; see SDS: https://www.fishersci.com/msds?productName=AC177170100&productDescription=ACETO

### ppe
- Lab Coat
- Eye Protection
- Nitrile Gloves

### where
- Fumehood
- Pre-PCR bench

### references
- Thermo Technical Note on Acetone Protein Precipitation: https://assets.thermofisher.com/TFS-Assets/LSG/Application-Notes/TR0049-Acetone-precipitation.pdf 

### emergency
- IF INHALED: Remove victim to fresh air and keep at rest in a position comfortable for breathing
- IF ON SKIN (or hair): Immediately remove contaminated clothing; rinse skin with water/shower
- IF IN EYES: Rinse cautiously with water for several minutes; remove contact lenses, if present and easy to do; continue rinsing. If eye irritation persists get medical advice/attention
- In case of fire use CO2, dry chemical, or foam for extinction

### cleanup
- Wipe down work surfaces with 70% isopropanol
- NOTE: Do not use isopropanol on instruments

### waste
- Tips/Tubes should be disposed of in biohazard bags

### maintenance
- Wipe down fumehood with 70% isopropanol; close sash when done & turn out light

### before_starting
- This protocol assumes that protein extraction has already been performed, and that removal of extract buffer is required (i.e. to remove SDS, DTT, etc)
- Well-cooled (-20C) acetone is required; overnight cooling may be required
- This protocol assumes re-suspension will be performed in 100 mM Tris; ensure that sufficient 100 mM Tris is available for resuspension using the calculator below
- To make 1M Tris stock: Dissolve 121 g Tris base in 800 ml ddH2O; warm to dissolve as required; adjust to desired pH with concentrated HCl (approximately 42 mL HCl is needed to achieve pH 8.0 solution); top up to 1L total volume with ddH2O

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
	<tr><td>Total volume of required Cool Acetone (mL):</td>
<!--- calculation: --->
	<td><input readonly type="text" size="10px" id="calc1"/></td></tr>
	<tr><td>Volume of 100 mM Tris required for re-suspension (mL):</td>
<!--- calculation: --->
	<td><input readonly type="text" size="10px" id="calc2"/></td></tr>
	<tr><td>Volume of 1 M Tris required to make the above solution (uL):</td>
<!--- calculation: --->
	<td><input readonly type="text" size="10px" id="calc3"/></td></tr>
	<tr><td>Volume of ddH2O required to make the above solution (mL):</td>
<!--- calculation: --->
	<td><input readonly type="text" size="10px" id="calc4"/></td></tr>
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
        // uncomment and adjust here with correct calculations for the correct text boxes above:
        document.getElementById('calc1').value = (0.66 * (count)).toFixed(1);
        document.getElementById('calc2').value = (0.11 * (count)).toFixed(1);
        document.getElementById('calc3').value = (11 * (count)).toFixed(1);
	document.getElementById('calc4').value = (0.099 * (count)).toFixed(1);
    }
}
</script>
</body>
</html>
~~~~
### procedures
1. Add 4 volumes of cooled acetone (i.e. if continuing from previous extraction SOP, add 400 uL of acetone directly to 100 uL of the extract supernatant)
2. Cap and vortex
3. Place in the -20C freezer to incubate for 60 minutes
4. Centrifuge 10 minutes at 13,000-15,000 × g
5. Without dislodging the pellet, discard the supernatant and allow the remaining acetone to evaporate from the uncapped tube in the fumehood (room temperature ~ 30 minutes)
6. Add 2 original volumes of cooled acetone to the pellet
7. Cap and vortex
8. Place in the -20C freezer to incubate for 60 minutes
9. Centrifuge 10 minutes at 13,000-15,000 × g
10. Without dislodging the pellet, discard the supernatant and allow the remaining acetone to evaporate from the uncapped tube in the fumehood (room temperature ~ 30 minutes)
11. Resuspend the pellet in 100 uL of 100 mM Tris
