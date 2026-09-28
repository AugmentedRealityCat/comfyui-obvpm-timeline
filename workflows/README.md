# OBVPM Timeline Workflows

This folder contains ComfyUI workflow files to be used with the [comfyui-obvpm-timeline](https://github.com/chanon/comfyui-obvpm-timeline) custom node pack.

The version format is 

v`[comfyui-obvpm-timeline nodepack version to use it with]`-`[workflow version no]`

Use the latest workflow where possible. Older ones are kept for reference or in case a newer one has bugs or compatibility issues with a ComfyUI install.

## v0.1.1-006 (2026-09-28)

- New workflow [`h3_obvpm_timeline_r2v_v0.1.1-006.json`](h3_obvpm_timeline_r2v_v0.1.1-006.json). It runs on the pack's 0.1.1, with the same requirements as 005.
- Fixed: The latent upscaler now references the new renamed filename `minimax_h3_latent_upscaler_3d_conv_v1_fp16.safetensors` as reported by #16. Download it from [Hugging Face](https://huggingface.co/LBH-123-AI/Minimax_h3_latent_Upscaler/blob/main/minimax_h3_latent_upscaler_3d_conv_v1/minimax_h3_latent_upscaler_3d_conv_v1_fp16.safetensors) into `ComfyUI/models/latent_upscale_models/`.
- Fixed: Moved the `ModelSamplingMiniMaxH3` node from the sampling subgraphs to the `H3 Model Optimization` subgraph so that the `shift_video` is applied and shapes the schedule and the vsa sparse attention window correctly. The included presets all use 12, so their results are unchanged but if you changed the `shift_video` previously, this will change the result to be the correct one.

## v0.1.1-005 (2026-09-27)

- New workflow `h3_obvpm_timeline_r2v_v0.1.1-005.json`. It runs on the pack's 0.1.1.
- **Needs [comfyui-obvpm](https://github.com/chanon/comfyui-obvpm) 0.2.9 or newer.** Update it before loading the workflow.
- Feature: **Compatibility Check node**: when the workflow loads, it checks your ComfyUI version and every custom node pack the workflow uses, and lists anything missing or too old with a link to update it. Its **Copy Report** button copies the details for a bug report.
- Feature: Settings Presets: every setting has a tooltip, and the turbo LoRA and strength are only shown when a turbo loader is selected.
- Fixed: the `lightx2v` generation preset had its turbo loader set to off, so its LoRA was never loaded.
- Layout: A little bit less Get/Set nodes as Bundle and Unbundle can now Get/Set by themselves

## v0.1.1-004 (2026-09-22)

- Set the default generation preset to sample 20 steps instead of 8.

## v0.1.1-003 (2026-09-22)

- Fixes for errors when loading the workflow. (removed from repo)

## v0.1.0-002 (2026-09-22)

- Fixes for errors when loading the workflow. (removed from repo)

## v0.1.0-001 (2026-09-21)

- First workflow, released with the pack's 0.1.0. (removed from repo)
