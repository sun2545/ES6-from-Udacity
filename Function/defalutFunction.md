### if you want to make default value, do it like below
function greet(name, greeting){
   name = (typeof name!=='undefined') ? name : 'Student';
   greeting = (typeof greeting !== 'undefined')? greeting : 'Welcome';
   
   return  `${greeting} ${name}!`;
  }
  
  greet();
  greet('James');
  greet('Richard', 'Howdy');

### more simple 
function greet(name = 'Student', greeting = 'Welcome') {
  return `${greeting} ${name}!`;
}

greet(); // Welcome Student!
greet('James'); // Welcome James!
greet('Richard', 'Howdy'); // Howdy Richard!
