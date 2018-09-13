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

### Defaults and destructuring arrays
function createGrid([width = 5, height = 5]) {
  return `Generates a ${width} x ${height} grid`;
}

createGrid([]); // Generates a 5 x 5 grid
createGrid([2]); // Generates a 2 x 5 grid
createGrid([2, 3]); // Generates a 2 x 3 grid
createGrid([undefined, 3]); // Generates a 5 x 3 grid

### when call createGrid(), it will be occur error
function createGrid([width = 5, height = 5] = []) {
  return `Generates a ${width} x ${height} grid`;
}
createGrid(); // Generates a 5 x 5 grid
