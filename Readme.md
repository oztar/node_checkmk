## Check MK
check_MK is a library to monitor your application internally from the server
 monitoring checkmk server.

By default the library generates two services:
* check_ml
* status

Using function "addService" you can create more services.

Once the library is assembled, adding a new host in monitoring checkmk server.

## Intall

...
npm install checkmk
...


## Usage


let check = require('checkMK');

let options = {
    host:  '10.10.1.20'    
}

check.createServer(options);

check.addService('test',{
    name: 'test',
    ok: 'Test- Test is OK',
    warning:  'O no, i have a problem',
    critical: ' Faltal error ',
    counter: {	
	counter1 : '9;2;3;0;10',
	counter2 : '1;2;7'
    }
    
})

...
check.updateService('test',{
	counter1 : 1,
	counter2 : 2
    });
...