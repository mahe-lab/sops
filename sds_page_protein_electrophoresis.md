
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
- Ammonium Persulfate (APS) is highly reactive/flammable and is an oxidizer; handle gently, and dispense only a small amount
- Care must be taken during electrophoresis to avoid electric shock

### ppe
- Lab Coat
- Eye Protection
- Nitrile Gloves

### where
- Fumehood
- Post-PCR Bench (casting and electrophoreis only)

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
- 0.5M Tris (pH 6.8): in a beaker, dissolve 6g Tris base in 60mL ddH<sub>2</sub>O (heat/stir) and adjust pH 6.8 with 12 M HCL (slowly, as an overshoot is not salvageable); pout into 100mL graduated cylinder and top off to 100mL with ddH<sub>2</sub>O, sore in a labled 100mL bottle at 4°C
- 1.5M Tris (pH 8.8):  in a beaker, dissolve 18.15g Tris base in 60mL ddH<sub>2</sub>O (heat/stir) and adjust pH 8.8 with 12 M HCL (slowly, as an overshoot is not salvageable); pout into 100mL graduated cylinder and top off to 100mL with ddH<sub>2</sub>O, sore in a labled 100mL bottle at 4°C
- 10% w/v SDS: dissolve 10g SDS in 60-90 mL ddH<sub>2</sub>O (heat/stir slowly); top up to 100mL with ddH<sub>2</sub>O; store in a labelled 100 mL bottle at RT
- Specimen buffer (reducing): In a 15mL Falcon tube, combine 3.55 mL ddH<sub>2</sub>O; 1.25 mL 0.5 M Tris (pH 6.8); 2.5 mL glycerol; 2.0 mL 10% (w/v) SDS; 0.2 mL 0.5% (w/v) bromophenol blue. Store at RT
- 10x Running Buffer: 30.3 g Tris base; 144 g glycine; 10 g SDS in 1L. NO pH ADJUSTMENT. Store at 4°C
- 
- Prepare the gel cassette sandwich(es):
- For each gel, obtain one each of a short and tall glass plate
- Identify two 1 mm spacers and line them up correctly (flush) at either side of the gel (use the spacer card to assist with placement of the spaces relative to the glass plates)
- Slide the sandwich carefully into the clamp assembly with the short plate to the exterior
- Prior to securing the knobs, stand the apparatus up in the alignment tray of the casting stand to ensure that the glass plates and spacers are flush at the bottom; tighten the knobs to secure
- Move the clamp assembly to the casting slot and gently push into place; two gels can be cast on one casting stand at a time
- Check for leaks by dripping a few mLs of 100% ethanol into the sandwich; ensure that this is well dried up with a kimwipe once complete (residual ethanol will impede gel casting)
- Select the correct comb for the indicated number of wells and place in the upper opening of the sandwich; mark 1 cm below the teeth of the comb. This is the height to which the lower resolving gel should be cast

### calculator
~~~~
<!DOCTYPE html>
<html lang="en">
    <head>
        <meta name="viewport" content="width=device-width, initial-scale=1.0">
        <link rel="stylesheet" href="mahe-lab_style.css">
        <title>MAHELAB SOP Calculator</title>
        <style>
            .vertical-line {
                border-left: 5px solid --tred;
                height: 250px;
                position: absolute;
            }
        </style>
    </head>
<body>
<!---configure reagent prep details here--->
<table id="table1">
<tr><td>Number of gels to be cast:</td><td><input type="number" id="01" min="1" step="1" value="2"></td></tr>
<tr><td>Number of lanes/wells per gel (if using a size standard, ensure that an additional well is present to account for this):</td><td><select id="02"><option value="5">5 wells (max 105 μl each)</option><option value="9">9 wells (max 44 μl each)</option><option selected value="10">10 wells (max 44 μl each)</option><option value="15">15 wells (max 26 μl each)</option></select></td></tr>
</table>
<br>
<button type="button" class="button" onclick="calculate()">Calculate</button>
<br>
<table id="table2">
    <tr><td></td><td></td></tr>
    <tr><td>Calculations for running buffer:</td><td></td></tr>
    <tr><td>10x Running buffer stock (mL):</td>
    <td><input readonly type="text" size="10px" id="calc20"/></td></tr>
    <tr><td>ddH<sub>2</sub>O for 1x running buffer (mL):</td><td><input readonly type="text" size="10px" id="calc21"/></td></tr>
    <tr><td></td><td></td></tr>
    <tr><td>Calculations for 10% Resolvibng Gel(s):</td><td></td></tr>
    <tr><td>30% bis/tris acrylamide stock (mL):</td><td><input readonly type="text" size="10px" id="calc22"/></td></tr>
    <tr><td>1.5M Tris (pH 8.8) stock (mL):</td><td><input readonly type="text" size="10px" id="calc23"/></td></tr>
    <tr><td>Volume ddH<sub>2</sub>O (mL):</td><td><input readonly type="text" size="10px" id="calc24"/></td></tr>
    <tr><td>10% SDS (uL):</td><td><input readonly type="text" size="10px" id="calc25"/></td></tr>
    <tr><td></td><td></td></tr>
    <tr><td>Calculations for 4% Resolvibng Gel(s):</td><td></td></tr>
    <tr><td>30% bis/tris acrylamide stock (mL):</td><td><input readonly type="text" size="10px" id="calc26"/></td></tr>
    <tr><td>0.5M Tris (pH 8.8) stock (mL):</td><td><input readonly type="text" size="10px" id="calc27"/></td></tr>
    <tr><td>Volume ddH<sub>2</sub>O (mL):</td><td><input readonly type="text" size="10px" id="calc28"/></td></tr>
    <tr><td>10% SDS (uL):</td><td><input readonly type="text" size="10px" id="calc29"/></td></tr>
    <tr><td></td><td></td></tr>
    <tr><td>Calculations for specimen loading buffer:</td><td></td></tr>
    <tr><td>Specimen buffer stock (uL):</td><td><input readonly type="text" size="10px" id="calc210"/></td></tr>
    <tr><td>β-Mercaptoethanol (uL) :</td><td><input readonly type="text" size="10px" id="calc211"/></td></tr>
    <tr><td></td><td></td></tr>
    <tr><td>Specimen volume (uL) per well:</td><td><input readonly type="text" size="10px" id="calc212"/></td></tr>
    <tr><td>Specimen loading buffer volume (uL) per well:</td><td><input readonly type="text" size="10px" id="calc213"/></td></tr>
