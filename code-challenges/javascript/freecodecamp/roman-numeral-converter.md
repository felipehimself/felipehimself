**Description:**

Convert the given number into a roman numeral.

All roman numerals answers should be provided in upper-case.


**My Solution:**

```
function convertToRoman(num){
 const deC = ["",
             "I",
             "ii", 
             "iii", 
             "iv",
             "v",
             "vi",
             "vii",
             "viii",
             "ix"]
const deC2 = ["",
             "x",
             "xx",
             "xxx",
             "xl",
             "l",
             "lx",
             "lxx",
             "lxxx",
             "xc"]

const deC3 = ["",
             "c",
             "cc",
             "ccc",
             "cd",
             "d",
             "dc",
             "dcc",
             "dccc",
             "cm"]   
 const decM = ["m"]
             
let str = num.toString();
let arr = str.split('');
let l = arr.length;
let r = "";

if (l == 1){
	r += deC[num]
}

else if (l == 2){
  r += deC2[arr[0]] + deC[arr[1]]
}

else if (l == 3){
  r += deC3[arr[0]] + deC2[arr[1]] + deC[arr[2]] 
}

else if (l == 4){
  r +=  decM[0].repeat(arr[0]) + deC3[arr[1]] + deC2[arr[2]] + deC[arr[3]]
}

return r.toUpperCase()
}

convertToRoman(36);
```
