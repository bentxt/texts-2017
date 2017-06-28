# standalone scheme2js


How to make a standalone scheme2js version from the hop package.

## create 'scheme2js' binary

- in 'hop' run ./configure, then 'make'

- cd to scheme2js/o

- cp ../*.s*  ( .scm, and .sch files)

- compile with  something like :  

   $ bigloo [args] objectfiles.o -o scheme2js

( have a look at the attached file 'build_scheme2js.sh')


## work with 'scheme2js'

compile from scheme to javascript with:

   $ scheme2js -o test.js test.scm


in order to run test.js you need 'runtime.js' 



### runtime-cli.js

runtime.js is also part of 'hop' and contains the libray to run the compiled js files. 

runtime-cli.js  is special version that runs in node (a browserless context).

All window references are removed.


### scm2js 

This script manages the transpiling with scheme2js and the inclusion of the runtime and finally the execution with nodejs.



files: 

* [build_scheme2js.sh](build_scheme2js.sh)
* [runtime-cli.js](runtime-cli.js)
* [scm2js](scm2js)


