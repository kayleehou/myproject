---
toc: true
layout: post
description: big idea 5.1 and 5.2 questions
categories: [Javascript]
title: Virtual Pet
comments: true

---
<!--
IMPORTANT NOTICE
Virtual pet needs Vitamins M and R.
Virtual pet keeps consuming Vitamins M and R.
Click the appropriate Feed button to restore vitamin.
Virtual pet cannot survive without vitamins M and R.
Virtual pet is entirely dependent on your assistance to acquire necessary nutrition.

This is a repost of a virtual pet thing I did with JavaScript, which I previously posted on GitHub. 
Except now -- look out this thing is sans-serif.
I might do some more stuff to it later.
-->

<head>
  <title>Virtual Pet</title>
</head>


<body>

<!--
Virtual pet is an image (in this case, some rubbish I made with type)
with eyes/face expressing state of pet (well, sick, dead)
-->
	<div id="petImage" class="alignCtr backMe cornered floatLeft">
		
		<div id="petTop">^^^^^^^^</div>
		<div id="petEyes">o....o</div>
		<div id="petMouth">=v====v=</div>
		<div id="petBtm">vvvvvvvv</div>
		
	</div>
	
<!--
Next section is the HUD, which will appear to the right of the pet image.
The three meters (health, vitamin M, vitamin R) are labeled.
There are 2 buttons for feeding your pet vitamin M and vitamin R.
-->
    <div id="hud">
		
		<div id="labels" class="backMe floatLeft">
			<div id="labelH">Life</div>
			<div id="labelVM">Food</div>
			<div id="labelVR">Sleep</div>
		</div>
		
		<div id="meters" class="backMe floatLeft">
			<div id="mtrH" class="cornered heightFix"></div>
			<div id="mtrVM" class="cornered heightFix"></div>
			<div id="mtrVR" class="cornered heightFix"></div>
		</div>
		
		<div id="buttons" class="backMe floatLeft">
			<div id="btnVM" class="feedBtn alignCtr cornered heightFix">Feed</div>
			<div id="btnVR" class="feedBtn alignCtr cornered heightFix">Sleep</div>
		</div>

	</div>
	
	<!--
	Feedback div display state is controlled by Javascript. It will appear under everything else.
	-->
	<div id="feedback" class="alignCtr backMe cornered">Oops, your pet didn't make it! Refresh to try again.</div>
 
  </body>

</html> 

/*
UPDATE 8/18 Improved Feed button response styling
*/

*
{
  font-family: sans-serif;
}

body
{
	color: #1C1C1C; /* near-black */
}

#petImage
{
	width: 100px;
	height: 76px;
}


#labels
{
	margin-left: 10px;
	padding: 2px 0 2px 5px;
	width: 80px;
	border-top-left-radius: 5px;
	border-bottom-left-radius: 5px;
}

#meters
{
	padding: 3px 0 4px 0;
	width: 130px;
}

/*
The meters each have a border color matching their background color, to be manipulated via script as indicators.
*/

#mtrH
{
	background-color: #81F781; /* green */
	border: 1px solid #81F781;
}

#mtrVM
{
	background-color: #FAAC58; /* orange */
	border: 1px solid #FAAC58;
}

#mtrVR
{
	background-color: #5882FA; /* blue */
	border: 1px solid #5882FA;
}

#buttons
{
	padding: 18px 4px 0 0;
	height: 40px;
	width: 50px;
	border-top-right-radius: 5px;
	border-bottom-right-radius: 5px;
}

.feedBtn
{
	background-color: #04B4AE; /* turquoise */
  color: #F2F2F2; /* near white */
  padding: 2px;
  margin: 1px;
}

.feedBtn:hover
{
  background-color: #01DFD7;
}

.feedBtn:active
{
  background-color: #088A85;
}

#feedback
{
	margin-top: 67px;
	padding: 3px 0 4px 0;
	width: 380px;
	float: none;
}


/* Miscellaneous */

.alignCtr
{
	text-align: center;
}

.backMe
{
	background-color: #BDBDBD; /* grey */
}

.cornered
{
	border-radius: 5px;
}

.floatLeft
{
	float: left;
}

.heightFix
{
	height: 15px;
}