</table>
<br><br>
<button type="button" class="button" onclick="addGels()">Add Gel Configuration Table</button>
<br><br>
<table style="visibility:hidden" id="table3"></table>
<script type='text/javascript'>
function calculate() {
    var count = parseInt(document.getElementById('01').value);
    var wells = parseInt(document.getElementById('02').value);
    var well_volume = 44;
    if(wells == "5") { well_volume = 105; }
    if(wells == "15") { well_volume = 26; }
    document.getElementById('calc20').value = ((2 * Math.round(count / 2)) * 25).toFixed(1);
        document.getElementById('calc21').value = ((2 * Math.round(count / 2)) * 225).toFixed(1);
        document.getElementById('calc22').value = (count * 1.75).toFixed(1);
        document.getElementById('calc23').value = (count * 1.25).toFixed(1);
    document.getElementById('calc24').value = (count * 1.75).toFixed(1);
        document.getElementById('calc25').value = (count * 50).toFixed(1);
    document.getElementById('calc26').value = (count * 0.65).toFixed(1);
        document.getElementById('calc27').value = (count * 1.25).toFixed(1);
    document.getElementById('calc28').value = (count * 3.05).toFixed(1);
        document.getElementById('calc29').value = (count * 50).toFixed(1);
    document.getElementById('calc210').value = (count * well_volume * wells * (3/4)).toFixed(1);
    document.getElementById('calc211').value = (count * well_volume * wells * 0.05 * (3/4)).toFixed(1);
    document.getElementById('calc212').value = (well_volume / 4).toFixed(1);
    document.getElementById('calc213').value = (3 * well_volume / 4).toFixed(1);
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
        //add empty row
	    var t3rws = table3.rows.length;
        var row = table3.insertRow(t3rws);
        row.style.height = '40px';

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
1. Prepare the running buffer (use the calculator above)
2. Prepare the gel cassette sandwich as directed above
3. Prepare fresh APS when ready to pour gels: 50 mg in 500 uL ddH<sub>2</sub>O
4. Prepare the 10% resolving gel solution (use the calculator above); mix gently and DEGAS for 15 minutes
5. When ready to cast the gel(s), in the fumehood add 50 uL APS and 5 uL TEMED
6. Quickly return to the gel casting stand and pipette in the activated gel up to the marker line
7. Quickly but gently overlay the gel with ddH<sub>2</sub>O and allow to stand for one hour; once the gel has polymerized, use filter paper to carefully remove the overlain ddH<sub>2</sub>O
8. Prepare the 4% stacking gel solution (use the calculator above); mix gently and DEGAS for 15 minutes
9. When ready to cast the gel(s), in the fumehood add 50 uL APS and 5 uL TEMED
10. Quickly return to the gel casting stand and pipette in the activated gel; place the gel combs; allow to polymerize for one hour
11. SAFE STOP: Store flat and wrapped in plastic wrap at 4°C (keep comb in place) until ready for use
12. When ready for electrophoresis, remove the specimens/extracts from the freezer and allow to warm to RT
13. Prepare the specimen loading buffer (use the calculator above)
14. For each well, mix the corresponding specimen and specimen loading buffer, at the volume ratios indicated in the calculator above, in a clean tube and heat to 95°C in the Thermomixer x 5 minutes (to denature)
15. Carefully remove gel combs
16. Assemble the upper buffer chamber by attaching the clamp assembly/gel sandwich to the cooling core (electrode assembly) such that the gel sandwich abuts the u-shaped gasket (knobs face out). If not running two gels, the opposite side can be set up with a buffer dam (two glass plates together WITHOUT spacers in a clamp assembly)
17. Place the inner cooling core into the lower buffer chamber
18. Add running buffer to the upper chamber until the level of fluid reaches halfway between the long and short glass plates (be sure that buffer does not overflow)
19. Using a syringe or gel tips, carefully add each denatured specimen mix (including size standards, if applicable) into its designated well
20. Place the lid on the lower buffer chamber, attach electrodes and run the electrophoresis at 200V (60 mA for one gel or 120 mA for two gels) x 45 minutes.
21. Verify the position of the gel front using the position of the bromophenol blue dye
22. When electrophoresis is complete, remove the electrodes/lid, remove the inner chamber and detach the clamp assembly and remove the gel sandwich by loosening the knobs
23. Gently peel off the shorter glass plate and remove the spacers
24. Peel off the upper stacking gel and discard in the contaminated gel waste bucket
25. Make a notch at the top left of the resolving gel to indicate the position of the first well/top of the gel
26. Proceed immediately to STAINING or BLOTTING
