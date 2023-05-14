# TU;DL

#### A fun project to use the NRF51822 chip
I bought it a few years back and saw it lying around. Why not try a new project?


#### Todo
- Blink LED with SDK every 2s 
- Create 2.54mm board chip
- 

#### Softdevice preparations

Start the GDB server 
`openocd -f /usr/share/openocd/scripts/interface/stlink-v2.cfg -f /usr/share/openocd/scripts/target/nrf51.cfg`

Connect to server and program your hex
```
telnet localhost 4444
reset
halt
nrf51 mass_erase 0
program <path to hex file> verify
```

Serve rejects connections from their program
`nrfjprog --family NRF51 --eraseall --port 3333 --ip 127.0.0.1`


#### Self notes

I would eventually learn that I didn't need Segger Embedded Studio (SES) for deve-
lopment, and I could have simply called a makefile to do the needful. It didn't occur
to me that the SDK was fairly self-content and using SES was uneccessary. Using SES with
SDK v12.3 means you have to configure the IDE options, flags, etc that the compiler would
use [This guy's video](https://www.youtube.com/watch?v=o_9Lmm0SYr8) is good for context.

