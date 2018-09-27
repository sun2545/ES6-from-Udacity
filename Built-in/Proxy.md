#### Proxy
const proxyObj = new Proxy({age: 5, height: 4}, { <br>
    get(targetObj, property) { <br>
        console.log(`getting the ${property} property`); <br>
        console.log(targetObj[property]); <br>
    } <br>
});<br><br>

proxyObj.age; // logs 'getting the age property' & 5 <br>
proxyObj.height; // logs 'getting the height property' & 4 <br>
