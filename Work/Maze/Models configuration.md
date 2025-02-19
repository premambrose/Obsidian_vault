- ## Main:
	- Model: 64,32,32,256,128,64,64
	- Policy: CNN
- ## Main2:
	- Model: 64,32,32,256,64,64,64
	- Policy: CNN
- ## Main3:
	- Model: 64,32,32,256,64,64,64
	- Policy: MLP
- ## Main4:
	- Model: 16,32,32,256,64,64,64
	- Policy: CNN



# Model Input size 13x19

- ## Model 1: 3MB
	- 16,32,32,256,128,128

- ## Model_2: 1565KB, 99.03%, 38.7ms
	- 38 - 39ms: on device measured with clock
	- Topology: 16,32,32,128,64,64
	- Total Flash: 1.54 MiB
		- weights: 1.52 MiB
		- Library: 18.70 KiB
	- RAM: 26.99 KiB
	- Final win rate:  **0.99**0340684072754
	- 0.990340684072754 evaluated on  103527  games played
	- nb sample(s)     :   10
	- duration            :   38.701ms by sample (38.678/38.725/0.012)
	- MACC                 :   1883764   
	- cycles/MACC     :   8.22 
	- counter             :   [15,480,488]

- ## Model_3: 1621 KB, 98.38%, 69.14ms
	- Topology: 64,32,32,128,64, 64
	- Total Flash: 1.60 MiB
		- weights: 1.58 MiB
		- Library: 18.70 KiB
	- RAM: 52.30 KiB
	- Final win rate:  **0.98**3844389156354
	- 0.7653683716564993 evaluated on  4262  games played
	- nb sample(s)     :   10
	- duration            :   69.147ms by sample (69.118/69.191/0.021)
	- MACC                 :   3839812
	- cycles/MACC     :   7.20
	- counter              :   [27,658,726]

- ## Model_4: 3053KB, 99.51%, 53.95ms
	- Topology: 16,32,32,256,64,64
	- Total Flash: 3.00 MiB
		- weights: 2.98 MiB
		- Library: 18.70 KiB
	- RAM: 26.99 KiB
	- Final win rate:  **0.99**51588853817703
	- nb sample(s)     :   10
	- duration            :   53.950ms by sample (53.937/53.967/0.010)
	- MACC                 :   2264948
	- cycles/MACC     :   9.53
	- counter              :   [21,579,803]

- ## Model_5: 923KB, 99%, 42.464ms
	- Topology: 64, 32, 16, 128, 128, 64
	- Total Flash: 937.66 KiB
		- weights: 918.95 KiB
		- Library: 18.70 KiB
	- RAM: 52.30 KiB
	- Final win rate:  **0.99**00259325753042
	- 0.9900259325753042 evaluated on  100260  games played
	- nb sample(s)     :   10
	- duration            :   42.464ms by sample (42.441/42.477/0.011)
	- MACC                 :   3245060
	- cycles/MACC     :   5.23
	- counter              :   [16,985,505]

- ## Model_6: 821KB, 99.11%, 22.09ms
	- Topology: 16,32,32,64,64,64
	- Total Flash: 835.64 KiB
		- weights: 816.64 KiB
		- Library: 18.70 KiB
	- RAM: 26.99 KiB
	- Final win rate: 0.991105102113427
	- 0.9911051021134277 evaluated on  112424  games played
	- nb sample(s)    :   10
	- duration        :   22.095ms by sample (22.088/22.098/0.003)
	- macc            :   1693172
	- cycles/MACC     :   5.22
	- counter         :   [8,838,056]
