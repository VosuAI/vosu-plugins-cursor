---
name: vosu
description: Generate and browse images, videos, and 3D with the VOSU MCP tools.
---

# /vosu

Natural-language entrypoint for VOSU. Keep the user's constraints. Tool descriptions from the connected VOSU MCP server are the source of truth for arguments, model keys, and prices.

## Usage

```
/vosu <natural language request>
```

## Examples

```
/vosu Make a cinematic product hero shot, 16:9
/vosu Animate this product photo — slow push-in, 5s, 9:16
/vosu What will a Seedance clip cost at 1080p?
/vosu How many credits do I have?
/vosu Show my recent images
/vosu Turn this image into a 3D model
```

## Routing

- **Credits** → `check_balance`. Quote its text as returned.
- **What a model accepts, or what a setting costs** → `model_options` before generating. Do not guess option keys.
- **One image** → `generate_image`.
- **One video** → `generate_video_model`.
- **Image to 3D** → `generate_3d`. It needs an image, not only a prompt.
- **Library** → `show_images`, `show_videos`, or `show_media` when they want both.
- **A local file** → `upload_media`, then pass the hosted URL into the generate tool.
- **A job that is still running** → `get_generation_status`.
- **The user's open Blender** → the `blender_*` tools, and only when they are driving Blender.

`generate_video`, `plan_ad`, `script_to_ad`, and `show_generations` are not in the live tool list. Do not call them.

Do not invent model ids, option keys, or prices. If a call fails, follow the tool's error instead of retrying the same arguments.
