
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
- BioRad MiniProtean II: https://github.com/mahe-lab/sops/blob/main/MAHELAB_SOP_Assets/BioRad_MiniProteanII_Manual.pdf
- BioRad Guide to Protein Electrophoresis: https://github.com/mahe-lab/sops/blob/main/MAHELAB_SOP_Assets/BioRad_ProteinElectrophoresisGuide.pdf

### emergency
- See SDS
- If skin/eye contact with chemicals, flush aggressively and continuously with water using an eyewash, sink or shower
- Use spill kit to clean up small spills; Contact maintenance and log incident for large spills
- Contact emergency services and log any injuries

### cleanup
- Wipe down work surfaces with 70% isopropanol
- Do not use isopropanol on instruments

### waste
- Tips/Tubes should be disposed of in yellow biohazard bag/tub

### maintenance
- Rinse equipment with distilled water after use
- Can wipe down glass plates with isopropanol to remove debris and ensure re-use without leaks

### before_starting
- Several buffers/solutions are required and should be prepared in advance:
- 0.5M Tris (pH 6.8): in a beaker, dissolve 6g Tris base in 60mL ddH2O (heat/stir) and adjust pH 6.8 with 12 M HCL (slowly, as an overshoot is not salvageable); pout into 100mL graduated cylinder and top off to 100mL with ddH2O, sore in a labled 100mL bottle at 4°C
- 1.5M Tris (pH 8.8):  in a beaker, dissolve 18.15g Tris base in 60mL ddH2O (heat/stir) and adjust pH 8.8 with 12 M HCL (slowly, as an overshoot is not salvageable); pout into 100mL graduated cylinder and top off to 100mL with ddH2O, sore in a labled 100mL bottle at 4°C
- 10% w/v SDS: dissolve 10g SDS in 60-90 mL ddH2O (heat/stir slowly); top up to 100mL with ddH2O; store in a labelled 100 mL bottle at RT
- Specimen buffer (reducing): In a 15mL Falcon tube, combine 3.55 mL ddH2O; 1.25 mL 0.5 M Tris (pH 6.8); 2.5 mL glycerol; 2.0 mL 10% (w/v) SDS; 0.2 mL 0.5% (w/v) bromophenol blue. Store at RT
- 10x Running Buffer: 30.3 g Tris base; 144 g glycine; 10 g SDS in 1L. NO pH ADJUSTMENT. Store at 4°C
- 
- Prepare the gel cassette sandwich(es):
- For each gel, obtain one each of a short and tall glass plate
- Identify two 1 mm spacers and line them up correctly (flush) at either side of the gel (use the spacer card to assist with placement of the spaces relative to the glass plates)
- Slide the sandwich carefully into the clamp assembly with the short plate to the exterior
- Prior to securing the knobs, stand the apparatus up in the alignment tray of the casting stand to ensure that the glass plates and spacers are flush at the bottom; tighten the knobs to secure
- Move the clamp assembly to the casting slot and gently push into place; two gels can be cast on one casting stand at a time
- Check for leaks by dripping a few mLs of 100% ethanol into the sandwich; ensure that this is well dried up with a kimwipe once complete (residual ethanol will impede the gel)
- Select a comb appropriate to the number of wells for loading (10-12 wells usually). Place the comb in the upper opening of the sandwich and mark 1 cm below the teeth of the comb. This is the height to which the lower resolving gel will be added

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
<!---configure reagent prep details here--->
<table id="table1">
<tr><td>Number of gels to be cast:</td><td><input type="number" id="01" min="1" step="1" value="2"></td></tr>
</table>
<br>
<button type="button" class="button" onclick="calculate()">Calculate</button>
<br>
<table id="table2">
	<tr><td></td><td></td></tr>
	<tr><td>Calculations for running buffer:</td><td></td></tr>
	<tr><td>10x Running buffer stock (mL):</td>
	<td><input readonly type="text" size="10px" id="calc20"/></td></tr>
	<tr><td>ddH2O for 1x running buffer (mL):</td><td><input readonly type="text" size="10px" id="calc21"/></td></tr>
	<tr><td></td><td></td></tr>
	<tr><td>Calculations for 10% Resolvibng Gel(s):</td><td></td></tr>
	<tr><td>30% bis/tris acrylamide stock (mL):</td><td><input readonly type="text" size="10px" id="calc22"/></td></tr>
	<tr><td>1.5M Tris (pH 8.8) stock (mL):</td><td><input readonly type="text" size="10px" id="calc23"/></td></tr>
	<tr><td>Volume ddH2O (mL):</td><td><input readonly type="text" size="10px" id="calc24"/></td></tr>
	<tr><td>10% SDS (uL):</td><td><input readonly type="text" size="10px" id="calc25"/></td></tr>
	<tr><td></td><td></td></tr>
	<tr><td>Calculations for 4% Resolvibng Gel(s):</td><td></td></tr>
	<tr><td>30% bis/tris acrylamide stock (mL):</td><td><input readonly type="text" size="10px" id="calc26"/></td></tr>
	<tr><td>0.5M Tris (pH 8.8) stock (mL):</td><td><input readonly type="text" size="10px" id="calc27"/></td></tr>
	<tr><td>Volume ddH2O (mL):</td><td><input readonly type="text" size="10px" id="calc28"/></td></tr>
	<tr><td>10% SDS (uL):</td><td><input readonly type="text" size="10px" id="calc29"/></td></tr>
</table>
<br>
<script type='text/javascript'>
function calculate() {
    var count = parseInt(document.getElementById('01').value);
    if(count>0) {
        document.getElementById('calc20').value = (2 * Math.round(count / 2)) * 25;
        document.getElementById('calc21').value = (2 * Math.round(count / 2)) * 225;
        document.getElementById('calc22').value = count * 1.75;
        document.getElementById('calc23').value = count * 1.25;
	document.getElementById('calc24').value = count * 1.75;
        document.getElementById('calc25').value = count * 50;
	document.getElementById('calc26').value = count * 0.65;
        document.getElementById('calc27').value = count * 1.25;
	document.getElementById('calc28').value = count * 3.05;
        document.getElementById('calc29').value = count * 50;
    }
}
</script>
</body>
</html>
~~~~

### procedures
1. Prepare the running buffer (use above calculator)
2. Prepare the gel cassette sandwich as directed above
3. Prepare fresh APS when ready to pour gels: 50 mg in 500 uL ddH2O
4. Prepare the 10% resolving gel solution (use above calculator); mix gently and DEGAS for 15 minutes
5. When ready to cast the gel(s), in the fumehood add 50 uL APS and 5 uL TEMED
6. Quickly return to the gel casting stand and pipette in the activated gel up to the marker line
7. Quickly but gently overlay the gel with ddH2O and allow to stand for one hour; once the gel has polymerized, use filter paper to carefully remove the overlain ddH2O
8. Prepare the 4% stacking gel solution (use above calculator); mix gently and DEGAS for 15 minutes
9. When ready to cast the gel(s), in the fumehood add 50 uL APS and 5 uL TEMED
10. Quickly return to the gel casting stand and pipette in the activated gel; place the gel combs; allow to polymerize for one hour
11. Store flat and wrapped in plastic wrap at 4°C (keep comb in place) until ready for use
12. Remove the specimens/extracts from the freezer and allow to warm to RT
