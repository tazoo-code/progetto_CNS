# Te-LLM-e what you can see

In the context of police investigations, since the identification of the culprit depends also on the number and the quality of images of the subject, it is important to maximize the information at disposal of law enforcement agencies.
For this reason, we developed a forensic tool composed by pretrained models for image processing, with the aim of helping the identification of the subject.
This tool initially performs an enhancement of the original picture, to highlight the image details.
The second phase performs a linguistic description of the subject using a Vision-Language Model, extracting information about their physical features.
In the last stage, a generative model produces a synthetic picture of the subject, based on the original image and using a physical description as input prompt.
This method allows generating new images of the individual, performing data augmentation with respect to the original information.

## Method

We developed the tool using the following strategy:
  - Image enhancement: The quality of the original picture is improved using data processing methods, including Deep Learning techniques.
  - Linguistic description: The enhanced picture is described using a Vision-Language Model (VLM), to extract physical information about the subject.
  - Image augmentation: An Image-to-image model is used to generate new synthetic pictures of the subject, using as text prompt the information extracted in the previous phase.

### Image enhancement
In order to improve the quality of the images, we compared three signal processing methods for image enhancement, addressing different image processing tasks.

#### MAXIM enhancement ([source code](./models/enhancement_models/MAXIM_enhancement.ipynb))
This method is specialized in low-light enhancement, which is able to enhance lighting while reducing the image noise. 

#### Total variation denoising ([source code](./models/enhancement_models/Total_Variation_Denoising.ipynb))
This technique reduces the total variation of the picture, facilitating the removal of unwanted details while minimizing the error compared with the original image.

#### SRGAN enhancement ([source code](./models/enhancement_models/SRGAN_enhancement.ipynb))
This method aims to estimate a high-resolution image from its low-resolution counterpart.


### Linguistic description
The enhanced picture is described using a Vision-Language Model (VLM), to extract physical information about the subject.

#### Qwen-VL ([source code](./models/VLM_models/Qwen-VL/Qwen-VL-Chat-Int4_infer_dir.ipynb))
This small-scale VLM is composed by a pretrained vision encoder, a Vision-Language adapter, and a Large Language Model (Qwen-7B), and shows good performances on a broad range of visual-centric benchmarks.

#### TinyLLaVA ([source code](./models/VLM_models/TinyLLaVa/TinyLLaVA_infer_dir.ipynb))
The model is a small-scale large-multimodal architecture, composed by a pretrained vision encoder and a small-scale LLM, connected by a two-layer Multi-Layer Perceptron (MLP).



### Image augmentation
An Image-to-image model is used to generate new synthetic pictures of the subject, using as text prompt the information extracted in the previous phase.

#### PhotoMaker ([source code](./models/generative_models/PhotoMaker.ipynb))
This generative model produces synthetic pictures while preserving the identity of the subjects, guided through the input text prompts.



