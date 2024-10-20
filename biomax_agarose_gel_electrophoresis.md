
### protocol
- Protocol: BioMax Agarose Gel Electrophoresis
- Faculty: Cumming School of Medicine
- Institute: Charbonneau Cancer Institute
- Site: Arthur J.E. Child Comprehensive Cancer Center, YC083402
- Version: 2
- Version Date: 7MAY2024
- Approver: ermahe@ucalgary.ca

### authorization
- Requires Completion of Safety Training
- Requires Pre-Authorization by PI

### hazards
- Ethidium bromide is mutagenic & carcinogenic. DO NOT MICROWAVE ETHIDIUM BROMIDE!
- Care must be taken to avoid electric shock when performing electrophoresis

### ppe
- Lab Coat
- Eye Protection
- Nitrile Gloves

### where
- Make solutions in fumehood, as required
- Post-PCR Bench

### references
- See BioMax Manual: https://github.com/mahe-lab/sops/tree/main/MAHELAB_SOP_Assets/BioMax_QS710_Manual.pdf

### emergency
- If skin/eye contact with chemicals, flush aggressively and continuously with water using an eyewash, sink or shower
- Contact emergency services and log any injuries if required

### cleanup
- Wipe down work surfaces with 70% isopropanol
- NOTE: Do not use isopropanol on instruments

### waste
- Tips/Tubes should be disposed of in yellow biohazard bag/tub

### maintenance
- Rinse electrophoresis equipment components with distilled water after use.
- Do not use universal cleaner or other detergents on gel apparatus (this may cause damage).

### before_starting
- If required, make 50xTAE stock:
- Prepare 0.5 M EDTA: 93.05 g of EDTA disodium salt (MW=372.24 g/mol); dissolve in 400 mL ddH2O and adjust the pH to 8; top up to 500 mL with ddH2O
- Weigh out 242 g of Tris-base (MW = 121.14 g/mol) and dissolve in ~700 mL of ddH2O; carefully add 57.1 mL of 100 % glacial acetic acid (in fumehood!) and 100 mL of 0.5 M EDTA (pH 8.0); adjust to a final volume of 1 L with ddH2O

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
<tr><td>Number of lanes/wells per gel (if using a size standard, ensure that an additional well is present to account for this):</td><td><select id="02"><option value="8">8 wells </option><option value="10">10 wells </option><option selected value="12">12 wells </option><option value="15">15 wells </option></select></td></tr>
<tr><td>Gel Size:</td><td><select id="03"><option value="Small">Small size gel </option><option value="Large">Large size gel </option></select></td></tr>
<tr><td>% Agarose:</td><td><input type="number" id="04" min="0.1" step="0.1" value="1"></td></tr>
</table>
<br>
<button type="button" class="button" onclick="calculate()">Calculate</button>
<br>
<table id="table2">
    <tr><td></td><td></td></tr>
    <tr><td>Calculations for 1x TAE buffer:</td><td></td></tr>
    <tr><td>50x TAE buffer stock (mL):</td>
    <td><input readonly type="text" size="10px" id="calc20"/></td></tr>
    <tr><td>Up to a total volume (with ddH<sub>2</sub>O) of:</td><td><input readonly type="text" size="20px" id="calc21"/></td></tr>
    <tr><td></td><td></td></tr>
    <tr><td>Calculations for Agarose Gels:</td><td></td></tr>
    <tr><td>Weight of Agarose (g):</td><td><input readonly type="text" size="10px" id="calc22"/></td></tr>
    <tr><td>Volume of buffer (mL):</td><td><input readonly type="text" size="10px" id="calc23"/></td></tr>
    <tr><td>Volume of Ethidium Bromide Required (uL):</td><td><input readonly type="text" size="10px" id="calc24"/></td></tr>
    <tr><td></td><td></td></tr>
