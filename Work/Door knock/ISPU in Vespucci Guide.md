### Guide to use ISPU.AI and ISPU toolchain in Vespucci

1. Copy your python and ISPU project files into ../../workspace/<userID>/models/door_knock_detector/experiments/fully_connected_layers/application folder
2. Open the python project and run the training in Vespucci:
    - Either using the GUI
    - or using the terminal
3. Generate and save a supported python model file
4. To generate ISPU code for the generated model, open Terminal and use the commands below

To change directory to where the model is saved
```
cd ../../workspace/<userID>/models/door_knock_detector/experiments/fully_connected_layers/application
```

To analyze the generated model with ISPU.AI tool
```
ispuai analyze -m $model_path
```

To validate the same
```
ispuai validate -m $model_path
```

To generate c code for the model with IPSU.AI
```
ispuai generate -m $model_path -o $output_path
```

To see the help and other available options
```
ispuai --help
```

5. Copy the generated AI code(contents of the folder named "ispuai_output" by default) to the ISPU project root folder
6. Program the ISPU as per the project and once completed, in the terminal:
```
cd ../../workspace/<userID>/models/door_knock_detector/experiments/fully_connected_layers/application/ISPU_Project/ispu
cd make && make
```
7. This can also be done in local with STM32CubeIDE by opening the ../../../ISPU_Project/ispu/eclipse/.project file

8. Binaries are saved in the following locaiton as ../../../ISPU_Project/ispu/eclipse/release or ../../../ISPU_Project/ispu/make/bin
