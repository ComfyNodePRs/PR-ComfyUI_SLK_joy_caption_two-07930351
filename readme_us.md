# JoyCaptionAlpha Two for ComfyUI
English | [中文](./readme.md)
## Recent changes
* [2024-10-12] v0.0.1: Basic implementation of [JoyCaptionAlpha Two](https://huggingface.co/spaces/fancyfeast/joy-caption-alpha-two) on ComfyUI is completed.


## Implementation of JoyCaptionAlpha Two on ComfyUI

Referred to [Comfyui_CXH_joy_caption](https://github.com/StartHua/Comfyui_CXH_joy_caption) and [JoyCaptionAlpha Two](https://huggingface.co/spaces/fancyfeast/joy-caption-alpha-two).

Refer to the example workflow in examples/workflow.png:
![image](./examples/workflow.png)

### Dependency Installation

1. Download and clone the repository to the custom_nodes subfolder.
```
cd custom_nodes
git clone https://github.com/EvilBT/ComfyUI_SLK_joy_caption_two.git
```
2. Install related dependencies:
```
pip install -r ComfyUI_SLK_joy_caption_two\requirements.txt
```
3. Download related models.
4. Restart ComfyUI.

### Downloading Related Models
The following "models" directory refers to the models folder under the ComfyUI root directory.

#### 1. google/siglip-so400m-patch14-384:

International: [google/siglip-so400m-patch14-384](https://huggingface.co/google/siglip-so400m-patch14-384)

China: [hf/google/siglip-so400m-patch14-384](https://hf-mirror.com/google/siglip-so400m-patch14-384)

It will be downloaded automatically. You can also manually download the entire repository and copy all files inside siglip-so400m-patch14-384 to `models/clip/siglip-so400m-patch14-384`.
![image](./examples/clip.png)

#### 2. Llama 3.1-8B Model Download

Two versions are supported:

* **unsloth/Meta-Llama-3.1-8B-Instruct-bnb-4bit:** This version utilizes 4-bit quantization (bnb) and is ideal for users with limited VRAM. This is the version I personally use and recommend, especially for 8GB VRAM environments. 

* **meta-llama/Meta-Llama-3.1-8B:** This is the standard, unquantized version of the model. I have not tested it extensively, but you are welcome to try it out.

Both versions will be downloaded automatically by the program if they are not found, but you can also download them manually from the links below:

**2.1 unsloth/Meta-Llama-3.1-8B-Instruct-bnb-4bit**

* **International:** [unsloth/Meta-Llama-3.1-8B-Instruct-bnb-4bit](https://huggingface.co/unsloth/Meta-Llama-3.1-8B-Instruct-bnb-4bit)
* **China:** [hf/unsloth/Meta-Llama-3.1-8B-Instruct-bnb-4bit](https://hf-mirror.com/unsloth/Meta-Llama-3.1-8B-Instruct-bnb-4bit)

After downloading, copy the entire contents of the folder to `models\LLM\Meta-Llama-3.1-8B-Instruct-bnb-4bit`.

**2.2 meta-llama/Meta-Llama-3.1-8B**

* **International:** [meta-llama/Meta-Llama-3.1-8B](https://huggingface.co/meta-llama/Llama-3.1-8B)
* **China:** [hf/meta-llama/Meta-Llama-3.1-8B](https://hf-mirror.com/meta-llama/Llama-3.1-8B)

After downloading, copy the entire contents of the folder to `models\LLM\Meta-Llama-3.1-8B`.

![image](./examples/Llama3.1-8b.png)

#### 3. Joy-Caption-alpha-two Model Download (must be downloaded manually)

Download and copy all the contents of the `cgrkzexw-599808` folder under [Joy-Caption-alpha-two](https://huggingface.co/spaces/fancyfeast/joy-caption-alpha-two/tree/main) to `models/Joy_caption_two`.
![image](./examples/joy_caption.png)

### After restarting ComfyUI, you can add and use it. Refer to the following images for details:
![image](./examples/workflow.png)
![image](./examples/workflow_flux.png)

### Others

If you have installed the [AIGODLIKE-ComfyUI-Translation](https://github.com/AIGODLIKE/AIGODLIKE-ComfyUI-Translation) language pack plugin, you can copy the Chinese translation under the `translation` folder to the corresponding language pack path, and restart to use the Chinese version.
Copy `translation/zh-CN/Nodes/Comfyui_SLK_joy_caption_two.json` to the directory: `AIGODLIKE-ComfyUI-Translation\zh-CN\Nodes`.

You can open an issue to ask me if you have any questions. It has not been fully tested, I am using an 8G VRAM environment.