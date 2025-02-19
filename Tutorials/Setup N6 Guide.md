- Add STM32_Programmer_CLI.exe's path to system path

- `cd C:\ST`

- `git clone https://github.com/STMicroelectronics/stm32ai-modelzoo-services.git`

- `git clone https://github.com/STMicroelectronics/stm32ai-modelzoo.git`

- `cd C:\ST\stm32ai-modelzoo-services

- `python -m venv st_zoo`

- `st_zoo\Scripts\activate.bat`

- `pip install -r requirements.txt`

- Set the Boot 0 and Boot 1 switches to high

- Plug the power jumper to STLink

- Plug the USB-C to USB-C to board and computer (USB-A to USB-C has power delivery issues)
---
## Method 1
- `cd C:\ST\stm32ai-modelzoo-services\<application>\src\`

- Change the YAML file for each application
	- set the STEdgeAI path
		- `path_to_stedgeai: C:/ST/STEdgeAI/Utilities/windows/stedgeai.exe`
	- set the STM32CUBEIDE path
		- `path_to_cubeIDE: C:/ST/STM32CubeIDE_1.17.0/STM32CubeIDE/stm32cubeide.exe`
	- set the model path
		- `../../../stm32ai-modelzoo/<application>/<model_folder>/..`

- `python stm32ai_main.py --config-path ./config_file_examples/ --config-name deployment_n6_st_movenet_lightning_heatmaps_config.yaml`

---
## Method 2
- Configure the deploy_example.ps1 script to your system

- `In powershell`

- `cd C:\ST`

- `.\deploy_example.ps1`

---

- Set the Boot 0 and Boot 1 switches to low and press reset