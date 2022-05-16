//Convert a number to a roman Numeral.

function toRoman(num,pos) { /*convert a digit into roman depending on position
                            (thousands, hundreds, etc)*/
  let romanNum = "";
  if (pos == 4) {
    romanNum = "M".repeat(num);
  }
  if (pos == 3) {
    if (num == 0) {
    } else if (num < 4) {
      romanNum = "C".repeat(num);
    } else if (num == 4) {
      romanNum = "CD";
    } else if (num == 5) {
      romanNum = "D"
    } else if (num > 5 && num < 9) {
      romanNum = "D" + "C".repeat(num-5)
    } else {
      romanNum = "CM"
    }
  }
  if (pos == 2) {
    if (num == 0) {
    } else if (num < 4) {
      romanNum = "X".repeat(num);
    } else if (num == 4) {
      romanNum = "XL";
    } else if (num == 5) {
      romanNum = "L"
    } else if (num > 5 && num < 9) {
      romanNum = "L" + "X".repeat(num-5)
    } else {
      romanNum = "XC"
    }
  }
  if (pos == 1) {
    if (num == 0) {
    } else if (num < 4) {
      romanNum = "I".repeat(num);
    } else if (num == 4) {
      romanNum = "IV";
    } else if (num == 5) {
      romanNum = "V"
    } else if (num > 5 && num < 9) {
      romanNum = "V" + "I".repeat(num-5)
    } else {
      romanNum = "IX"
    }
  }
  return romanNum
}

function convertToRoman(num) {
 let roman = "";
 let numStr = num.toString();
 let numChars = numStr.length; // to know if it's thousands, hundreds, etc.
 let i = 0
 // iterate through the digits based on position starting at thousands.
 while (numChars > 0) {
   roman += toRoman(parseInt(numStr[i]),numChars)
   numChars--
   i++
 }

 
 return roman;
}


console.log(convertToRoman(36)); //result XXXVI
console.log(convertToRoman(3999)); //result MMMCMXCIX