</table>
<br><br>
<button type="button" class="button" onclick="addGels()">Add Gel Configuration Table</button>
<br><br>
<table style="visibility:hidden" id="table3"></table>
<script type='text/javascript'>
function calculate() {
    	var count = parseInt(document.getElementById('01').value);
	var wells = parseInt(document.getElementById('02').value);
	var size = 50;
	var perc = parseFloat(document.getElementById('04').value);
	if (document.getElementById('03').value === "Large") {size = 100;}
	document.getElementById('calc20').value = (count * size * 6 * (1/50));
	document.getElementById('calc21').value = "" + Math.round(count * size * 6) + " mL \(" + Math.round(count * size * 6 * (49/50)) + " mL ddH2O\)";
	document.getElementById('calc22').value = (count * size * perc * (1/100));
	document.getElementById('calc23').value = Math.round(count * size);
	document.getElementById('calc24').value = Math.round(count * (size/50) * 25);
}
function addGels() {
    const band_width = 40;
    //empty the table if already filled
    var table3 = document.getElementById('table3');
    var t3rws = table3.rows.length;
    if(t3rws>0) {
        for(var ii=0;ii<t3rws;ii++) {
            table3.deleteRow(-1);
        }
    }
    //turn on the table & add the appropriate number of columns = # of wells + 1
    table3.style="visibility:none";
    var count = parseInt(document.getElementById('01').value);
    var wells = parseInt(document.getElementById('02').value);
    table3.style.width = `${(wells+1)*band_width}px`;
    for(var g=0;g<count;g++) {
        //first row of gel = lane names
        var t3rws = table3.rows.length;
        var row = table3.insertRow(t3rws);
        row.style.height = '100px';
        for(var c=0;c<wells+1;c++) {
            var cell = row.insertCell(c);
            //cell.style.width = '5px';
            if(c>0) {
                var laneName = document.createElement('input'); 
                laneName.setAttribute('type','text'); 
                laneName.setAttribute('size','10px');
                laneName.setAttribute('id',`3${t3rws}${c}`);
                cell.appendChild(laneName);
                cell.style.transform = 'rotate(-90deg)';
                cell.style.transformOrigin = '100% 50%';
            }
        }
        //second row of gel = gel image in iframe
        var t3rws = table3.rows.length;
        var row = table3.insertRow(t3rws);
        row.style.height = '250px';
        //sliders
        var col0 = row.insertCell(0);
        var sld1 = document.createElement('input');
        sld1.type = "range";
        sld1.setAttribute('class','slider');
        sld1.setAttribute('min','1');
        sld1.setAttribute('max','100');
        sld1.setAttribute('value','100');
        sld1.setAttribute('id',`3_v_${g}`);
        sld1.addEventListener("change",function(event){changeVerticalSize(event.target.id);});
        col0.appendChild(sld1);
        var sld2 = document.createElement('input');
        sld2.type = 'range';
        sld2.setAttribute('class','slider');
        sld2.setAttribute('min','1');
        sld2.setAttribute('max','100');
        sld2.setAttribute('value','100');
        sld2.setAttribute('id',`3_h_${g}`);
        sld2.addEventListener("change",function(event){changeHorizontalSize(event.target.id);});
        col0.appendChild(sld2);
        col0.style.transform = 'rotate(-90deg)';
        //iframe in div wrapper in table cell
        var col1 = row.insertCell(1);
        col1.colSpan = wells;
        
        var ifrm = document.createElement('iframe');
        ifrm.setAttribute('id',`3_ifrm_${g}`);
        ifrm.setAttribute('height',row.style.height);
        ifrm.setAttribute('width',(wells+1)*band_width);
        ifrm.style.cssText = 'position: relative; border: 0';
        ifrm.src = 'about:blank';
        col1.appendChild(ifrm);
        var w = document.createElement('input');
        w.type = 'hidden';
        w.setAttribute('id',`3_ifrm_${g}_width`);
        col1.appendChild(w);
        var h = document.createElement('input');
        h.type = 'hidden';
        h.setAttribute('id',`3_ifrm_${g}_height`);
        col1.appendChild(h);
        //third row of gel = file selector and load button
        var t3rws = table3.rows.length;
        var row = table3.insertRow(t3rws);
        row.style.height = '20px';
        var col0 = row.insertCell(0);
        col0.colSpan = 1+wells;
        var addimg = document.createElement('input');
        addimg.type='file';
        addimg.setAttribute('accept', 'image/*');
        addimg.setAttribute('id',`3_fb_${g}`);
        col0.appendChild(addimg);
        var upimg = document.createElement('button');
        upimg.setAttribute('id',`3_ub_${g}`);
        upimg.innerHTML = 'Upload';
        upimg.style.height = '22px';
        upimg.style.width = '60px';
        upimg.addEventListener("click",function(event){loadImgFile(event.target.id);});
        col0.appendChild(upimg);
	//add empty row
	var t3rws = table3.rows.length;
        var row = table3.insertRow(t3rws);
        row.style.height = '40px';
    }
}
function loadImgFile(btn_id) {
    var wells = parseInt(document.getElementById('02').value);
    //figure out which file and iframe to reference based on the id
    var id_num = btn_id.split('_')[2];
    var iframe_id = document.getElementById(`3_ifrm_${id_num}`);
    var file_select_id = document.getElementById(`3_fb_${id_num}`);
    // remove any child nodes
    while (iframe_id.contentWindow.document.getElementsByTagName("body")[0].firstChild) {
        iframe_id.contentWindow.document.getElementsByTagName("body")[0].removeChild(iframe_id.contentWindow.document.getElementsByTagName("body")[0].lastChild);
    }
    // check if file name set
    if (file_select_id.files.length == 1) {
        var reader = new FileReader();
        reader.onload = function(event) {
            var newImage = document.createElement("img");
            newImage.setAttribute('id',`3_img_${id_num}`);
            newImage.src = event.target.result;
            iframe_id.contentWindow.document.getElementsByTagName("body")[0].appendChild(newImage);
            document.getElementById(`3_ifrm_${id_num}_width`).value = newImage.width;
            document.getElementById(`3_ifrm_${id_num}_height`).value = newImage.height;
            iframe_id.contentWindow.document.getElementsByTagName("body")[0].style.cssText = 'overflow: hidden';
        };
        reader.readAsDataURL(file_select_id.files[0]);
        
     
    }
    iframe_id.contentWindow.document.getElementsByTagName("body")[0].style.scrollbarWidth = 'none';
    
}
function changeHorizontalSize(btn_id) {
    var id_num = btn_id.split('_')[2];
    var range = document.getElementById(`3_h_${id_num}`).value;
    document.getElementById(`3_ifrm_${id_num}`).contentWindow.document.getElementsByTagName("body")[0].childNodes[0].width = (range/100) * document.getElementById(`3_ifrm_${id_num}_width`).value;
}
function changeVerticalSize(btn_id) {
    var id_num = btn_id.split('_')[2];
    var range = document.getElementById(`3_v_${id_num}`).value;
    document.getElementById(`3_ifrm_${id_num}`).contentWindow.document.getElementsByTagName("body")[0].childNodes[0].height = (range/100) * document.getElementById(`3_ifrm_${id_num}_height`).value;
}
</script>
</body>
</html>
~~~~
### procedures
1. Weigh out (in an Erlenmeyer flask) the agarose (see calculator above)
2. Add 1x TAE (see calculator above)
3. Microwave the agarose slurry on high in 30 s increments until boiling
4. Allow agarose solution to cool to ~60C
5. Add Ethidium bromide
6. Assemble gel cast apparatus and insert combs
7. Pour in agarose; remove bubbles with a pipette tip; allow to cool for at least 30 minutes
8. Carefully Remove comb(s) and remove the cast gel base from the casting stand.
9. Place cast gel into the electrophoresis tray with wells closest to the black lead
10. Pour in sufficient 1xTAE to fully immerse the gel
11. On a 10 cm length of parafilm, mark out the gel specimens (including ladders) with a sharpie pen
12. Pipette ~1 uL Gel-Red/Gel-Green/Loading-Buffer Dye onto each parafilm spot
13. Pipette ~6 uL of one of the molecular weight ladders (“Millipore Direct Load” or “Thermo TrackIt”) onto the corresponding spot
14. Dial up the pipette to 6-7 uL and draw up the mix; gently pipette into the first gel well
15. Pipette ~5 uL of each subsequent specimen onto the corresponding spot
16. Dial up the pipette to 6-7 uL and draw up the mix; gently pipette into the corresponding well
17. Once the gel is fully loaded, apply the electrophoresis cover, and run the gel at 100V for 60 minutes. Be sure to set the powerpack time to ensure auto-halt.
18. Proceed to imaging using the GelDoc EtBr protocol: Refer to GelDoc SOP
19. Disassemble the apparatus and rinse with distilled water
