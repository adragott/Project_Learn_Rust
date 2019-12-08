# Rust: Embedded

I'm going to be using a lot of different hardware for this learning project. Here are the first 5 mcus I'll be working with:

 - atsamd21j18a     (SAMD21 XPLAINED)
 - atsamd21g18a     (Metro M0)
 - stm32f303vct6    (STM32F3DISCOVERY)
 - stm32l432kc      (STM32 Nucleo-32)
 - atsame54p20a     (SAME54 XPLAINED)

I am using all of these at first so I can just get more experience with hardware other than the samd series of mcus. It is my crutch, and it's bad to have a crutch like this.

# Knowing your hardware

We need some knowledge of our hardware in order to get going. I think these should be prerequisites before writing any code:

 - ARM Core
 - Does it have an FPU? Can it have an FPU?
 - How much memory does a device have? What kind? Where is it mapped to?
 - What does its setup look like as far as serial options? (UART, SPI, I2C)
 - Does the device offer individual modules dedicated to certain protocols, or does it do some complex multiplexing with hardware that allows us to pick and choose which protocols we would like to us? An example is that the samd21 doesn't have individual U(S)ARTs, I2Cs, or SPIs. It has SERCOM ports we can configure to do either of those three, which is extremely convenient and is one of the reasons why I love that chip. Other chips have other forms of this. The samg55 has flexcoms, which are similar but not as good imo. 

Knowing these things allows us to start understanding what we're doing, so I'm going to map some of that our here. I've included datasheets in the doc folder, but you can just as easily google these.

Note: Consider Flash memory your program memory. Consider SRAM your data memory.
Second Note: I am far more comfortable with microchip (atmel) mcus. I may make some mistakes with the stm32 line. Forgive me.

### ATSAMD21J18A
```
Core:               Cortex-M0+
Flash:              256 KB 
RAM:                32 KB SRAM
Pin Count:          64
Package:            TQFP

Memory Locations: (Section 10.1 of Datasheet)
Flash Address:       0x00000000
Flash RWW Address:   0x00400000 (More on this later)
RAM Address:         0x20000000
IOBUS:               0x60000000
NVM User Row:        0x00804000

Serial Setup:
x6 SERCOM Modules
```

I'm skipping the peripheral busses because we likely won't need them for this.

### ATSAMD21G18A
```
Core:               Cortex-M0+
Flash:              256 KB
RAM:                32 KB SRAM
Pin Count:          48
Package:            TQFP

Memory Locations: (Section 10.1 of Datasheet)
Flash Address:       0x00000000
Flash RWW Address:   0x00400000 (More on this later)
RAM Address:         0x20000000
IOBUS:               0x60000000
NVM User Row:        0x00804000

Serial Setup:
x6 SERCOM Modules
```
### ATSAME54P20A
```
Core:               Cortex-M4F
Flash:              1MB ECC
RAM:                256 KB SRAM (w/128KB ECC Option?? Need to check this)
Pin Count:          128
Package:            TQFP

Memory Locations:   (Physical Memory Map Section 9.2)
Flash Address:      0x00000000
SRAM Address:       0x20000000
Backup SRAM:        0x47000000  (Need to find out what this is for)
NVM User Page:      0x00804000

Serial Setup:
x6 SERCOM Modules
```

### STM32L432KC
```
Core: Cortex-M4F

```

### STM32F303VCT6
```
Core: Cortex-M4F

```