![[Pasted image 20230227100722.png]]


- ### UART - Asynchronos - no CLK
	- transfer speed and length are to be sent to receiver .
	- only one signal line
	- point to point transfer

- ### I2C - Synchronos - uses CLK
	- SDA - data signal 
	- SCL - clock signal
	- transfer speed and length are to be sent to receiver .
	- send data to multiple slaves at a time using receiver slave addresses.
- ### Serial Peripheral Interface (SPI) - uses CLK
	- SCLK - clock
	- MISO - Master in slave out
	- MOSI - Master out slave in 
	- SS - Slave select
	- Full Duplex (two way communication simultaneously)
