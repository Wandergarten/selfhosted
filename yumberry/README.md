# Yumberry

## TODO
* Get that RPi!
* Shopping List
    * [RPi 5 8GB](https://www.berrybase.de/raspberry-pi-5-8gb-ram)
    * [27 Watt, USB-C, 5.1V, 5A Netzteil](https://www.berrybase.de/raspberry-pi-27w-usb-c-power-supply-netzteil-schwarz)
    * [Gehäuse](https://www.berrybase.de/offizielles-gehaeuse-fuer-raspberry-pi-5-schwarz/grau)
    * [Lüfter](https://www.berrybase.de/raspberry-pi-active-cooler-luefter-fuer-raspberry-pi-5)
    * [AI Kit: Hailo 8L + M2 HAT](https://www.berrybase.de/ai-kit-fuer-raspberry-pi-m.2-hat-hailo8l-ai-accelerator)
    * [Micro HDMI <-> HDMI-Adapterkabel](https://www.berrybase.de/micro-hdmi-adapterkabel-d-stecker-a-buchse-15cm-schwarz)
    * [Raspberry Pi High Quality Kamera, C-Mount mit CS-Adapter](https://www.berrybase.de/raspberry-pi-high-quality-kamera) ([Documentation](https://www.raspberrypi.com/documentation/accessories/camera.html))
        * [Zoom Objektiv, C-Mount](https://www.berrybase.de/8-50mm-zoom-objektiv-c-mount)
        * [Stativ, C-Mount](https://www.berrybase.de/flexibles-mini-stativ-mit-kugelkopf-175mm-schwarz)
        * [Teleobjektiv, C-Mount](https://www.berrybase.de/100mm-teleobjektiv-c-mount)
        * [Weitwinkel, CS-Mount](https://www.berrybase.de/6mm-weitwinkelobjektiv-cs-mount)

## Ideas
* Get those karma points - citizen science
    * Environmental monitoring - active: [https://luftdaten.info/](https://sensor.community/de/sensors/airrohr/)
    * Environmental monitoring - passive: visualize open data from Umweltamt open data API: [here](https://www.umweltbundesamt.de/daten/luft/luftdaten/doc#tag/measurements), [here](https://luftqualitaet.api.bund.dev/), and [here](https://luftdaten.berlin.de/station/mc117?group=pollution&period=1h&timespan=currentday&page=37)
* Machine Learning is fun!
    * Raspberry Pi AI Kit powered by HAILO 8L
        * [Prerequisites](https://www.raspberrypi.com/documentation/accessories/ai-kit.html#prerequisites): RPi 5, AI Kit (M.2 HAT+ + Hailo 8L module), Raspberry Pi OS, Raspberry Pi camera (HQ Camera)
        * Raspberry Pi: [AI Kit](https://www.raspberrypi.com/products/ai-kit/)
        * Raspberry Pi: [AI Kit Product Brief](https://datasheets.raspberrypi.com/ai-kit/raspberry-pi-ai-kit-product-brief.pdf)
        * Raspberry Pi: [AI Kit Documentation & Getting Started](https://www.raspberrypi.com/documentation/accessories/ai-kit.html)
        * Hailo: [Hailo 8L](https://hailo.ai/de/products/ai-accelerators/hailo-8l-m-2-entry-level-acceleration-module/)
        * Hailo: [Hailo 8L Model Zoo](https://github.com/hailo-ai/hailo_model_zoo/tree/master/docs/public_models/HAILO8L)
        * Hailo: [RPi AI Kit Installation Guide](https://www.youtube.com/watch?v=_aCyR8XJcws)
        * Hailo: [Hailo World Example](https://github.com/hailo-ai/hailo-rpi5-examples)
        * Raspberry Pi: [AI Kit Announcement](https://www.raspberrypi.com/news/raspberry-pi-ai-kit-available-now-at-70/)
    * Local SLM server 
        * [Ollama](https://ollama.com/download/linux)
        * [Open Web UI](https://github.com/open-webui/open-webui) - User-friendly WebUI for LLMs (Formerly Ollama WebUI)
        * HOWTO: RPi 5 (+ Docker) + Ollama + Open Web UI [#1](https://github.com/adijayainc/LLM-ollama-webui-Raspberry-Pi5), [#2](https://k33g.hashnode.dev/run-ollama-on-a-pi5), [#3](https://blog.berrybase.de/large-language-model-llm-auf-raspberry-pi-5-installieren-eine-anleitung/)
        * Small Language Models: [DeepSeek Coder 1.3B](https://ollama.com/library/deepseek-coder:1.3b), [Phi-3 mini](https://ollama.com/library/phi3:mini), [TinyLlama](https://ollama.com/library/tinyllama:1.1b), [Qwen2 1.5B](https://ollama.com/library/qwen2:1.5b), [CodeGemma 2B](https://ollama.com/library/codegemma:2b), [Orca Mini 3B](https://ollama.com/library/orca-mini:3b), [TinyDolphin 1.1B](https://ollama.com/library/tinydolphin:1.1b), [Startcode 1B](https://ollama.com/library/starcoder:1b); Source: [#1](https://github.com/parakeet-nest/awesome-slms)
    * Local SDXL server
        * [OnnxStream](https://github.com/vitoplantamura/OnnxStream)
        * HOWTO: [#1](https://ai-search.io/articles/how-to-use-stable-diffusion-with-raspberry-pi-onnxstream-and-diffusers)
* HDD Diagnostics


