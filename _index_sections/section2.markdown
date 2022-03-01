---
layout: section-tab
icon: /assets/img/icons/ocr.svg
title: Optical Character Recognition
---

The **Glyph Engine** (work in progress) is an *Optical Character Recognition* (**OCR**) system which supports text segmentation and recognition for multiple languages, given colorized, grayscaled or binarized documents.

## Example

We ran Glyph on one of the more distorted images from the English benchmarking set; the recognized text is attached below the image (errors in bold).


{% include image.html url="/assets/img/index_sections/glyph_demo1.png" description="An excessively smart gown is made of bands of<br>white cloth cut<strong>\"</strong>with the scissors and not hemmed<br>at the edges, arabesqued upon fin<strong>c</strong> Valenciennes<br>lace. The sleev<strong>è</strong>s are rather mor<strong>c</strong> full than the" size="60%" %}


## API
Currently, interaction with the **Glyph API** can be made using **POST** requests.
For example, a Python implementation of such request is provided below.
```python
import requests

# see lang codes below
data = {'lang' : 'en-ma'}
files = {'img': open('glyph_demo1.png', 'rb')}

response = requests.post('https://glyph-main.api.overfitted.io/process', files=files, data = data)

print(response.text)
```



## Supported Languages
- **English** - Modern Antiqua (lang code: *en-ma*) (25.02.2022) ([see benchmark](/benchmarks/ocr/glyph-en-modern-antiqua-benchmark))
- **German** - Modern Antiqua (lang code: *de-ma*) (01.03.2022) ([see benchmark](/benchmarks/ocr/glyph-de-modern-antiqua-benchmark))

## Supported Layouts
- One-column text (25.02.2022)