(function() {
"use strict";
    
 document.addEventListener('DOMContentLoaded',function(){
	 
     //Variables
	 	//Pet's stats are health, vitamin M, and vitamin R
     var ctMaxH =       30,
         ctMaxVM =      30,
         ctMaxVR =      30,
         
         ctCurH =       ctMaxH,
         ctCurVM =      ctMaxVM,
         ctCurVR =      ctMaxVR,
         
         intervalH =    1000,
         intervalVM =   2000,
         intervalVR =   3000,
         
		 	//When vitamins fall below threshold, pet starts losing health
         threshold =    ctMaxH * 0.6,
         points =       2,
         widther =      4,
         
		 	//When conditions are dangerous, affected stat bars will be hilited in red
		 alive =		true,
         dangerH =      false,
         dangerVM =     false,
         dangerVR =     false,
         
		 	//Get meters to change width and border color
         getMtrH =      document.getElementById('mtrH'),
         getMtrVM =     document.getElementById('mtrVM'),
         getMtrVR =     document.getElementById('mtrVR'),
         
		 getStyleH =    getMtrH.style,
         getStyleVM =   getMtrVM.style,
         getStyleVR =   getMtrVR.style,
		 bdrStart =		"1px solid ",
		 
		 	//Colors for meter borders
		 clrDfltH =     "#81F781",  //green
         clrDfltVM =    "#FAAC58",  //orange
         clrDfltVR =    "#5882FA",  //blue
             
         clrCurH =      clrDfltH,
         clrCurVM =     clrDfltVM,
         clrCurVR =     clrDfltVR,
         
         clrWarn =      "#FF0040", //red
	 
		 	//Get buttons for click events
         getBtnVM =     document.getElementById('btnVM'),
         getBtnVR =     document.getElementById('btnVR'),
         
		 	//Get eyes to express status
		 getEyes =		document.getElementById('petEyes'),
		 eyesOK =		"o....o",
	 	 eyesSick = 	"@....@",
		 eyesDead =		"x....x",
	 
		 	//Get style for the feedback div
	 	 getStyleFb = 	document.getElementById('feedback').style;
		 
    
	 getStyleFb.display = 'none';
	 meterWidth();
	 
     //At set intervals, vitamin M decreases.
     setInterval(function(){
		 if(alive == true){
				loseVM();
			 	checkDangerVM();
	 	}
     },intervalVM);
     
     //At set intervals, vitamin R decreases.
     setInterval(function(){
		 if(alive == true){
				loseVR();
			 	checkDangerVR();
		 }
     },intervalVR);
     
     /*
	 What happens in this nest:
	 Health starts to drop if vitamin M or vitamin R are too low.
	 Meter graphics are adjusted as applicable.
	 If the pet is dead, then the ending events trigger.
	 */
     setInterval(function(){
		 
		 meterWidth();
		 checkDangerH();

		 //Adjust graphics
		 if(dangerH == true)
             {
				warnH();
				loseH();  
             }
		 else
		 	{
				okH();
			}
		 
		 if(dangerVM == true)
             {
				 warnVM();      
             }
		 else
			 {
				 okVM();
			 }
	 
		 if(dangerVR == true)
             {
				 warnVR();      
             }
		 else
			 {
				 okVR();
			 }
	 
	 //When your pet runs out of health, it will be a gonner.
	 if(ctCurH < 0){
		 alive = false;
	 }
		 
     if(alive == false)
        {
            ending();
        }
		 
     },intervalH);


     //Clicking on a "Feed" button will restore vitamin and health to your pet.
     getBtnVM.addEventListener("click",function(){
		 if(alive == true){
			 if(ctCurVM + points <= ctMaxVM)
			 	{
					ctCurVM = ctCurVM + points;
				 
					if(ctCurH + points < ctMaxH)
						{
							ctCurH = ctCurH + points;
						}
				 
					meterWidth();
				 
					//Check conditions and adjust graphics as appropriate.
					checkDangerH();
					checkDangerVM();
					checkDangerVR();
				 
					if(dangerH == false)
					{okH();}
					if(dangerVM == false)
					{okVM();}
					if(dangerVR == false)
					{okVR();}
			 }
		 }
	 });
	 
     getBtnVR.addEventListener("click",function(){
		 if(alive == true){
		 	if(ctCurVR + points <= ctMaxVR)
				{
					ctCurVR = ctCurVR + points;
				 
					if(ctCurH + points < ctMaxH)
						{
							ctCurH = ctCurH + points;
						}
				 
					meterWidth();
				 
					//Check conditions and adjust graphics as appropriate.
					checkDangerH();
					checkDangerVM();
					checkDangerVR();
				 
					if(dangerH == false)
						{okH();}
					if(dangerVM == false)
						{okVM();}
					if(dangerVR == false)
						{okVR();}
             }
		 }
	 });
     
	 
     //Functions
	 
	 function meterWidth(){
		 //This updates the width of the meters.
			getStyleH.width = ctCurH * widther + "px";	 
		 	getStyleVM.width = ctCurVM * widther + "px";	 
		 	getStyleVR.width = ctCurVR * widther + "px";	 
	 }
	 
	 function checkDangerVM(){
		 		if(ctCurVM < threshold)
					{
						dangerVM = true;
					}
		 		else
					{
						dangerVM = false;	
					}
	 }
	 
	 function checkDangerVR(){
		 		if(ctCurVR < threshold)
					{
						dangerVR = true;
					}
		 		else
					{
						dangerVR = false;	
					}
	 }
	 
	 function checkDangerH(){
		 if((ctCurVM < threshold || ctCurVR < threshold)  && alive == true)
             {
                 dangerH = true;
             }
		 else
			 {
				 dangerH = false;
			 }
	 }
	
     function loseVM(){
         ctCurVM = ctCurVM - points;
     }
     
     function loseVR(){
         ctCurVR = ctCurVR - points;
     }
     
     function loseH(){
          ctCurH = ctCurH - points;        
     }
	 
	 function warnVM(){
		 getEyes.innerHTML = eyesSick;
		 getStyleVM.border = bdrStart + clrWarn;
	 }
	 
	 function warnVR(){
		 getEyes.innerHTML = eyesSick;
		 getStyleVR.border = bdrStart + clrWarn;
	 }
	 
	 function warnH(){
		 getEyes.innerHTML = eyesSick;
		 getStyleH.border = bdrStart + clrWarn;
	 }
	 
	 function okVM(){
		 getStyleVM.border = bdrStart + clrDfltVM;
	 }
	 
	 function okVR(){
		 getStyleVR.border = bdrStart + clrDfltVR;
	 }
     
	 function okH(){
		 getEyes.innerHTML = eyesOK;
		 getStyleH.border = bdrStart + clrDfltH;
	 }
	 
     function ending(){
		 getEyes.innerHTML = eyesDead;
		 getStyleFb.display = 'block';
     }
     
    });
    
})();