## Software
Software refers to programs: the instructions that the computer executes to perform tasks. Embedded systems contain limited instruction sets and only perform specific tasks, while general-purpose computer can run a range of tasks.
#### System software
System software controls the hardware of a computer system. This includes:
- **Operating systems**, which manages hardware resources such as processor time and memory, provides a platform for application software to run on, and a way for application software to interact with hardware through APIs
- **Program translators** (compilers, interpreters, assemblers) convert source code into machine code
- **Library programs**, which are collections of resources used to develop software, including pre-written code and subroutines
- **Utility programs** that perform maintenance and housekeeping tasks (disk defragmentation, antivirus, compression)
#### Application software
Application software is designed to perform user-facing tasks. This includes web browsers, word processors, video editors, etc. Application software can be categorised into general purpose (used for a variety of tasks), special purpose (only used for one specific task), or bespoke (developed for the client's specific requirements).


## Hardware
Hardware is the physical components of a computer system. The 'three-box model', which describes a von Neumann machine, consists of a processor, main memory, and I/O controllers, all linked by a system bus. Computers also have additional hardware (peripherals), which include secondary storage, and input/output devices.
#### Von Neumann and Harvard
In the **von Neumann** architecture, instructions and data are stored together in main memory; they are in fact indistinguishable. von Neumann is used extensively in general purpose computing systems. In the **Harvard** architecture, instructions and data are stored in separate memory spaces accessed by different buses. The Harvard architecture is used extensively in embedded systems such as digital signal processing (DSP).
###### Stored program concept
Machine code instructions stored in main memory are fetched and executed serially by a processor that performs arithmetic and logical operations.

#### Processor
The processor executes the instructions that allow the computer to perform tasks. It contains:
- The **control unit**, which contains the clock and sends control signals to control the execution of instructions
- The **ALU** (arithmetic logic unit), which performs arithmetic operations (addition, multiplication) and logical operations (AND, NOT)
- Registers, which are very small but fast to access places of memory in the processor. There are general-purpose and dedicated registers.
- Cache, which stores frequently accessed data and instructions
###### Registers
Dedicated registers include:
- The **program counter** (PC), which contains the address of the next instruction to be executed.
- The **current instruction register** (CIR), which contains the current instruction being executed.
- The **memory address register** (MAR), which contains the address of the memory location for a read/write instruction.
- The **memory buffer register** (MBR), which contains data that is being written to or read from memory.
- The **status register** (SR), which contains bits that are set depending on the result of an instruction, including:
	- The zero flag, set if the last operation resulted in zero
	- The carry flag, set if the last operation created a carry
	- The sign or negative flag, set depending on the sign of the result of the last operation
	- The overflow flag, set if integer overflow occurred. 
###### Fetch-execute cycle
**Fetch**
1. The address of the next instruction is copied from the PC to the MAR, and sent through the address bus to the main memory.
2. The next instruction is retrieved from main memory and sent along the data bus to the MBR. The PC is incremented so it contains the address of the next instruction.
3. The MBR is copied to the CIR.
**Decode**
4. The instruction in the CIR is decoded. It is split into opcode and operand. The control unit uses the opcode to determine the type of instruction and what hardware should execute it. Additional data is fetched from memory if necessary and passed to registers.
**Execute**
5. The instruction is executed, using the ALU if needed.

###### Factors affecting processor performance
**Number of cores**
In a traditional computer, instructions are fetched and executed one at a time. Modern computers have processors with multiple cores, which can theoretically independently execute instructions simultaneously, each running their own fetch-execute cycle. However, software needs to be written such that it can use multiple processor cores.

**Amount and type of cache**
Cache is a small amount of very fast memory inside the processor. When an instruction or piece of data is fetched from main memory, it is copied from the cache, so that if the same instruction or data is needed again, it can be fetched from cache, which is faster than accessing main memory. Processors typically contains three levels of cache, ranging from L1, which is fastest but the smallest, to L3.

**Clock speed**
All processor activities start on a clock pulse. The faster the clock speed, the more instructions that can be executed per second. Typical modern computers have clock speeds around 3 GHz.

**Bus width**
The width of the data bus affects how many bits are processed simultaneously. Therefore, a larger data bus width can reduce the number of instructions needed to process a given amount of data, increasing performance e.g. a 32 bit data bus only requires one memory read to read 32 bits while a 16 bit bus requires 2.

**Interrupts**
Interrupts are signals sent by a software program or hardware device to the processor. For example, a hardware issue could cause an interrupt. When the CPU receives an interrupt, it stops execution of the current program and calls an **Interrupt Service Routine** (ISR) to process the interrupt.

When an interrupt occurs: 
- The current fetch-execute cycle is completed
- The program counter and other registers are stored in memory where they can be restored from later
- The source of the interrupt is identified and interrupts of a lower priority are disabled 
- The program counter is loaded with the start address of the interrupt service routine and the interrupt service routine is executed 
- The saved values for the registers other than the program counter are restored to the processor registers 
- Interrupts are re-enabled
- The program counter is restored to point to the next instruction to be executed
- The fetch-execute cycle continues normally
#### Buses
A bus is a set of parallel wires that connects different components of a computer.
###### Control bus
The control bus is bi-directional and transmits command, timing, and status information between system components. Control lines include:
- Memory write: data on the data bus is written to the address in memory given by the address bus
- Memory read: data is read from the address in memory given by the address bus, and placed onto the data bus.
- Clock: synchronises components.
###### Data bus
The data bus typically consists of 8, 16, 32, or 64 lines, and provides a bi-directional path for transmitting data and instructions between system components. The width of the data bus is extremely important for system performance, as it determines how much data is typically processed in one instruction.
###### Address bus
Memory is divided into words, and each word is given an address. The address bus is used by the processor to select which address to read / write in memory. The width of the address bus determines the maximum memory capacity of the system.

## Machine code
#### Addressing modes
**Immediate addressing**: the operand is the datum.
**Direct addressing**: the operand is the memory address of the datum (could be main memory address or a register).

## Secondary Storage
#### Hard disk
A hard disk drive contains multiple rapidly spinning platters with a magnetic coating. Each platter consists of concentric tracks and radially segmented sectors. Each platter has a read-write head, which moves radially to access different tracks. To read and write data, the read-write head moves to the desired sector. To read, the head uses an electromagnet to change the magnetic polarity of specific areas in the sector, with one polarity representing a binary 1 and the other representing a 0. To write, an electromagnetic records the changing polarity and converts this to a binary signal. 
#### Solid-state disk (SSD)
A SSD has NAND flash memory and a controller that manages pages, and blocks and complexities of writing. NAND flash memory is based on floating gate transistors that trap and store charge. A block is made up of many pages. Pages cannot be overwritten - the page has to be erased before it can be written to, but technology requires the whole block to be erased. SSDs have lower latency and faster transfer speeds than a magnetic disk drive.
#### Optical disk
To write data to an optical disk, the disk is rotated in a disk drive. There is a single spiral track on the disk. A laser inside the drive moves to access different areas of the track, physically burning a pattern on the surface coating of the disk. To read data from an optical disk, the same process is used except with a weaker laser where the laser beam reflects off the surface of the disk. The changes between areas of different reflectance (lands and pits) is detected by a photodiode, and the signal is processed to become a digital binary signal. 

## Input / output devices
#### Barcode reader
A barcode reader has a light source that illuminates the bars. The white and black bars reflect light differently, which is converted to an electrical signal by a sensor. The signal is decoded to obtain the barcode's store data. 
#### Digital camera
A digital camera has a camera sensor. When the shutter is opened, light falls onto the camera sensor, which has a matrix of photodioides (typically CCD or CMOS). The light causes an amount of charge to build in each photosensor proportional to the brightness of light, which is then sensed and converted into a digital value by an ADC (analogue to digital converter). Each cell is covered by 1 blue, 1 red, and 2 green filters (Bayer filter).  

CCD sensors are used for low-noise applications such as astrophotography. CCD is also used in profession photography where quality is important. CMOS is used in mobile devices where minimising power consumption is important. 
#### Laser printer
There is a photosensitive drum that is negatively charged. A laser scans across the drum through an optical lens and mirror mechanism, turning on and off to apply the bitmap data onto the drum. The laser causes the drum's charge to be neutralised where it scans over. The pattern of charge on the drum surface is an image of the page to be printed. The charged drum is exposed to toner, where the negatively charged areas repel toner, while the neutral areas attract toner. The drum then rolls over a piece of positively charged paper, transferring the toner pattern onto the paper. The toner is then passed through heated rollers to fuse the toner to the paper. 
#### RFID
RFID is a method of identifying items using radio waves. A reader communicates with a transponder in a RFID tag to transmit digital information over radio waves. 

An RFID tag is a microchip with an antenna, which is packaged in a way to be applied to an object. The tag contains a transponder that picks up signals from and transmits signals to a reader. RFID tags can be used without a line of sight.