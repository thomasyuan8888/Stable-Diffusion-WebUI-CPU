# Stable Diffusion WebUI CPU
 install Stable Diffusion WebUI on Windows with only CPU

 This project is cloned from:
 https://github.com/AUTOMATIC1111/stable-diffusion-webui/releases/tag/v1.0.0-pre

 and changed a few lines code to let it runs on Windows PC without GPU.

in launch.py:
```python
torch_command = os.environ.get('TORCH_COMMAND', "pip install torch==1.13.1  torchvision==0.14.1  --index-url https://download.pytorch.org/whl/cpu")
requirements_file = os.environ.get('REQS_FILE', "requirements_versions.txt")
commandline_args = os.environ.get('COMMANDLINE_ARGS', "--skip-torch-cuda-test  --disable-nan-check  --no-half --precision full --use-cpu all")
```
in webui.py, comment out the following line:
```python
#app.add_middleware(GZipMiddleware, minimum_size=1000)
``` 

then you can execute "run.bat" to start.


