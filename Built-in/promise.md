#### Promise
new Promise(function (resolve, reject) {<br>
    window.setTimeout(function createSundae(flavor = 'chocolate') {<br>
        const sundae = {};<br>
        // request ice cream <br>
        // get cone <br>
        // warm up ice cream scoop <br>
        // scoop generous portion into cone! <br>
    }, Math.random() * 2000); <br>
}); <br>

resolve ->successful <br>
reject  ->couldn't be completed

#### .then()
##### Two function of .then()
1. the function to run if the request completed successfully <br>
2. the function to run if the request failed to complete <br>

mySundae.then(function(sundae) { -----(1)<br>
    console.log(`Time to eat my delicious ${sundae}`); <br>
}, function(msg) {    ------(2) <br>
    console.log(msg); <br>
    self.goCry(); // not a real method <br>
}); <br>
if successful, it calls (1), if unsuccessful, it calls (2) 
