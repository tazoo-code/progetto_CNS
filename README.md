# progetto_CNS

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

#### MAXIM
  [Maxim enhancement](./models/Enhancement models/MAXIM_enhancement.ipynb)
