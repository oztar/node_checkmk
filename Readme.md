## Check MK
check_MK is a library to monitor your application internally from the server
 monitoring checkmk server.

By default the library generates two services:
* check_ml
* status

Using function "addService" you can create more services.

Once the library is assembled, adding a new host in monitoring checkmk server.

## Install

...
npm install checkmk
...


## Usage


let check = require('checkMK');

let options = {
    host:  '10.10.1.20',
    port: 6556,
    encoding : 'utf8',
    exclusive: true
}

check.createServer(options);

check.addService('test',{
    name: 'test',
    ok: 'Test- Test is OK',
    warning:  'O no, i have a problem',
    critical: ' Faltal error ',
    counter: {	
	counter1 : '9;2;3;0;10',
	counter2 : '1;2;7',
	othername : 1
    }
    
})

...
check.updateService('test',{
	counter1 : 1,
	counter2 : 2,
	othername : 0
    },' value 1 for counter1 and 2 in counter 2 ( other 0)');
...