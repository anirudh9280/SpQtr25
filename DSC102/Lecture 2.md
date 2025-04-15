# Key Parts of Computer Hardware
## Processor (GPU, CPU, etc)
- hardware to orchestrate and execute instructions to manipulate data as specified by the program 
## Main Memory (Dynamic Random Access Memory)
- hardware to store data and programs that allows very fast location/retrieval; byte-level addressing scheme
## Disk (secondary/persistent storage)
- similar to memory but persistent, slower, and higher capacity / cost ratio; various addressing schemes

## Network (interface controller NIC)
- hardware to send data / to retrieve data over network of interconnected computers/devices

# Key Aspects of Software 
## Instruction 
- a command understood by hardware; finite vocab for a processor
- Instruction Set Architecture (ISA); bridge between software and hardware
## Program (code)
- a human-readable formal language to write programs; at a much higher level of abstraction than ISA
## Application Programming Interface (API)
- a set of functions ("interface") exposed by a program/set of programs for use by humans/other programs
## Data 
- digital representation of information that is stored, processed, displayed, retrieved, or sent by a program 
## Firmware 
- read-only programs "baked into" a device to offer hardware control functionalities
## Operating Systems (OS)
- collection of interrelated programs that work as an intermediary platform/service to enable application software to use hardware more effectively/easily
- Linux, Windows, macOS
## Application Software
- a program or a collection of interrelated programs to manipulate data, typically designed for human use
- Examples: Excel, Chrome, PostgreSQL

# Digital Representation of Data
## Bits: All digital data, Sequences of 0 and 1
- physics, electronic implementation
- easy to store with bistable elements, e.g., high-low/off-on electromagnetism on disk
- reliably transmitted on noisy and inaccurate wires
- expressive and inefficient\
- ![[Pasted image 20250414195928.png]]
## Data Type: first layer of abstraction to interpret bit sequence with a human-understandable category of information
- Examples: Boolean, Byte, Integer, float, character, or string
## Data Structure: second layer of abstraction to organize multiple instance of the same or varied data types into a more complex structure
- - - 
- the size and interpretation of a data type depends on PL
- a byte is 8 bits and is the basic unit of data types
### Boolean
- Y/N or T/F
- just one bit is needed 
### Integer
- typically 4 bytes

## Question: How many unique data items can be represented by 3 bytes? 
- given k bits, we can represent $2^k$ unique data items
- $3 \text{ bytes }=24 \text{ bits} \rightarrow 2^{24}\text{ items}$
## Question: How many bits are needed to distinguish 97 data items?
- for k unique items, we can do $\lceil log_{2}() \rceil$
- $97 \rightarrow 128=2^7 = 7\text{ bits}$
## Question: How to convert from decimal to binary representation?
1. Given a decimal n 
	1. If n is a power of 2 say $2^k$, put 1 bit at position k; if k = 0, stop; else pad with trailing 0s till position 0
	2. if n is not a power of 2, identify the power of 2 just below n (say $2^k$); # bits is then k; and we put 1 at position k 
2. Reset n as $n - 2^k$; return to steps 1-2
3. Fill remaining positions in between with 0s
![[Pasted image 20250414201053.png]]

