### if you want to make default value, do it like below
function greet(name, greeting){ <br>
   name = (typeof name!=='undefined') ? name : 'Student'; <br>
   greeting = (typeof greeting !== 'undefined')? greeting : 'Welcome'; <br>
   
   return  `${greeting} ${name}!`; <br>
  } <br> <br>
  
  greet(); <br>
  greet('James'); <br>
  greet('Richard', 'Howdy'); <br>

### more simple 
function greet(name = 'Student', greeting = 'Welcome') { <br>
  return `${greeting} ${name}!`; <br>
} <br> <br>

greet(); // Welcome Student! <br>
greet('James'); // Welcome James! <br>
greet('Richard', 'Howdy'); // Howdy Richard! <br>

### Defaults and destructuring arrays
function createGrid([width = 5, height = 5]) { <br>
  return `Generates a ${width} x ${height} grid`; <br>
} <br> <br>

createGrid([]); // Generates a 5 x 5 grid <br>
createGrid([2]); // Generates a 2 x 5 grid <br>
createGrid([2, 3]); // Generates a 2 x 3 grid <br>
createGrid([undefined, 3]); // Generates a 5 x 3 grid <br>

### when call createGrid(), it will be occur error
function createGrid([width = 5, height = 5] = []) { <br>
  return `Generates a ${width} x ${height} grid`; <br>
} <br><br>
createGrid(); // Generates a 5 x 5 grid
