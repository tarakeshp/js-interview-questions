# js-interview-questions

## Q1: Rotate elements in a array with given index by Clock wise and Anti Clockwise
#### start index is 2
### Clock wise Solution 1 
`var tmp = "";`    
`var arr = [ "a", "b", "c", "d", "e", "f" ];`    
`for(var i = 2; i < arr.length; i++) {`   
    `tmp = tmp + arr[i];`    
`}`   

`for(var i = 0; i < 2; i++) {`   
	`tmp = tmp + arr[i];`    
`}`   

`console.log("clock wise %s", tmp); //cdefab`  

### Clock wise Solution 2
`tmp = "";`    
`for(var i=0; i< arr.length; i++) {`   
   `tmp = tmp + (arr[(2+i) % arr.length]); `      
`}`   
`console.log("close wise-2 %s", tmp); //cdefab`   
### Anti-Clock wise Solution 1
`tmp = "";`   
`for(var i=arr.length; i > 0; i--) {`    
   `tmp = tmp + (arr[(2+i) % arr.length]);`  
`}`   
`console.log("anti close wise-1 %s", tmp); //cbafed`   
### Anti-Close Wise Solution 2
`tmp = "";`   
`var arr = [ "a", "b", "c", "d", "e", "f" ];`   
`for(var i=2; i >= 0; i--) {`   
  `tmp = tmp + arr[i];`   
`}`   
`for(var i=arr.length - 1; i > 2; i--) {`   
   `tmp = tmp + arr[i];`   
`}`   

`console.log("anti close wise-2 %s", tmp); //cbafed`   
