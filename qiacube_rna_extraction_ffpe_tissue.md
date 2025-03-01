
### protocol
- Protocol: QIACUBE RNA Extraction from FFPE Materials
- Faculty: Cumming School of Medicine
- Institute: Charbonneau Cancer Institute
- Site: Arthur J.E. Child Comprehensive Cancer Center, YC083402
- Version: 1
- Version Date: 25FEB2025
- Approver: ermahe@ucalgary.ca

### authorization
- Requires Completion of Safety Training
- Requires Pre-Authorization by PI

### hazards
- Xylene, Ethanol, and Qiagen buffers are toxic, volatile, flammable, and/or poisonous
- Scrape-blades/glass slides may cause sharps injury
- Thermomixer may cause thermal injury

### ppe
- Lab Coat
- Eye Protection
- Nitrile Gloves

### where
- Fumehood
- Pre-PCR bench
- QIACUBE room

### references
- Qiagen RNA Extraction from FFPE Manual: https://github.com/mahe-lab/sops/blob/main/MAHELAB_SOP_Assets/RNeasy%20RNA%20FFPE.pdf
- QIACUBE RNA Extraction from FFPE Protocol Sheet: 
- QIACUBE Manual:

### emergency
- Use spill kit to clean up small spills; Contact maintenance and log incident for large spills
- If skin/eye contact with chemicals, flush aggressively and continuously with water using an eyewash, sink or shower
- Contact emergency services and log any injuries

### cleanup
- Wipe down work surfaces with 70% isopropanol

### waste
- Tips/Tubes should be disposed of in yellow biohazard bag
- Xylene/ethanol should be disposed of in chemical waste container (fumehood)
- Sharps disposal: use approved biohazard bucket

### maintenance
- Wipe surfaces down with 70% isopropanol
- Do not use isopropanol on instruments

### before_starting
- A maximum of 12 and a minimum of 2 specimens can be processed per run
- 
- Rotor adapters, RNeasy columns and Qiagen elution tubes are required
- 
- Obtain fresh scrape blades (one per specimen)
- 
- Ensure that sufficient Xylene, 100% Ethanol, Proteinase K, Buffers PKD, RBC, RPE and RNAse-free (DEPC) water are available; fill the appropriate QIACUBE bottles to just below the volume mark line with each of 100% Ethanol, RBC, RW1 and RNase-free water
- 
- Enter specimen accession numbers below and use the calculator to calculate the required reagent volumes

### calculator
~~~~
<!DOCTYPE html>
<html lang="en">
	<head>
		<meta name="viewport" content="width=device-width, initial-scale=1.0">
		<link rel="stylesheet" href="mahe-lab_style.css">
		<title>Reagent Calculator</title>
	</head>
<body>
<!---configure reagent prep details here, with calculations based on the table inputs below--->
<table id="table1">
	<tr><td><input type="text" size="10px" id="00"/></td><td><input type="text" size="10px" id="01"/></td><td><input type="text" size="10px" id="02"/></td><td><input type="text" size="10px" id="03"/></td></tr>
	<tr><td><input type="text" size="10px" id="10"/></td><td><input type="text" size="10px" id="11"/></td><td><input type="text" size="10px" id="12"/></td><td><input type="text" size="10px" id="13"/></td></tr>
  <tr><td><input type="text" size="10px" id="20"/></td><td><input type="text" size="10px" id="21"/></td><td><input type="text" size="10px" id="22"/></td><td><input type="text" size="10px" id="23"/></td></tr>
</table>
<br>
<!--- insert the necessary calculations here.--->
<table id="table2">
	<tr><td>Volume of Xylene required (uL) for de-paraffinization:</td>
	<td><input readonly type="text" size="10px" id="calc1"/></td></tr>
	<tr><td>Volume of 100% Ethanol required (uL) for de-paraffinization:</td>
	<td><input readonly type="text" size="10px" id="calc2"/></td></tr>
	<tr><td>Volume of Buffer PKD required (uL):</td>
	<td><input readonly type="text" size="10px" id="calc3"/></td></tr>
	<tr><td>Volume of Proteinase K required (uL):</td>
	<td><input readonly type="text" size="10px" id="calc4"/></td></tr>
  <tr><td>Volume of DNase Stock Solution required (uL):</td>
	<td><input readonly type="text" size="10px" id="calc5"/></td></tr>
<tr><td>Volume of DNase Booster Buffer required (uL):</td>
	<td><input readonly type="text" size="10px" id="calc6"/></td></tr>
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
    if(count>1) {
	      document.getElementById('calc1').value = (1100 * (count)).toFixed(1);
        document.getElementById('calc2').value = (1100 * (count)).toFixed(1);
	      document.getElementById('calc3').value = (264 * (count)).toFixed(1);
        document.getElementById('calc4').value = (11 * (count)).toFixed(1);
        document.getElementById('calc5').value = (96 * (3/8) * (1.3 ^ (count - 1))).toFixed(1);
        document.getElementById('calc6').value = (96 * (5/8) * (1.3 ^ (count - 1))).toFixed(1);
    }
}

</script>
</body>
</html>
~~~~

### procedures
1. Ensure that specimens are accessioned and that a sufficient number of labels are printed (usually 3 per specimen)
2. IF STARTING WITH CURLS/SCROLLS OR TISSUE TRANSFER MATERIAL: Ensure the tube(s) are correctly labelled; move to step 4
3. IF STARTING WITH SLIDES: If coverslipped, soak with xylene in a Coplin jar in fume hood for ~4 hours; use gentle traction (applied using forceps or another slide) to remove the coverslip; Use a fresh scrape blade to scrape off the materials into a labelled 2.0 mL microfuge tube
4. In the fumehood, add 1000 uL xylene per tube
5. Cap, vortex well and incubate 5 min at RT
6. Centrifuge 5 min at 10,000 RPM at RT and carefully pipette off the supernatant
7. Add 1000 uL 100% Ethanol
8. Vortex 10 s and incubate 5 min at RT
9. Centrifuge 5 min at 10,000 RPM at RT and pipette off the supernatant
10. Let the tube stand open in the hood to dry the pellet (this may take 30 minutes or more)
11. Add 250uL of the Buffer PKD/Proteinase K working solution to each tube and reconstitue/mix
Incubate in the thermomixer at 56C for 15 minutes
Remove the tubes and increase the thermomixer temperature to 80C
Incubate the tubes at 80C for 15 minutes
Assemble the QIACUBE rotor adapters (use the Protocol Sheet linked above as a guide)
In the hole at the narrow end of the rotor adapter (facing left), place the RNeasy spin column and anchor the cap securely
The middle hole is left open/un-filled
In the hole at the wide end of the rotor adapeter, place one Qiagen collection tube (labelled); anchor the cap securely in the anchor facing down
Load the specimens (in even numbers) starting at the top of the specimen rack columns
Load the corresponding rotor adapters in the appropriate rotor positions
Load 2 racks of 1000 uL (normal; light gray) QIACUBE tips
Place QIACUBE reagent bottles into the correct slots: 2: RBC; 3: 100% Ethanol; 5: RPE; 6: RNase-free water
Place the DNase I/DNase Booster Buffer tube in slot A
Run the QIACUBE protocol
When complete, proceed to DNA quantification & store specimens in -20C specimen freezer
