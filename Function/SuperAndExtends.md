### subclasses with ES6
class Tree { <br>
  constructor(size = '10', leaves = {spring: 'green', summer: 'green', fall: 'orange', winter: null}) {<br>
    this.size = size;<br>
    this.leaves = leaves;<br>
    this.leafColor = null;<br>
  }<br>

  changeSeason(season) {<br>
    this.leafColor = this.leaves[season];<br><br>
    if (season === 'spring') {<br>
      this.size += 1;<br>
    }}}<br>
 
class Maple extends Tree {<br>
  constructor(syrupQty = 15, size, leaves) {<br>
    super(size, leaves);<br>
    this.syrupQty = syrupQty;<br>
  }<br>

  changeSeason(season) {<br>
    super.changeSeason(season);<br>
    if (season === 'spring') {<br>
      this.syrupQty += 1;<br>
    }<br>
  }<br>

  gatherSyrup() {<br>
    this.syrupQty -= 3;<br>
  }<br>
}<br>

const myMaple = new Maple(15, 5);<br>
myMaple.changeSeason('fall');<br>
myMaple.gatherSyrup();<br>
myMaple.changeSeason('spring');<br>

### Compared to ES6 subclasses
function Tree(size, leaves) {<br>
  this.size = (typeof size === "undefined")? 10 : size;<br>
  const defaultLeaves = {spring: 'green', summer: 'green', fall: 'orange', winter: null};<br>
  this.leaves = (typeof leaves === "undefined")?  defaultLeaves : leaves;<br>
  this.leafColor;<br>
}<br>

Tree.prototype.changeSeason = function(season) {<br>
  this.leafColor = this.leaves[season];<br>
  if (season === 'spring') {<br>
    this.size += 1;<br>
  }<br>
}<br>

function Maple (syrupQty, size, leaves) {<br>
  Tree.call(this, size, leaves);<br>
  this.syrupQty = (typeof syrupQty === "undefined")? 15 : syrupQty;<br>
}<br>

Maple.prototype = Object.create(Tree.prototype);<br>
Maple.prototype.constructor = Maple;<br>

Maple.prototype.changeSeason = function(season) {<br>
  Tree.prototype.changeSeason.call(this, season);<br>
  if (season === 'spring') {<br>
    this.syrupQty += 1;<br>
  }<br>
}<br>

Maple.prototype.gatherSyrup = function() {<br>
  this.syrupQty -= 3;<br>
}

const myMaple = new Maple(15, 5);<br>
myMaple.changeSeason('fall');<br>
myMaple.gatherSyrup();<br>
myMaple.changeSeason('spring');<br>
