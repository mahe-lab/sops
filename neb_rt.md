
### protocol
- Protocol: Reverse Transcription (NEB Protocol)
- Faculty: Cumming School of Medicine
- Institute: Charbonneau Cancer Institute
- Site: Arthur J.E. Child Comprehensive Cancer Center, YC083402
- Version: 2
- Version Date: 11NOV2024
- Approver: ermahe@ucalgary.ca

### authorization
- Requires Completion of Safety Training
- Requires Pre-Authorization by PI

### hazards
- Ensure that the dead-air box is closed shut prior to engaging UV treatment

### ppe
- Lab Coat
- Eye Protection
- Nitrile Gloves

### where
- Dead-air isolation box
- Post-PCR Bench Thermocycler

### references
- See NEB protocol reference:

### emergency
- If skin/eye contact with chemicals, flush aggressively and continuously with water using an eyewash, sink or shower
- Contact emergency services and log any injuries if required

### cleanup
- Wipe down work surfaces with 70% isopropanol
- 5 minute Dead-air UV exposure

### waste
- Tips/Tubes should be disposed of in biohazard bags

### maintenance
- Wipe down work surfaces with 70% isopropanol
- 5 minute Dead-air UV exposure

### before_starting
- Obtain some ice and place in the dead-air box ice box; the aluminum tube tray can be chilled in the dead-air box ice box
- Obtain sufficient tubes/strips to accomodate the specimens; label the tubes/strips appropriately
- Run 5 minute Dead-air UV exposure
- AFTER UV pre-treatment, identify the specimens for RT (scan/enter the specimen accession numbers below), as well as the necessary NEB reagents. Gently warm these on ice until ready to make the RT working solution.

### calculator
~~~~
 <!DOCTYPE html>
<html lang="en">
    <head>
        <meta name="viewport" content="width=device-width, initial-scale=1.0">
        <link rel="stylesheet" href="mahe-lab_style.css">
        <title>MAHELAB SOP Calculator for qPCR</title>
    </head>
<body>
<table id="table1">
    <tr><td>Accession number:</td><td>RNA Concentration (ng/uL):</td><td>Specimen Volume (uL):</td><td>Volume of ddH<sub>2</sub>O Required (uL):</td><td>Input RNA Mass (ng):</td></tr>
    
    <tr><td><input type="text" size="10px" id="110" /></td><td><input type="number" min="0" step="0.01" size="10px" id="111" /></td><td><input type="number" min="0" step="0.01" size="10px" id="112" /> <input type="hidden" id="112_h" value=""> </td><td><input readonly type="number" step="0.01" size="10px" id="113" /> </td><td> <input type="number" min="0" step="0.01" size="10px" id="114" /> <input type="hidden" id="114_h" value=""> </td></tr>
    
    <tr><td><input type="text" size="10px" id="120" /></td><td><input type="number" min="0" step="0.01" size="10px" id="121" /></td><td><input type="number" min="0" step="0.01" size="10px" id="122" /> <input type="hidden" id="122_h" value="">  </td><td><input readonly type="number" step="0.01" size="10px" id="123" /> </td> <td> <input type="number" min="0" step="0.01" size="10px" id="124" /> <input type="hidden" id="124_h" value=""> </td> </tr>
    
    <tr><td><input type="text" size="10px" id="130" /></td><td><input type="number" min="0" step="0.01" size="10px" id="131" /></td><td><input type="number" min="0" step="0.01" size="10px" id="132" /> <input type="hidden" id="132_h" value=""> </td><td><input readonly type="number" step="0.01" size="10px" id="133" /> </td> <td> <input type="number" min="0" step="0.01" size="10px" id="134" /> <input type="hidden" id="134_h" value=""> </td> </tr>
    
    <tr><td><input type="text" size="10px" id="140" /></td><td><input type="number" min="0" step="0.01" size="10px" id="141" /></td><td><input type="number" min="0" step="0.01" size="10px" id="142" /> <input type="hidden" id="142_h" value=""> </td><td><input readonly type="number" step="0.01" size="10px" id="143" /> </td> <td> <input type="number" min="0" step="0.01" size="10px" id="144" /> <input type="hidden" id="144_h" value=""> </td> </tr>
