# ComfyUI Load Image (with filename, HEIC)

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
