# ComfyUI Load Image (with filename, HEIC)

> [!IMPORTANT]
> **This repo has moved.** The node is now part of **[ComfyUI-RulZnodes](https://github.com/speedyrulz/ComfyUI-RulZnodes)**,
> together with Load Image Batch (Simple) and Mask Intelligent Crop. This repo is archived and won't get updates.
>
> To switch, delete this folder from `custom_nodes` and install ComfyUI-RulZnodes. The node ID is unchanged,
> so existing workflows keep working.

A `LoadImage` replacement that also loads `.heic` / `.heif` files and outputs the filename.

**Outputs:** `image`, `mask`, `filename` (name without directory or extension).

## Install

Put this folder in `ComfyUI/custom_nodes/`, then install the dependency into ComfyUI's Python:

```
pip install -r requirements.txt
```

Restart ComfyUI. The node is under **image → Load Image (with filename, HEIC)**.

## Notes

- The included `web/heic_upload.js` extension widens the upload button's file picker to allow HEIC/HEIF
  (hard-refresh the browser after installing).
- Previews: browsers can't render HEIC, so `heic_preview.py` adds a middleware that serves `.heic`/`.heif`
  files as JPEG from ComfyUI's `/view` endpoint. The conversion happens in memory; no extra files are created.
- EXIF rotation is applied (phone photos come out upright).
