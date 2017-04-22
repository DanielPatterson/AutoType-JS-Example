# AutoType-JS-Example
Extending AutoType.js to automatically typing text over multiple lines
You can simply add more or less characters to each line, all you need to do is edit the timing settings inside of the js file for each function depending on the amount of characters per line.


#### AutoType.js

```js
function autoTypeh1(elementClass, typingSpeed){
	
  var animateH1Text = $(elementClass);
  
  animateH1Text.css({
    "position": "relative",
    "display": "inline-block"
  });
  
  animateH1Text.prepend('<div class="h1cursor" style="right: initial; left:0;"></div>');
  animateH1Text = animateH1Text.find("h1");
  
  var text = animateH1Text.text().trim().split('');
  var amntOfChars = text.length;
  var newString = "";
  animateH1Text.text("|");
  
  setTimeout(function(){
    animateH1Text.css("opacity",1); // add animation ease here
    animateH1Text.prev().removeAttr("style");
    animateH1Text.text("");
	
    for(var i = 0; i < amntOfChars; i++){
      (function(i,char){
        setTimeout(function() {        
          newString += char;
          animateH1Text.text(newString);
        },i*typingSpeed);
      })(i+1,text[i]);
    }
  },2000);
}

$(document).ready(function(){ 
  autoTypeh1(".typeH1-js",120);  
});

function autoTypeh2(elementClass, typingSpeed){
	
  var animateH2Text = $(elementClass);
  
  animateH2Text.css({
    "position": "relative",
    "display": "inline-block"
  });
  
  animateH2Text.prepend('<div class="h2cursor" style="right: initial; left:0;"></div>');
  animateH2Text = animateH2Text.find("h2");
  
  var text = animateH2Text.text().trim().split('');
  var amntOfChars = text.length;
  var newString = "";
  animateH2Text.text("|");
  
  setTimeout(function(){
    animateH2Text.css("opacity",1); // add animation ease here
    animateH2Text.prev().removeAttr("style");
    animateH2Text.text("");
	// Hide prev cursors
	$(".h1cursor").hide();
	
    for(var i = 0; i < amntOfChars; i++){
      (function(i,char){
        setTimeout(function() {        
          newString += char;
          animateH2Text.text(newString);
        },i*typingSpeed);
      })(i+1,text[i]);
    }
  },6500);
}

$(document).ready(function(){ 
  autoTypeh2(".typeH2-js",120);
  $(".h2cursor").hide();  
});

function autoTypeh3(elementClass, typingSpeed){
	
  var animateH3Text = $(elementClass);
  
  animateH3Text.css({
    "position": "relative",
    "display": "inline-block"
  });
  
  animateH3Text.prepend('<div class="h3cursor" style="right: initial; left:0;"></div>');
  animateH3Text = animateH3Text.find("h3");
  
  var text = animateH3Text.text().trim().split('');
  var amntOfChars = text.length;
  var newString = "";
  animateH3Text.text("|");
  
  setTimeout(function(){
    animateH3Text.css("opacity",1); // add animation ease here
    animateH3Text.prev().removeAttr("style");
    animateH3Text.text("");
	// Hide prev cursors
	$(".h2cursor").hide();
	
    for(var i = 0; i < amntOfChars; i++){
      (function(i,char){
        setTimeout(function() {        
          newString += char;
          animateH3Text.text(newString);
        },i*typingSpeed);
      })(i+1,text[i]);
    }
  },12000);
}

$(document).ready(function(){ 
  autoTypeh3(".typeH3-js",100);  
  $(".h3cursor").hide();
});
```
