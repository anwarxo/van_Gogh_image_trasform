<div align="left">

# ComfyUI
**The most powerful and modular diffusion model GUI and backend.**

## Introduction
ComfyUI is a powerful and modular diffusion model GUI and backend that allows you to design advanced Stable Diffusion workflows using a simple graph/node-based interface. This project aims to demonstrate how you can transform images into Van Gogh-style artwork using ComfyUI, Stable Diffusion, and ControlNet.

With this guide, you'll be able to:
- Set up ComfyUI on your local machine.
- Download and integrate Stable Diffusion models.
- Create and execute workflows for image style transformation.


[matrix-shield]: https://img.shields.io/badge/Matrix-000000?style=flat&logo=matrix&logoColor=white
[matrix-url]: https://app.element.io/#/room/%23comfyui_space%3Amatrix.org
[website-shield]: https://img.shields.io/badge/ComfyOrg-4285F4?style=flat
[website-url]: https://www.comfy.org/
<!-- Workaround to display total user from https://github.com/badges/shields/issues/4500#issuecomment-2060079995 -->
[discord-shield]: https://img.shields.io/badge/dynamic/json?url=https%3A%2F%2Fdiscord.com%2Fapi%2Finvites%2Fcomfyorg%3Fwith_counts%3Dtrue&query=%24.approximate_member_count&logo=discord&logoColor=white&label=Discord&color=green&suffix=%20total
[discord-url]: https://www.comfy.org/discord

[github-release-shield]: https://img.shields.io/github/v/release/comfyanonymous/ComfyUI?style=flat&sort=semver
[github-release-link]: https://github.com/comfyanonymous/ComfyUI/releases
[github-release-date-shield]: https://img.shields.io/github/release-date/comfyanonymous/ComfyUI?style=flat
[github-downloads-shield]: https://img.shields.io/github/downloads/comfyanonymous/ComfyUI/total?style=flat
[github-downloads-latest-shield]: https://img.shields.io/github/downloads/comfyanonymous/ComfyUI/latest/total?style=flat&label=downloads%40latest
[github-downloads-link]: https://github.com/comfyanonymous/ComfyUI/releases



This ui will let you design and execute advanced stable diffusion pipelines using a graph/nodes/flowchart based interface. For some workflow examples and see what ComfyUI can do you can check out:
### [ComfyUI Examples](https://comfyanonymous.github.io/ComfyUI_examples/)

### [Installing ComfyUI](#installing)



# Installing


## Installing ComfyUI

To install ComfyUI, follow these steps:

1. Open your terminal and run the following command to clone the ComfyUI repository and run the application:

   ```bash
   git clone https://github.com/comfyanonymous/ComfyUI.git
   cd ComfyUI
   pip install -r requirements.txt
   python main.py
### AMD GPUs (Linux only)
AMD users can install rocm and pytorch with pip if you don't have it already installed, this is the command to install the stable version:

```pip install torch torchvision torchaudio --index-url https://download.pytorch.org/whl/rocm6.1```

This is the command to install the nightly with ROCm 6.2 which might have some performance improvements:

```pip install --pre torch torchvision torchaudio --index-url https://download.pytorch.org/whl/nightly/rocm6.2```

### NVIDIA

Nvidia users should install stable pytorch using this command:

```pip install torch torchvision torchaudio --extra-index-url https://download.pytorch.org/whl/cu124```

This is the command to install pytorch nightly instead which might have performance improvements:

```pip install --pre torch torchvision torchaudio --index-url https://download.pytorch.org/whl/nightly/cu124```

#### Troubleshooting

If you get the "Torch not compiled with CUDA enabled" error, uninstall torch with:

```pip uninstall torch```

And install it again with the command above.

### Dependencies

Install the dependencies by opening your terminal inside the ComfyUI folder and:

```pip install -r requirements.txt```

After this you should have everything installed and can proceed to running ComfyUI.

## Downloading the Stable Diffusion Model

To download the Stable Diffusion v1.5 model, follow these steps:

1. Visit the official Hugging Face page for Stable Diffusion v1.5:

   [Stable Diffusion v1.5 - Hugging Face](https://huggingface.co/stable-diffusion-v1-5/stable-diffusion-v1-5/tree/main)

2. Download the model weights by selecting the `v1-5-pruned-emaonly.safetensors`

## ComfyUI Workflow Screenshot

Below is the ComfyUI workflow that was created for transforming images into Van Gogh-style artwork using Stable Diffusion and ControlNet:

<div align="left">

<img src="https://github.com/anwarxo/van_Gogh_image_trasform/blob/main/images/comfy_workflow.png?raw=true" alt="ComfyUI Workflow" width="700"/>

</div>

## Features
- **Graph/Node-based Interface**: Easily design complex workflows using a drag-and-drop interface.
- **Stable Diffusion Support**: Fully supports SD1.x, SD2.x, and SDXL models.
- **GPU & CPU Support**: Works efficiently with both NVIDIA and AMD GPUs, and has a CPU fallback mode.
- **Memory Optimization**: Automatically manages memory to run models on devices with as low as 1GB of VRAM.
- **Modular**: Supports multiple extensions like ControlNet, Loras, and Inpainting.
- **Save/Load Workflows**: Easily save and load workflows, and even load them from generated PNG, WebP, and FLAC files.

## How It Works

The ComfyUI-based workflow allows you to upload an image (JPEG or PNG), which is then processed by Stable Diffusion with the help of ControlNet to transform it into a Van Gogh-style image.

1. **Upload**: You upload your image to the system.
2. **Preprocessing**: The image is resized and normalized to ensure it's ready for transformation.
3. **Style Transfer**: Stable Diffusion and ControlNet are applied to generate the Van Gogh style.
4. **Output**: The final stylized image is generated and displayed.

## Before and After Image Transformation

<div align="center">

<img src="https://github.com/anwarxo/van_Gogh_image_trasform/blob/main/images/lion.jpg?raw=true" alt="Original Image" width="400" height="300"/> ➡️ <img src="https://github.com/anwarxo/van_Gogh_image_trasform/blob/main/images/lion_after.png?raw=true" alt="Transformed Image" width="400" height="300"/>

</div>

<div align="center">

<img src="https://github.com/anwarxo/van_Gogh_image_trasform/blob/main/images/village_before.jpg?raw=true" alt="Original Image" width="400" height="280"/> ➡️ <img src="https://github.com/anwarxo/van_Gogh_image_trasform/blob/main/images/village_after.png?raw=true" alt="Transformed Image" width="400" height="280"/>

</div>

<div align="center">

<img src="https://github.com/anwarxo/van_Gogh_image_trasform/blob/main/images/elephant_before.jpg?raw=true" alt="Original Image" width="400" height="280"/> ➡️ <img src="https://github.com/anwarxo/van_Gogh_image_trasform/blob/main/images/elephant_after.png?raw=true" alt="Transformed Image" width="400" height="280"/>

</div>

## Frequently Asked Questions (FAQ)

**Q1**: What if I encounter a "Torch not compiled with CUDA enabled" error?  
**A1**: Uninstall your current version of `torch` using `pip uninstall torch` and reinstall it with CUDA support by running the appropriate `pip install` command for your GPU.

**Q2**: Can I use ComfyUI without a GPU?  
**A2**: Yes, but performance will be significantly slower. You can run it using the `--cpu` flag.

**Q3**: Where can I find more workflow examples?  
**A3**: You can find various workflow examples on the [ComfyUI Examples page](https://comfyanonymous.github.io/ComfyUI_examples/).


## License
This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.