</table>
<br>
<button type="button" class="button" onclick="addRow()">Add Row</button><button type="button" class="button" onclick="deleteRow()">Remove Row</button><button type="button" class="button" onclick="calculate()">Calculate Default Volumes</button><button type="button" class="button" onclick="recalculate()">Recalculate With Altered Values</button>
<br><br>
<!--- insert the necessary calculations here.--->
<table id="table2">
    <tr><td>RTWS Calculations:</td><td></td></tr>
    <tr><td>Volume of NEB 10X Isothermal Amplification Buffer (uL):</td>
<!--- calculation: --->
    <td><input readonly type="text" size="10px" id="calc1"/></td></tr>
    <tr><td>Volume of NEB dNTP Mix (uL):</td>
<!--- calculation: --->
    <td><input readonly type="text" size="10px" id="calc2"/></td></tr>
    <tr><td>Volume of NEB Random Primer Mix (uL):</td>
<!--- calculation: --->
    <td><input readonly type="text" size="10px" id="calc3"/></td></tr>
<tr><td>Volume of NEB Murine RNase Inhibitor (uL):</td>
<!--- calculation: --->
    <td><input readonly type="text" size="10px" id="calc4"/></td></tr>
<tr><td>Volume of NEB WarmStart RTx Reverse Transcriptase (uL):</td>
<!--- calculation: --->
    <td><input readonly type="text" size="10px" id="calc5"/></td></tr>
</table>

