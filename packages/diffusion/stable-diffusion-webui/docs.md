
![two robots sitting by a lake by a mountain](/docs/images/diffusion_webui.jpg)

* stable-diffusion-webui: https://github.com/AUTOMATIC1111/stable-diffusion-webui (`/opt/stable-diffusion-webui`)
* with TensorRT extension: https://github.com/AUTOMATIC1111/stable-diffusion-webui-tensorrt 
* faster performance than the base [`stable-diffusion/txt2img.py`](/packages/diffusion/stable-diffusion) script

This container has a default run command that will automatically start the webserver like this:

```bash
cd /opt/stable-diffusion-webui && python3 launch.py \
  --data=/data/models/stable-diffusion \
  --enable-insecure-extension-access \
  --xformers \
  --listen \
  --port=7860
```

After starting the container, you can navigate your browser to `http://$IP_ADDRESS:7860` (substitute the address or hostname of your device).  The server will automatically download the default model ([`stable-diffusion-1.5`](https://huggingface.co/runwayml/stable-diffusion-v1-5)) during startup.

Other configuration arguments can be found at [AUTOMATIC1111/stable-diffusion-webui/wiki/Command-Line-Arguments-and-Settings](https://github.com/AUTOMATIC1111/stable-diffusion-webui/wiki/Command-Line-Arguments-and-Settings)

* `--medvram` (sacrifice some performance for low VRAM usage)
* `--lowvram` (sacrafice a lot of speed for very low VRAM usage)

To run image generation from a script (`txt2img.py`) as opposed to the web UI, see the [`stable-diffusion`](/packages/diffusion/stable-diffusion) container.