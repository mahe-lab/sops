
### protocol
- Protocol: Iron Extraction & Quantification (Bone Marrow or Tissue)
- Faculty: Cumming School of Medicine
- Institute: Charbonneau Cancer Institute
- Site: Arthur J.E. Child Comprehensive Cancer Center, YC
- Version: 3
- Version Date: JUNE2024
- Approver: ermahe@ucalgary.ca

### authorization
- Requires Completion of Safety Training
- Requires Pre-Authorization by PI

### hazards
- Xylene is toxic, volatile, flammable, and poisonous
- HCl is a strong acid and will cause skin burns and damage clothing

### ppe
- Lab Coat
- Eye Protection
- Nitrile Gloves

### where
- Fumehood
- Pre-PCR bench if using MAHELAB plate reader

### references
-  https://github.com/mahe-lab/sops/MAHELAB_SOP_Assets/Sigma_IronKit_MAK472.pdf

### emergency
- Use spill kit to clean up small spills; Contact maintenance and log incident for large spills
- If skin/eye contact with chemicals, flush aggressively and continuously with water using an eyewash, sink or shower
- Contact emergency services and log any injuries as required

### cleanup
- Wipe down work surfaces with 70% isopropanol
- NOTE: Do not use isopropanol on instruments

### waste
- Tips/Tubes should be disposed of in yellow biohazard bag/tub
- Xylene should be disposed of in chemical waste container (fumehood)
- Sharps disposal: approved biohazard bucket

### maintenance
- Refer to plate reader literature for required maintenance steps

### before_starting
- Complete the tissue transfer SOP (https://mahe-lab.github.io/sops/sop_template.html?tissue_transfer_extraction.md)
- Ensure that the mount quick curls from a given case (might be multiple slides) are placed in a volumetric tube
- Ensure that there is sufficient 1M HCl & 1M NaOH on hand (use the calculator below)
- New stock 1M HCl can be made in a 100 mL graduated cylinder: add 8.3 mL 12M (37%) HCl; add ddH2O up to 100 mL and store in a 100 mL bottle; 100 mL 1M NaOH can be made using 4 g NaOH and carefully adding ddH2O up to 100 mL
- Remove the kit reagents (Reagent A, Reagent B and Reagent C as well as Iron standard) from the fridge and allow to warm to RT
- Prepare sufficient Working Solution (WS) using the calculator below; mix well by pipetting up and down

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
	<tr><td>Total volume required of each of 1M HCl and 1M NaOH: </td>
<!--- calculation: --->
	<td><input readonly type="text" size="10px" id="calc1"/></td></tr>
	<tr><td>Required volume of Reagent A (uL):</td>
<!--- calculation: --->
	<td><input readonly type="text" size="10px" id="calc2"/></td></tr>
	<tr><td>Required volume of Reagent B (uL):</td>
<!--- calculation: --->
	<td><input readonly type="text" size="10px" id="calc3"/></td></tr>
<tr><td>Required volume of Reagent C (uL):</td>
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
        document.getElementById('calc1').value = (2.5 * count ).toFixed(1);
        document.getElementById('calc2').value = (200 * ( 16 + count )).toFixed(1);
        document.getElementById('calc3').value = (10 * ( 16 + count )).toFixed(1);
        document.getElementById('calc4').value = (10 * ( 16 + count )).toFixed(1);
    }
}
</script>
</body>
</html>
~~~~

### procedures
1. In the fumehood, dissolve the mount quick curls in the glass volumetric tubes with 500 uL xylene
2. Vortex gently and incubate 5 min at RT in the fumehood
3. When the gel has fully dissolved, spin gently in the Dade centrifuge (low setting x 2 minutes; NOT Eppendorf centrifuge)
4. Carefully pipette off the supernatant (discard in the organic waste in fumehood) without disturbing the tissue pellet
5. Allow the pellet to dry fully in the fumehood (can be left overnight, without the stopper on, to allow for xylene to evaporate completely)
6. Add 500 uL 1M HCl and pipette carefully but aggressively (20 passes) to re-suspend the pellet
7. Replace the stoppers and place the tube in the thermomixer set at 50°C with gentle rotation overnight
8. Carefully add additional 1M NaOH up to the exact 1 mL volume indicated on the volumetric tube; allow tubes to stand (with stoppers in place) at RT x 30 minutes
9. If not proceeding directly to quantification, the supernatant from step 8 can be stored in a labelled Eppendorf tube in the -20C freezer
10.	Prepare a 1000 µg/dL (10 µg/mL) Iron Standard by mixing 40 µL of the 10 mg/dL kit Iron standard with 360 µL ddH2O in an Eppendorf tube (label the tube “#1”)
11.	Prepare subsequent dilutions (mix well by pipetting up and down):
#2: 80 uL from #1 with 20 uL ddH2O (this is 800 µg/dL of iron)
#3: 60 uL from #1 with 40 uL ddH2O (this is 600 µg/dL of iron)
#4: 40 uL from #1 with 60 uL ddH2O (this is 400 µg/dL of iron)
#5: 30 uL from #1 with 70 uL ddH2O (this is 300 µg/dL of iron)
#6: 20 uL from #1 with 80 uL ddH2O (this is 200 µg/dL of iron)
#7: 10 uL from #1 with 90 uL ddH2O (this is 100 µg/dL of iron)
#8: 100 uL ddH2O (this is 0 µg/dL of iron)
12.	Pipette 200 uL of WS into the wells of a 96-well optical plate (sufficient for each specimen and standard to be assessed in duplicate)
13.	Transfer 50 uL of each of the above standards and query specimens into the appropriate wells, with duplicates performed
14.	Tap the plate gently to mix and allow the plate to stand at RT for 40 minutes
15.	Read optical density (OD) at 590 nm using a platereader
16.	Generate a standard curve in excel by plotting ∆OD of the reference specimens ( ∆OD = ODi – OD8 ) with their respective concentrations (as above)
17.	From this standard curve, use the query specimen ∆OD to calculate specimen iron concentration (report the average of the duplicates as well as the standard deviation for each specimen)
18.	NOTE: if a query specimen ∆OD exceeds the standard curve (ie is higher than the highest measurement on the standard curve) a dilution of the specimen will need to be re-run to confirm accuracy of the concentration (the dilution factor can be approximated by dividing the ∆OD of reference #1 by the specimen measured ∆OD; dilute with 1M HCl)