<br><br>
<script type='text/javascript'>
//define max volume in uL allowed after addition of working solution here:
const max_rx_vol = 14.25;
//define max default input RNA mass in ng here:
const max_rna_input = 1;
//define min default input RNA mass in ng here:
const min_rna_input = 0.001;
var mass_decimals = (min_rna_input.toString()).split('.')[1].length + 1;
window.onload = init();    
function init() {
    var table1 = document.getElementById('table1');
    var trows = table1.rows.length;
    for(var i=1;i<trows;i++) {
        document.getElementById('1'+`${i}`+'2').placeholder = max_rx_vol;
        document.getElementById('1'+`${i}`+'3').placeholder = max_rx_vol - document.getElementById('1'+`${i}`+'2').placeholder;
        document.getElementById('1'+`${i}`+'4').placeholder = max_rna_input;
        document.getElementById('1'+`${i}`+'4').step = (1/(10^mass_decimals)).toString();
    }
}
function addRow() {
    document.getElementById('calc1').value = "";
    document.getElementById('calc2').value = "";
    document.getElementById('calc3').value = "";
    document.getElementById('calc4').value = "";
    document.getElementById('calc5').value = "";
    var table1 = document.getElementById('table1');
    var trows = table1.rows.length;
    var row = table1.insertRow(trows);
    var txtAcc = document.createElement('input'); txtAcc.setAttribute('type','text'); txtAcc.setAttribute('size','10px'); txtAcc.setAttribute('id',`1${trows}0`); var col = row.insertCell(0); col.appendChild(txtAcc);
    var txtConc = document.createElement('input'); txtConc.setAttribute('type','number'); txtConc.setAttribute('size','10px'); txtConc.setAttribute('min','0'); txtConc.setAttribute('step','0.01'); txtConc.setAttribute('id',`1${trows}1`); var col = row.insertCell(1); col.appendChild(txtConc);
    var txtVol = document.createElement('input'); txtVol.setAttribute('type','number'); txtVol.setAttribute('step','0.01'); txtVol.setAttribute('min','0'); txtVol.setAttribute('size','10px'); txtVol.setAttribute('id',`1${trows}2`); txtVol.setAttribute('placeholder',`${max_rx_vol}`); var col = row.insertCell(2); col.appendChild(txtVol); 
    var txtVol_h = document.createElement('hidden'); txtVol_h.setAttribute('id',`1${trows}2_h`); txtVol_h.setAttribute('value',''); col.appendChild(txtVol_h); 
    var txtH2O = document.createElement('input'); txtH2O.setAttribute('type','number'); txtH2O.setAttribute('readonly',true); txtH2O.setAttribute('size','10px'); txtH2O.setAttribute('step','0.01'); txtH2O.setAttribute('min','0'); txtH2O.setAttribute('id',`1${trows}3`); txtH2O.setAttribute('placeholder',`${max_rx_vol - max_rx_vol}`); var col = row.insertCell(3); col.appendChild(txtH2O);
    var txtWt = document.createElement('input'); txtWt.setAttribute('type','number'); txtWt.setAttribute('size','10px'); txtWt.setAttribute('step',(1/(10^mass_decimals)).toString()); txtWt.setAttribute('min','0'); txtWt.setAttribute('id',`1${trows}4`); txtWt.setAttribute('placeholder',`${max_rna_input}`); var col = row.insertCell(4); col.appendChild(txtWt);
    var txtWt_h = document.createElement('hidden'); txtWt_h.setAttribute('id',`1${trows}4_h`); txtWt_h.setAttribute('value',''); col.appendChild(txtWt_h); 
}
function deleteRow() {
    document.getElementById('calc1').value = "";
    document.getElementById('calc2').value = "";
    document.getElementById('calc3').value = "";
    document.getElementById('calc4').value = "";
    document.getElementById('calc5').value = "";
    var table1 = document.getElementById('table1');
    var trows = table1.rows.length;
    if(trows>2) { table1.deleteRow(-1); }
}
function calculate() {
    var count = 0;
    var table1 = document.getElementById('table1');
    var trows = table1.rows.length;
    var minConc = Number.POSITIVE_INFINITY; //find lowest concentration, and adjust 
    for(var i=1;i<trows;i++) {
        var txtAcc = document.getElementById('1'+`${i}`+'0').value;
        var txtConc = parseFloat(document.getElementById('1'+`${i}`+'1').value);
        if( txtAcc != '' && !isNaN(txtConc) ) {
            count++;
            if( txtConc < minConc ) {
                var minConc = txtConc;
            }
        }
    }
    if( count == (trows-1) && minConc < Number.POSITIVE_INFINITY ) {
        document.getElementById('calc1').value = (2.2 * count ).toFixed(2);
        document.getElementById('calc2').value = (1.1 * count ).toFixed(2);
        document.getElementById('calc3').value = (2.2 * count ).toFixed(2);
        document.getElementById('calc4').value = (0.55 * count ).toFixed(2);
        document.getElementById('calc5').value = (0.275 * count ).toFixed(2);
        // compute input masses relative to the lowest concentration, for the same input mass across the board
        var inputMass = minConc * max_rx_vol;
        if (inputMass > max_rna_input) {
            var inputMass = max_rna_input;
        }
        for(var i=1;i<trows;i++) {
            var volI = (inputMass / parseFloat(document.getElementById('1'+`${i}`+'1').value)).toFixed(2);
            document.getElementById('1'+`${i}`+'2').value = volI; 
            document.getElementById('1'+`${i}`+'3').value = (max_rx_vol - volI).toFixed(2);
            document.getElementById('1'+`${i}`+'4').value = inputMass.toFixed(mass_decimals);
            //make mass font red if too low
            if(inputMass < min_rna_input) {
                document.getElementById('1'+`${i}`+'4').style.color = '#dd0238'; // red = danger
            }
            else {
                document.getElementById('1'+`${i}`+'4').style.color = '#494949';
            }
            document.getElementById('1'+`${i}`+'2_h').value = volI; 
            document.getElementById('1'+`${i}`+'4_h').value = inputMass.toFixed(mass_decimals);
        }
    }
}
function recalculate() {
    var table1 = document.getElementById('table1');
    var trows = table1.rows.length;
    for(var i=1;i<trows;i++) {
        var specAcc = document.getElementById('1'+`${i}`+'0').value;
        var specCon = parseFloat(document.getElementById('1'+`${i}`+'1').value);
        var spec_vol_now = parseFloat(document.getElementById('1'+`${i}`+'2').value);
        var spec_vol_original = parseFloat(document.getElementById('1'+`${i}`+'2_h').value);
        var spec_mass_now = parseFloat(document.getElementById('1'+`${i}`+'4').value);
        var spec_mass_original = parseFloat(document.getElementById('1'+`${i}`+'4_h').value);
        //validate
        if(spec_vol_now > max_rx_vol) {
            spec_vol_now = max_rx_vol;
            document.getElementById('1'+`${i}`+'2').value = spec_vol_now;
        }
        if(spec_mass_now / specCon > max_rx_vol) {
            spec_mass_now = specCon * max_rx_vol;
            document.getElementById('1'+`${i}`+'4').value = spec_mass_now.toFixed(mass_decimals);
        }
        //now apply changes
        //both volume and mass changes
        if(spec_vol_now != spec_vol_original && spec_mass_now != spec_mass_original) {
            if( spec_vol_now * specCon >= spec_mass_now ) { //volume changes greater than input mass
                document.getElementById('1'+`${i}`+'2_h').value = spec_vol_now;
                document.getElementById('1'+`${i}`+'3').value = (max_rx_vol - spec_vol_now).toFixed(2);
                document.getElementById('1'+`${i}`+'4').value = (spec_vol_now * specCon).toFixed(mass_decimals);
                document.getElementById('1'+`${i}`+'4_h').value = spec_vol_now * specCon;
                
                console.log('both changed: volume changes greater than input mass')
                 
            }
            else {
                document.getElementById('1'+`${i}`+'4_h').value = spec_mass_now;
                document.getElementById('1'+`${i}`+'2').value = (spec_mass_now / specCon).toFixed(2);
                document.getElementById('1'+`${i}`+'3').value = (max_rx_vol - (spec_mass_now / specCon)).toFixed(2);
                document.getElementById('1'+`${i}`+'2_h').value = spec_mass_now / specCon;
                    
                console.log('both changed: input mass greater than volume changes')
                
            }
        }
        //only mass changed
        else if(spec_mass_now != spec_mass_original && spec_mass_now / specCon <= max_rx_vol) {
            document.getElementById('1'+`${i}`+'4_h').value = spec_mass_now;
            document.getElementById('1'+`${i}`+'2').value = (spec_mass_now / specCon).toFixed(2);
            document.getElementById('1'+`${i}`+'3').value = (max_rx_vol - (spec_mass_now / specCon)).toFixed(2);
            document.getElementById('1'+`${i}`+'2_h').value = spec_mass_now / specCon;
            
            console.log('input mass change only')
            
        }
        //only vol changed
        else if(spec_vol_now != spec_vol_original && spec_vol_now * specCon >= min_rna_input) {
            document.getElementById('1'+`${i}`+'2_h').value = spec_vol_now;
            document.getElementById('1'+`${i}`+'3').value = (max_rx_vol - spec_vol_now).toFixed(2);
            document.getElementById('1'+`${i}`+'4').value = (spec_vol_now * specCon).toFixed(mass_decimals);
            document.getElementById('1'+`${i}`+'4_h').value = spec_vol_now * specCon;
            
            console.log('volume change only')
                    
        }
        //make weight font red if mass too low
        if(spec_mass_now < min_rna_input) {
            document.getElementById('1'+`${i}`+'4').style.color = '#dd0238'; // red = danger
        }
        else {
            document.getElementById('1'+`${i}`+'4').style.color = '#494949';
        }
    }
}
</script>
</body>
</html>
~~~~

### procedures
1. Using the above calculator, prepare the RT working solution (RTWS). Return NEB reagents to the freezer.
2. Pipette out the required water for each reaction per the above calculator
3. Pipette 5.75 uL of RTWS into each tube
4. Pipette out the required specimen volumes into each respective tube; gently pipette up and down to ensure that the solutions are well mixed, ensuring not to cross-contaminate
5. Spin tubes or tap gently on benchtop to ensure no drops are present on tube sidewalls
6. Keep the specimens on ice until ready to proceed to the thermocycler
7. Run the NEB WarmStart RTx program: 5 minutes at 25°C for annealing; 10 minutes at 55°C for synthesis; 10 minutes at 80°C for heat inactivation
8. Store cDNA products in -20°C freezer until ready for downstream use
