conda activate <env>

Enable system proxy

git clone https://github.com/comfyanonymous/ComfyUI.git

fish_pip torch torchvision torchaudio --extra-index-url https://download.pytorch.org/whl/cu124

cd ComfyUI

fish_pip -r requirements.txt

python main.py --listen giove-hmi.col.st.com

## Install comfyui-manager

cd custom_nodes

git clone https://github.com/ltdrdata/ComfyUI-Manager.git

If a custom node cannot be installed:
- go to github repo of the node
- git clone to custom_nodes directory
- cd to that node directory
- fish_pip -r requirements.txt

