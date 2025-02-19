
## 1. Generate ISPUAI model

1. Generate a python model and save the model file

2. Open windows wsl and use the commands below

```
ispuai analyze -m $model_path
```

```
ispuai generate -m $model_path -o $output_path
```

```
\cp $output_path/* "/mnt/c/Users/ambrosep/OneDrive - STMicroelectronics/Projects/Door/st-mems-ispu/tutorials/ispuai/ispu/"
```

4. Open the ../../ispuai/ispu/eclipse/.project in STM32CubeIDE

5. Program the ISPU code and build project in STM32CubeIDE

6. Binary for datalogger application will be saved ../ispuai/ispu/eclipse/release/ispu.ucf



## 2. Datalogger application for STWINBX1

1. Open the following folder and program the STWINBX1 and flash the firmware.
```
C:\Users\ambrosep\OneDrive - STMicroelectronics\Projects\Door\STM32CubeFunctionPack_DATALOG2_V1.1.0\Projects\STWIN.box\Applications\DATALOG2
```


## 3. Start the python Datalog GUI Application

```
cd C:\Users\ambrosep\OneDrive - STMicroelectronics\Projects\Door\STM32CubeFunctionPack_DATALOG2_V1.1.0\Utilities\HSDPython_SDK\examples
```

```
conda activate door
```


```
python hsdatalog_GUI.py
```

1. Connect the STWINBX1 to the computer and click "connect" in the GUI application

2. Select the ISPU sensor and upload the ucf file from the following location:
```
"/mnt/c/Users/ambrosep/OneDrive - STMicroelectronics/Projects/Door/st-mems-ispu/tutorials/ispuai/ispu/eclipse/release/"
```

3. Modify and upload the json file describing how to interpret output from the ISPU.

4. Click play and click the gear icon next to the ispu output plot.

5. Upload the json file again here to get the right output in the graph