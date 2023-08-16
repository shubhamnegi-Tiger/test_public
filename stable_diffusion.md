**Content Generation**

In the fast-paced digital landscape, where information spreads like wildfire, content generation has become a vital strategy for businesses and individuals aiming to establish their online presence. One intriguing approach that has gained prominence is "Stable Diffusion." This method revolves around the controlled and strategic dissemination of content to captivate and engage the target audience.

# <a name="_toc135249779"></a>Terminologies:
<a name="_toc135249780"></a>Prompts: The prompt is a way to guide the diffusion process to the sampling space where it matches. A good prompt needs to be detailed and specific.

<a name="_toc135249780"></a>Negative Prompts: A negative prompt is a way to use Stable Diffusion in a way that allows the user to specify what he doesn’t want to see, without any extra input. It is a parameter that tells the Stable Diffusion model what not to include in the generated image.

<a name="_toc135249780"></a>CFG scale: In the context of Stable Diffusion, the CFG scale essentially governs how much the image looks closer to the prompt or input image. The higher the CFG scale, the more the image will match your prompt. Conversely, a lower CFG scale value produces a better-quality image that may differ from the original prompt or image.

<a name="_toc135249780"></a>Sampling Steps: Sampling steps is the number of iterations that Stable Diffusion runs to go from random noise to a recognizable image based on the text prompt. As an extremely general rule of thumb, the higher the sampling steps, the more detail you will add to your image at the cost of longer processing time.

# <a name="_toc135249784"></a>Objective
In our study, we focused on and implemented methods specifically to create content for a personalized and targeted advertisement generation using various versions of stable diffusion.

<a name="_toc135249780"></a>**Stable Diffusion**: Stable Diffusion is a deep learning, text-to-image model released in 2022 based on diffusion techniques. It is primarily used to generate detailed images conditioned on text descriptions, though it can also be applied to other tasks such as inpainting, outpainting, and generating image-to-image translations guided by a text prompt.

![1](https://user-images.githubusercontent.com/110606035/260971587-549e4bb1-d714-4185-ba22-3323a0b4c81e.png)

*Figure 1: Batman in IronMan suit

<a name="_toc135249780"></a>**SDv1.5**: Stable Diffusion v1-5 is a latent diffusion model which combines an autoencoder with a diffusion model that is trained in the latent space of the autoencoder. During training, Images are encoded through an encoder, which turns images into latent representations. It was released on 20 October 2022.

![4](https://user-images.githubusercontent.com/110606035/260971713-f10f46ec-be50-4b99-bfa8-d6995828a40b.png)

*Figure 2: Image generated through SDv1.5
Prompt: a caucassian couple in their 30s eating breakfast in morning on a wooden table, face, intricate details
Sampling method: DPM++ 2M SDE Karras
Sampling step: 55
CFG Scale = 7
seed : 3972808974

<a name="_toc135249780"></a>**SDv2.1**: Stable Diffusion 2.1 is a state-of-the-art machine learning model introduced in 2022, primarily designed for High-Resolution Image Synthesis with Latent Diffusion. The model excels in generating detailed and high-quality images conditioned on text descriptions.

![17](https://user-images.githubusercontent.com/110606035/260971806-ab2da5cd-222c-4966-a6c2-a3ceaa432880.png)

*Figure 3:Image generated thorough SDv2.1
Prompt: a ((african american)) couple in their 30s eating breakfast in morning on a wooden table, face, intricate details
Sampling method: DPM++ SDE Karras
sampling step: 45
CFG Scale = 7
seed : 3972808974

<a name="_toc135249780"></a>**SDXL 1.0**: SDXL 1.0, short for “Stable Diffusion XL,” is touted as a latent text-to-image diffusion model that supposedly surpasses its predecessors with a range of promising enhancements.

![2](https://user-images.githubusercontent.com/110606035/260971922-41b8bb75-d81f-4695-a6af-21cef4f1746c.png)

*Figure 1: Image created through SDXL 1.0
Prompt: an african american couple with in their 30s eating breakfast in morning on a wooden table, face, intricate details, Ultra realistic, UHD
Sampling method: DPM++ 2M SDE Karras
sampling step: 55
CFG Scale = 7
seed : 4022988122

![8](https://user-images.githubusercontent.com/110606035/260972040-d866924c-15f0-4439-ace5-fe2cf9bbbb57.png)

![1](https://user-images.githubusercontent.com/110606035/260972209-285ef46d-1864-410b-8537-dead427e6f13.png)

![2](https://user-images.githubusercontent.com/110606035/260972276-56dc72f6-2af3-4f93-8871-0fc1b67c4492.png)
