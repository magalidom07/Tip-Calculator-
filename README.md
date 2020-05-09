# Tip-Calculator-
*This Tip calculator would help you know how much money you should tip a waiter based on the quality of service. First you can type the bill amount, then the quality of service, and the number of people splitting the bill when you are done just press the heart and you will get your result!
*To create the tip calculator I decided to use codepen because of how accesible it made runing a html, css, and Java. 
I was originally going to use a library of P5 but i found it rather dificult and I didnt think it really added much to my project
*I also had to learn some aspects of codepen that were diferent from the other platforms we have used in the past
*I also realised that i wasnt able to use some functionalities because i was using the free package of CodePen
The HTML was the easiest part of the project once I learnd how to use IDs

 <div id="container">
  <h1>Tip Calculator</h1>
  <div id="calculator">


    <form>
      <p>Bill amount?
        <p>
          $ <input id="billamt" type="text" placeholder="Bill Amount">

          <p>quality of service?
            <p>
              <select id="serviceQual">
            <option disabled selected value="0">-- 
            <option value="0.3">30&#37; &#45; Exellent</option>
            <option value="0.2">20&#37; &#45; 
Ordinary </option>
            <option value="0.15">15&#37; &#45; It was Terrible</option>
        </select>

    </form>
    <p>Number  of people sharing the bill?</p>
    <input id="peopleamt" type="text" placeholder="Number of People"> people
    <button type="button" id="calculate">♥</button>

  </div>
  <div id="totalTip">
    <sup>$</sup><span id="tip">0.00</span>
    <small id="each">each</small>
  </div>
</div>
<script type="text/javascript" src="tipcalculator.js"></script>

//The hardest part was the css file so i decided to keep it very simple and just add a nice font and a solid background

@import url(https://fonts.googleapis.com/css?family=Cutive+Mono);
body {
  font-family: Cutive Mono;
background-color: lightgreen;
}
h1 {
    align-self: stretch;
    margin: 0;
    padding: 1em 0;
    text-align: center;
    background: rgba(white, .8);
}
 gistfile3.txt
 
 
 
 
//Using the HTML's ID, variables, functions and a couple of if and else statements i was able to create the code for the functionality of the calculator aka, the math aspect of it.
function calculateTip() {
  
  var billAmt = document.getElementById("billamt").value;
  var serviceQual = document.getElementById("serviceQual").value;
  var numOfPeople = document.getElementById("peopleamt").value;

  if (billAmt === "" || serviceQual == 0) {
    alert("Please enter values");
    return;
  }

  if (numOfPeople === "" || numOfPeople <= 1) {
    numOfPeople = 1;
    document.getElementById("each").style.display = "none";
  } else {
    document.getElementById("each").style.display = "block";
  }

  var total = (billAmt * serviceQual) / numOfPeople;

  total = Math.round(total * 100) / 100;
 
  total = total.toFixed(2);
  document.getElementById("totalTip").style.display = "block";
  document.getElementById("tip").innerHTML = total;

}

document.getElementById("totalTip").style.display = "none";
document.getElementById("each").style.display = "none";

document.getElementById("calculate").onclick = function() {
  calculateTip();

};


Overal, I wish the aesthetic of the calculator was better, but. for me the most important part was for the calculator to have functionality.
