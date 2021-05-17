
<!DOCTYPE html>
<html>
<head>
	<title>Calculator</title>
	<style>
		#div-1
		{
			text-align: center;
			color: black;
		}
		#div-2
		{
			margin: center;
			display: inline-block;
			background-color: palegreen;
			width: 400px;
			height: 500px;
			border: 5px solid black;
			box-shadow: 10px 10px 10px black;
			border-radius: 10px;

		}
		table 
		{
			margin: auto;
		}
		button
		{
			padding: 10px;
			width: 65px;
			height: 60px;
			background-color:black;
			color: white;
			font-size:20px;
			font-weight: bolder;
			border-radius: 10%;

		}
		input
		{
			width: 270px;
			height: 40px;
			border-radius: 10px;
			font-size: 20px;
			font-weight: bolder;
			border: 2px solid black;
			margin-top: 30px;
			outline: none;
		}
		#divide
		{
			width: 135px;
		}
	</style>
</head>
<body>
   <div id="div-1">
   	<h1>CALCULATOR</h1>
   	<div id="div-2">
   		<input type="text" name="screen"  id="screen" readonly>
   		<table>
   			<tr>
   				<td></td>
   				<td></td>
   			<td><button>C</button></td>
   				   				<td><button><</button></td>
   			</tr>
   			<tr>

   				<td><button>(</button></td>
   				<td><button>)</button></td>
   				
   				<td colspan="2"><button id="divide">%</button></td>
   			</tr>
   			   			<tr>
   				<td><button>7</button></td>
   				<td><button>8</button></td>
   				<td><button>9</button></td>
   				<td><button>X</button></td>
   			</tr>
   			   			<tr>
   				<td><button>4</button></td>
   				<td><button>5</button></td>
   				<td><button>6</button></td>
   				<td><button>-</button></td>
   			</tr>
   			   			<tr>
   				<td><button>1</button></td>
   				<td><button>2</button></td>
   				<td><button>3</button></td>
   				<td><button>+</button></td>
   			</tr>
   			   			<tr>
   				<td><button>.</button></td>
   				<td><button>0</button></td>
   				<td><button>/</button></td>
   				<td><button>=</button></td>

   			</tr>
   		</table>
   	</div>
   </div>


   <script>
   	let screen=document.querySelector("#screen");
   	let buttons=document.querySelectorAll("button");
   	let screenValue='';
   	for(item of buttons){
   	item.addEventListener('click',(a)=>{
   	    buttonText=a.target.innerText;
   		console.log("button Text is" ,buttonText);
   		if (buttonText=='X'){
   			buttonText='*';
   			screenValue += buttonText;
   			screen.value =screenValue;
   		}
   		else if (buttonText=='C') {
   			screenValue="";
   			screen.value= screenValue;
   		}
   		else if (buttonText=='=') {
   			screen.value= eval(screenValue);
   		}
   		else if (buttonText=='<') {
   			 buttonText=screenValue.substring(0,screenValue.length-1);
             screen.value=buttonText;
   			 screenValue=buttonText;
   		}
   		else
   		{
   			screenValue += buttonText;
   			screen.value=screenValue;
   		}
   	})
   }

   </script>
</body>
</html>
