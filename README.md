# Consistent Character Sheet in One Image (ComfyUI + Qwen-Image-2512)

Pick your character LoRA, swap in your trigger word, and get a full character sheet in a single image: 4 turnaround views on the top row and 4 expressions on the bottom.

![Example output: Detective Crumpet character sheet](example_output_1.jpg)

*Example output made with this workflow and our free [Detective Crumpet LoRA](https://civitai.com/models/3033685).*

## What's inside

- `bravikron_character_sheet_qwen2512.json`: a clean ComfyUI workflow with a read-me note inside
- Full quality mode (30 steps, CFG 4, about 6 min on a 16 GB GPU) or fast mode (Lightning 4 steps, about 20 seconds)
- Works with any Qwen-Image-2512 character LoRA

## Models needed (all Apache 2.0)

| File | Folder |
|---|---|
| `qwen_image_2512_fp8_e4m3fn.safetensors` | `models/diffusion_models` |
| `qwen_2.5_vl_7b_fp8_scaled.safetensors` | `models/text_encoders` |
| `qwen_image_vae.safetensors` | `models/vae` |
| `Qwen-Image-2512-Lightning-4steps-V1.0-fp32.safetensors` (optional, for fast mode) | `models/loras` |
| Your character LoRA | `models/loras` |

## How to use

1. Start ComfyUI and drag the JSON onto the canvas.
2. Pick your LoRA in the green **"Your character LoRA"** node.
3. In the prompt node, replace `crump3t` with your LoRA's trigger word and describe the outfit.
4. Press **Queue**. Full quality renders at 1664x928.
5. Fast mode: select the **"Lightning 4-step"** node, press **Ctrl+B** to enable it, set steps to **4** and CFG to **1.0**, and queue again.

If the poses come out messy, try a few seeds first. If that doesn't help, ask for fewer views in the prompt, for example front, side and back only.

## Links

- Civitai page: <https://civitai.com/models/3036870>
- Detective Crumpet LoRA used in the example: [Civitai](https://civitai.com/models/3033685) · [Hugging Face](https://huggingface.co/bravikron/detective-crumpet-qwen-image-lora)
- All our free models: <https://bravikron.com/models.html>
- Custom LoRA training and character sheets: <https://bravikron.com/labs.html>

## Licence

The workflow is released under the MIT licence (see `LICENSE`). The models it loads have their own licences (Qwen-Image-2512 and its Lightning LoRA: Apache 2.0).
