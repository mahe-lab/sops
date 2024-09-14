
### protocol
- Protocol: RBC Lysis & Cell Pelleting, Blood & Bone Marrow
- Faculty: Cumming School of Medicine
- Institute: Charbonneau Cancer Institute
- Site: Arthur J.E. Child Comprehensive Cancer Center, 
- Version: 2
- Version Date: 14FEB2024
- Approver: ermahe@ucalgary.ca

### authorization
- Requires Completion of Safety Training
- Requires Pre-Authorization by PI

### hazards
- All blood and bone marrow specimens should be considered infectious; universal precautions are required

### ppe
- Lab Coat
- Eye Protection
- Nitrile Gloves

### where
- Biosafety Cabinet
- Pre-PCR bench

### references
- [UAMS Red Cell Lysis Protocol](MAHELAB_SOP_Assets/UAMSRedCellLysisProtocol.pdf)

### emergency
- Spills are assumed to be infectious
- Clean spills of blood/fluids using universal cleaning solution and/or 70% isopropanol surface disinfectant
- Cuts/wounds/skin contact with infectious materials should be thoroughly cleaned, wounds cared for and immediately reported to WHS
- Seek emergency medical attention as reasonably required

### cleanup
- Use 70% isopropanol for surface cleaning (including biosafety cabinet)
- Use bleach to clean waste container or any other blood-contaminated equipment

### waste
- Dispose of specimen tubes/containers/pipettes or any other contaminated materials in biohazard bags/containers
- When work is complete, allow waste container (containing bleach) to stand in biosafety cabinet for 30 minutes before disposing in the sink with ample tap water 
- Dispose of any unused 1x RBC Lysis Working Solution after 3 months of non-use

### maintenance
- Centrifuge maintenance/cleaning may be required – see separate manual/SOP
- Dispose of any unused 1x RBC Lysis Working Solution after 3 months of non-use

### before_starting
- Disposable Plastic pipettes (one per specimen)
- 50 mL falcon tubes (labelled; one per specimen)
- Ice container/bucket
- Waste container (e.g. 1L bucket with ~100 mL of bleach)
- If required, make sufficient 10x Stock RBC Lysis Solution: Weight out NH4Cl (ammonium chloride) 8.02 g, NaHCO3 (sodium bicarbonate) 0.84 g; EDTA (disodium) 0.37 g and dissolve in RNAse-free (or DEPC-sterile) water up to 100 mL
- 10x Stock RBC Lysis Solution is diluted to 1x RBC Lysis Working Solution (RLWS) with RNAse-free (or DEPC-sterile) on demand. Use the calculator below to determine the required volume

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
    <tr><td>Scan/enter Accession Number</td><td>Estimated Total Volume (mL)</td></tr>
</table>
<table id="table1">
    <tr> <td><input type="text" size="10px" id="00"/></td> <td><input type="text" size="10px" id="01"/></td> </tr>
    <tr> <td><input type="text" size="10px" id="10"/></td> <td><input type="text" size="10px" id="11"/></td> </tr>
</table>
<br>
<button type="button" class="button" onclick="addRows()">Add Rows</button>
<br>
<!--- insert the necessary calculations here.--->
<table id="table2">
    <tr><td></td><td></td></tr>
    <tr><td>Reagent/Input Calculations:</td><td></td></tr>
    <tr><td>Volume of (1x) RLWS required (mL): </td>
<!--- calculation: --->
    <td><input readonly type="text" size="10px" id="calc1"/></td></tr>
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
    for (var i=0;i<trows;i++) {
        var vol = parseFloat(document.getElementById(`${i}1`).value);
        if( isNaN(vol) ) {}
        else {
            count += 5*vol;
        }
    }
    if (count>0) {
        document.getElementById('calc1').value = count;
    }
}
</script>
</body>
</html>
~~~~

### procedures
1. In the biosafety cabinet, pipette the specimens into their respective labelled 50 mL falcon tubes and place on ice; keep the specimen tubes in the rack to store the pipettes in while working
2. Add 5x RLWS lysis buffer (eg if 5 mL specimen, pour in RLWS up to 30 mL total volume)
3. Vortex for 5-10 seconds
4. Allow to stand on ice for 5 minutes
5. Vortex for 5-10 seconds
6. Allow to stand on ice for 5 minutes
7. Vortex for 5-10 seconds
8. Centrifuge using a swing-bucket rotor for 15 minutes at 1500 rpm (1000g) at 4C
9. Return to the biosafety cabinet and carefully pipette off the supernatant into the waste flask down to the original volume while keeping tubes on ice. DO NOT DISTURB THE CELL PELLET AT THE BOTTOM OF THE TUBE WHEN PIPETTING
10. Add 5x of original volume RLWS (eg if 5 mL original specimen volume, pour in RLWS up to 30 mL total volume)
11. Vortex for 5-10 seconds
12. Allow to stand on ice for 5 minutes
13. Vortex for 5-10 seconds
14. Allow to stand on ice for 5 minutes
15. Vortex for 5-10 seconds
16. Centrifuge using a swing-bucket rotor for 15 minutes at 1500 rpm (1000g) at 4C
17. Return to the biosafety cabinet and pipette off the supernatant down to ~1-2 mL
18. Resuspend the pellet region and transfer to a labelled Eppendorf tube
19. Centrifuge at ~10000 rpm for 1 minute to pellet the cells again
20. Pipette off as much supernatant as possible WITHOUT DISTURBING THE CELL PELLET
21. IF extracting RNA, for example via RNeasy QIAGEN protocol: Add 20 uL beta-mercaptoethanol (to inhibit RNAses) and add sufficient volume of lysis buffer (eg buffer RLT) up to ~600 uL
22. IF extracting DNA, for example via DNeasy QIAGEN protocol, OR freezing: Resuspend the pellet in 100 uL PBS
