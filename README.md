# JavascriptAddInt
A javascript code to add 2 integers, html textboxes only accept integer input.
Save below file as add.html and open it into a web browser.

<!doctype html Written By - Atul Rauthan>
<html>
<head>
	<title>Addin two integers using JavaScript</title>
	<script type="text/javascript">
//Function to get sum
function getsum(){
var int1=document.getElementById("i1").value;
var int2=document.getElementById("i2").value;
int1=parseInt(int1);
int2=parseInt(int2);
var sum=int2+int1;
//window.alert(sum);
var lblValue = document.getElementById("lblValue");
//lblValue.innerText = "The text box contains: "+sum;
document.getElementById('sum').value=sum;
}
//Not implemented in this
function isNumber1(evt) {
    evt = (evt) ? evt : window.event;
    var charCode = (evt.which) ? evt.which : evt.keyCode;
    if (charCode > 31 && (charCode < 48 || charCode > 57)) {
        return false;
    }
    return true;
}
//function to check if input is an integer
function isNumber(obj) {
    var inp=obj.value;
    //window.alert(inp);
    inp=reverse(inp);
    var charCode = inp.charCodeAt(0);
    //window.alert(charCode);
    if (charCode > 47 && charCode < 58 ) {
    	 //window.alert("integer");
       	 getsum();
       }
    else{
    	window.alert("Only integers allowed");
      	obj.value="";  
 }
}
//function to reverse a string
function reverse(s) {
  var o = '';
  for (var i = s.length - 1; i >= 0; i--)
    o += s[i];
  return o;
}
</script>
	
</head>
<body>
	<h2>Adding two integers</h2>
	Ente First Integer:
	<input type="text" name="int1" id="i1" placeholder="enter first integer" onkeyup="isNumber(this)"><br><br>
	Ente Second Integer:
	<input type="text" name="int2" id="i2" placeholder="enter second integer" onkeyup="isNumber(this)"><br><br>
	<br>
	Sum of integers is:
	<input type="text" name="sum" id="sum" placeholder="Sum of the integers" value="">
	<span id="lblValue">The text box contains: </span>
</body>
</html>
