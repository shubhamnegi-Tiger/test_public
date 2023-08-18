Table of Content
=============================

- [Introduction to Text to Image Generation](#introduction-to-text-to-image-generation)
- [API Exploration](#api-exploration)
- [Limitations - DALL E2 ,Stable Diffusion and Craiyon](#limitations-dall-E2-Stable-Diffusion-and-craiyon)
- [Why Stable Diffusion?](#why-stable-diffusion)
- [Model Performence Enhancing Techniques ](#model-performence-enhancing-techniques)

  - [Negative Prompts](#negative-prompts)
  
  - [DreamBooth](#dreambooth)

- [Model Checkpoints](#model-checkpoints)
- [Limitation](#limitation)
- [Future Scope](#future-scope)
- [Conclusion](#conclusion)
- [Reference](#reference)

# Introduction to Text to Image Generation

Text-to-image generation is an exciting and rapidly advancing field of artificial intelligence that aims to convert textual descriptions into visually appealing images. This technology has the potential to revolutionize industries such as advertising, entertainment, and e-commerce by providing a way to generate customized images based on textual descriptions.

<img  align="center" width="835" src="https://github.com/tpjesudhas/cv_component/assets/59251032/1f943119-38ac-4f1f-bcbd-4f7e11df53f7">
...


A text to image model is a machine learning model which takes as input a natural language description and produces an image matching that description. Text-to-image models generally combine language model, which transforms the input text into a latent representation, and a generative image model, which produces an image conditioned on that representation. The most effective models have generally been trained on massive amounts of images and text data scraped from the web. This repository contains code for generating images from textual descriptions using various existing API’s like DALL E2, Stable Diffusion etc.Additionally, the repository contains various optimization techniques that can be applied to text-to-image models to improve their efficiency.

### Images Generated Using Different Text-to-Image Techniques

The table showcases a comparison of images generated by different text-to-image techniques, including `DALL-E 2`, `Stable Diffusion`, `Craiyon`, `Stable Diffusion with Negative Prompt`, and `Stable Diffusion with Dreambooth`. Each technique has been used to generate images based on the same text prompt, and the resulting images are shown side-by-side for comparison.For a more detailed understanding of each technique, we encourage to continue reading further.

  <table>
        <tr>
         <td> <style="font-size=20px"><b>Prompts</b></td>
         <td> <style="font-size=20px"><b>DALL E2</b></td>
         <td> <style="font-size=20px"><b>Stable Diffusion</b></td>
         <td> <style="font-size=20px"><b>Craiyon</b></td>
         <td> <style="font-size=20px"><b>Stable Diffusion with Negative Prompts</b></td>
         <td> <style="font-size=20px"><b>Stable Diffusion with DreamBooth</b></td>
         </tr>
          <tr>
          <td><b>A child eating ice cream</b></td>
          <td> <img src="https://github.com/tpjesudhas/cv_component/assets/59251032/05c81b47-0771-4e32-bc56-2d43ecb9574d"></td>
          <td> <img src="https://github.com/tpjesudhas/cv_component/assets/59251032/79ff8b91-b6d0-4235-a0b7-bc466f3d0857" ></td>
           <td> <img src="https://github.com/tpjesudhas/cv_component/assets/59251032/39f4a1c2-0e5a-4acc-bdfb-1ae473a75f82" ></td>
            <td> <img src="https://github.com/tpjesudhas/cv_component/assets/59251032/40d14ed8-c513-41bf-aa18-3f53bb3e7af6" ></td>
            <td> <img src="https://github.com/tpjesudhas/cv_component/assets/59251032/63f3a72e-6efc-45b2-9e54-0493904eaeb0" ></td>
          </tr> 
          <tr>
          <td><b>A family enjoying a meal together at McDonald's</b></td>
          <td> <img src="https://github.com/tpjesudhas/cv_component/assets/59251032/6d1e9964-190e-46f0-8579-43bc642de504" ></td>
           <td> <img src="https://github.com/tpjesudhas/cv_component/assets/59251032/2b559d9a-8019-4126-8140-54e9e6befa1d"></td>
          <td> <img src="https://github.com/tpjesudhas/cv_component/assets/59251032/23b2ce08-a4f2-465b-9a23-1077c25cba41"></td>
           <td> <img src="https://github.com/tpjesudhas/cv_component/assets/59251032/e224f078-10a6-4501-8a93-61baba362390"></td>
            <td> <img src="https://github.com/tpjesudhas/cv_component/assets/59251032/dbee82f7-8c32-4f4f-8926-02585fb0427a"></td>
          </tr> 
          <tr>
          <td><b>A person enjoying a bag of Lay's potato chips</b></td>
          <td> <img src="https://github.com/tpjesudhas/cv_component/assets/59251032/945d1e19-3571-414a-bf14-8bc0af382e10"></td>
          <td> <img src="https://github.com/tpjesudhas/cv_component/assets/59251032/7268630c-f58c-42a7-9c41-ffe43638bbec"></td>
           <td> <img src="https://github.com/tpjesudhas/cv_component/assets/59251032/68d25208-0099-47d8-a475-55a85d432724"></td>
            <td> <img src="https://github.com/tpjesudhas/cv_component/assets/59251032/caf1a88b-a17d-488e-8952-fa8b90903e30"></td>
            <td> <img src="https://github.com/tpjesudhas/cv_component/assets/59251032/e2f9a5aa-720f-46d6-89ae-4349b45cf197"></td>
          </tr> 
   </table>
   

 
 

Click for more - [DALL E 2](#dall-e-2) [Craiyon](#dall-e-mini) [Stable Diffusion](#stable-diffusion) [Stable Diffusion with Negative Prompts](#negative-prompts) [Stable Diffusion with DreamBooth](#dreambooth)



# API Exploration
We explored all freely available text to generation APIs like `Dalle 2`, `Stable diffusion`, `Dalle mini`, etc. and compared the results. 

#### DALL E 2

DALL-E 2 leverages a more powerful transformer architecture and has been trained on a massive dataset of over one billion image-text pairs. With its advanced capabilities, DALL-E 2 can generate complex images that combine multiple concepts and refine them iteratively to produce final, high-quality images. 
We found that all are giving comparable results, with Dalle 2 having a slight upper hand. But Dalle 2 has the limitation to generate images freely beyond a limit. Mostly all the APIs fail to generate good quality images in the aspect of human faces.

<img  align="center" width="835" src="https://github.com/SharmaSubham975/text_to_image_generation/assets/106384866/63e24d2e-25ca-4ec0-b729-708968a724dd">

For more images click [here](https://drive.google.com/drive/folders/1FExy6yPlbk-TnILNkcJOwNB8sBnKW5LK?usp=share_link)


#### DALL E MINI 

Craiyon, formerly DALL·E mini, is an image generation engine that uses artificial intelligence and machine learning, presenting an interface that will convert plain-language text to images. The AI was fed a database of images and text descriptions until it learned to associate words with not only shapes, but color combinations, line thicknesses, differences in perspective, and other elements of artistic style. The AI learned so well, it can duplicate, to a great extent, the style of well-known artists.

<img  align="center" width="835" src="https://github.com/SharmaSubham975/text_to_image_generation/assets/106384866/86960015-7224-42e6-91bf-6ea493eb6ee5">

For more images click [here](https://drive.google.com/drive/folders/1mLxbcugJN5e84lzwwkvtc6I2J5QsMvmT?usp=share_link)


#### Stable Diffusion

Stable Diffusion is a latent diffusion model that generates high-quality images by gradually refining an initial image. This process involves introducing noise into the image and iteratively refining it to produce a final image that meets the specified criteria. It is primarily used to generate detailed images conditioned on text descriptions, though it can also be applied to other tasks such as inpainting, outpainting, and generating image-to-image translations guided by a text prompt. Instead of operating in the high-dimensional image space, it first compresses the image into the latent space. The latent space is 48 times smaller so it reaps the benefit of crunching a lot fewer numbers. This makes it faster.

<img  align="center" width="835" src="https://github.com/SharmaSubham975/text_to_image_generation/assets/106384866/c7ad077a-3a39-499b-8309-188a1139db16">

**SDv1.5**: Stable Diffusion v1-5 is a latent diffusion model which combines an autoencoder with a diffusion model that is trained in the latent space of the autoencoder. During training, Images are encoded through an encoder, which turns images into latent representations. It was released on 20 October 2022.

![2](https://user-images.githubusercontent.com/110606035/260971713-f10f46ec-be50-4b99-bfa8-d6995828a40b.png)

Figure 2: Image generated through SDv1.5
||  Prompt: a caucassian couple in their 30s eating breakfast in morning on a wooden table, face, intricate details
||  Sampling method: DPM++ 2M SDE Karras
||  Sampling step: 55
||  CFG Scale = 7
||  seed : 3972808974

**SDv2.1**: Stable Diffusion 2.1 is a state-of-the-art machine learning model introduced in Dec 7, 2022, primarily designed for High-Resolution Image Synthesis with Latent Diffusion. The model excels in generating detailed and high-quality images conditioned on text descriptions.

![3](https://user-images.githubusercontent.com/110606035/260971806-ab2da5cd-222c-4966-a6c2-a3ceaa432880.png)

Figure 3: Image generated thorough SDv2.1
||  Prompt: a african american couple in their 30s eating breakfast in morning on a wooden table, face, intricate details
||  Sampling method: DPM++ SDE Karras
||  sampling step: 45
||  CFG Scale = 7
||  seed : 3972808974

**SDXL 1.0**: SDXL 1.0, short for “Stable Diffusion XL,” is touted as a latent text-to-image diffusion model that supposedly surpasses its predecessors with a range of promising enhancements.It was released on July 26, 2023

![4](https://user-images.githubusercontent.com/110606035/260971922-41b8bb75-d81f-4695-a6af-21cef4f1746c.png)

Figure 4: Image created through SDXL 1.0
||  Prompt: an african american couple with in their 30s eating breakfast in morning on a wooden table, face, intricate details, Ultra realistic, UHD
||  Sampling method: DPM++ 2M SDE Karras
||  sampling step: 55
||  CFG Scale = 7
||  seed : 4022988122

**Deliberate**: Deliberate - v2 is an open source model based on fine tuning of SDv1.5. It was released in Feb 25, 2023

![5](https://user-images.githubusercontent.com/110606035/260972040-d866924c-15f0-4439-ace5-fe2cf9bbbb57.png)

Figure 5: Image created through Deliberate2 
||  Prompt: an african american couple in their 30s eating breakfast in morning on a wooden table, face, intricate details
||  Sampling method: DPM++ SDE Karras
||  Sampling step: 45
||  CFG Scale = 7
||  seed : 3972808974

**RealisticVision**: Realistic Vision V5.0 is an open source model based on fine tuning of SDv1.5. It was released in Jul 25, 2023

![6](https://user-images.githubusercontent.com/110606035/260972209-285ef46d-1864-410b-8537-dead427e6f13.png)

Figure 6: Image created through RealisticVision5 
||  Prompt: a caucassian couple in their 30s eating breakfast in morning on a wooden table, face, intricate details
||  Sampling method: DPM++ 2M SDE Karras
||  sampling step: 55
||  CFG Scale = 7
||  seed : 3972808974

For more images click [here](https://drive.google.com/drive/folders/1hJ3eTrFYBKDpod8ksXmhl53p3IkxZaGg?usp=share_link)

# Limitations - DALL E2 ,Stable Diffusion and Craiyon


<p>
<img align="left" width="834" alt="flow2" src="https://user-images.githubusercontent.com/106384866/236795620-b6a07ca3-36c0-4973-9366-b2ddb6cbdfbb.png">

<br/>
<br/>
</p>

To see documentaton click [here](https://github.com/SharmaSubham975/text_to_image_generation/blob/fmcg_dreambooth_stablediffusion/docs/FMCG/API_pros_cons.xlsx)


# Why Stable Diffusion?

Since Stable Diffusion is open-sourced, users can either explore it online or download the model directly on their systems. In addition to its general user accessibility, the model is also available for commercial purposes. And we can do custom training and fine-tune stable diffusion models as per our requirements.

Besides its ability to generate highly-detailed images, the popularity of stable diffusion comes from its open-sourced nature, its ease of use, and its ability to run on consumer-level graphics cards. This is in a way democratizing image generation and allowing anyone interested to try it out and add fuel to its evolution.These all made us select Stable Diffusion for further research steps.

<p>
<img align="center"  width="834"  alt="flow2" src="https://user-images.githubusercontent.com/106384866/236799413-4b19ae06-c498-4ad9-a7d5-0b6348ee4e8a.png">
<br/>
<br/>
</p>
.....

**Components of Stable Diffusion**

Stable diffusion is not one simple AI model. It’s a process combining different neural networks.It mainly consits of consists of 3 parts: the `variational autoencoder` (VAE), `U-Net`, and an optional `text encoder`. We can break down the entire process of text-to-image generation with stable diffusion into different steps :

**Step 1.** Stable Diffusion generates a random tensor in the latent space. we can control this tensor by setting the seed of the random number generator. If we set the seed to a certain value, you will always get the same random tensor. This is your image in latent space. But it is all noise for now.

**Step 2.** The noise predictor U-Net takes the latent noisy image and text prompt as input and predicts the noise, also in latent space (a 4x64x64 tensor).

**Step 3.** Subtract the latent noise from the latent image. This becomes your new latent image.
Steps 2 and 3 are repeated for a certain number of sampling steps, for example, 20 times.

**Step 4.** Finally, the decoder of VAE converts the latent image back to pixel space. This is the image you get after running Stable Diffusion.

![10](https://user-images.githubusercontent.com/110606035/261001294-0b89065a-cefc-491b-9b57-ed6bdad42238.png)

Figure 10: Image created by Training DreamBooth
||  Base Model: SDv1.5
||  Number of Epochs:800
||  Learning Rate: 0.00001
||  Optimizer: 8bit_adam
||  Number of Images:9

# Model Performence Enhancing Techniques 

To improve the quality of the images generated by Stable Diffusion, we experimented the methods 

1) `Negative Prompts` 

2) `DreamBooth`
   
3) `LoRA`

4) `Textual Inversion`

5) `ControlNet` 

## Negative Prompts

Negative prompts are an additional way to control text-to-image generation.It is a parameter that tells Stable Diffusion what you don't want to see in the generated images. When specified, it guides the generation process not to include things in the image according to a given text.

<img align="center"  width="834" src="https://github.com/SharmaSubham975/text_to_image_generation/assets/106384866/0826f004-eb4d-4567-a2dd-3f5bda795587">
...

Technically, a positive prompt steers the diffusion towards the images associated with it, while a negative prompt steers the diffusion away from it. Negative prompt is implemented by hijacking the unconditional sampling in diffusion models. Instead of using an empty prompt in unconditional sampling that generates random images, a negative prompt is used .

**Negative Prompts used :** 

`fake, ugly ,disfigured, out of frame, extra fingers, extra limbs, extra arms, extra legs, fused fingers, too many fingers, poorly drawn face, cartoon, poor facial details, low resolution, bad composition, mutated body parts, blurry image, , poorly drawn fingers, fantasy, deformed, surreal`


### Samples Images Generated Using Negative Prompts

<table>
        <tr>
         <td> <style="font-size=20px"><b>Prompts</b></td>
         <td> <style="font-size=20px"><b>Without Negative Prompts</b></td>
         <td> <style="font-size=20px"><b>With Negative Prompts</b></td>
         </tr>
          <tr>
          <td><b>A family enjoying a meal together at McDonald's</b></td>
          <td> <img src="https://github.com/SharmaSubham975/text_to_image_generation/assets/106384866/cca5776c-12e5-480e-975d-c387467bbfc0"></td>
          <td> <img src="https://github.com/SharmaSubham975/text_to_image_generation/assets/106384866/1640c32a-df0a-466a-bd99-6afd04d4ff85" ></td>
          </tr> 
          <tr>
          <td><b>A lady baking a cake</b></td>
          <td> <img src="https://github.com/SharmaSubham975/text_to_image_generation/assets/106384866/e36deaa3-fac0-42fa-aeb0-d75a27aeeb77"></td>
          <td> <img src="https://github.com/SharmaSubham975/text_to_image_generation/assets/106384866/60aa9d87-2643-45f0-9404-acd577fed773" ></td>
          </tr> 
           <tr>
          <td><b>A old aged lady holding a packet of snacks in her hand</b></td>
          <td> <img src="https://github.com/SharmaSubham975/text_to_image_generation/assets/106384866/528a37b0-549c-4a5c-b17c-7eb41a7ec770"></td>
          <td> <img src="https://github.com/SharmaSubham975/text_to_image_generation/assets/106384866/6d160ecc-93be-41e2-b06a-dd4a0aba16e3" ></td>
          </tr> 
   </table>



For more images click [here](https://drive.google.com/drive/folders/118sy9gmcnRNAHKd7m5NG6b-Il0Hp9Rlb?usp=share_link)

Using negative prompts, we were able to improve the quality of the images much, especially the images with human faces. But still, there is more room to improve. This made us try other techniques like DreamBooth and Textual Inversion.


## DreamBooth

DreamBooth is a deep learning generation model used to fine-tune existing text-to-image models. We can use this method to personalize text-to-image model Stable Diffusion given just a few images of a subject. DreamBooth fine-tunes all the parameters in the diffusion model, keeping the text transformer frozen, and uses generated images as the regularization dataset. Textual Inversion only optimizes a new word embedding token for each concept.

The method takes as input a few images of a subject (e.g., a specific dog) and the corresponding class name (e.g. "dog"), and returns a fine-tuned/"personalized'' text-to-image model that encodes a unique identifier that refers to the subject. Then, at inference, we can implant the unique identifier in different sentences to synthesize the subjects in difference contexts.

<p>
<img align="center" width="834" alt="flow2" src="https://user-images.githubusercontent.com/106384866/236811735-f02bdf57-558c-447d-b870-5959c94224dd.png">
<br/>
<br/>
....
  


**DreamBooth Training**

**Child**:For fine-tuning the model with DreamBooth, we created a dataset with 28 images of a child eating ice cream.Training Images Must all be of exact dimensions (512×512).All images are different and from different angles and backgrounds. The unique identifier used is "chice."
The images were renamed using the unique identifier. We gave detailed captions for each image and trained the model with 2000 training steps and 5e-6 learning rate.

**Family**:And another dataset with 38 images of same family members from differnet angles and backgrounds and resized to 512*512.The unique identifier used is "famtog."The images were renamed using the unique identifier. We gave detailed captions for each image and trained the model with 2000 training steps and 5e-6 learning rate.

**Chocos**: Here we used a relatively small dataset of 9 images resized to 512X512. The unique identifier was "uxz". The base model used was SDv1.5 and trained with 800 steps with e-5 learning rate and 8bit_adam optimizers.

### Samples Images Generated using DreamBooth

**1) A chice(child)  savoring a vanilla ice cream cone with rainbow sprinkles in a park**

<p>
<img align="center"  width="500" height="400" src="https://user-images.githubusercontent.com/106384866/235663914-6b9a3695-6321-4779-abc5-d3a6df276194.png">
<br/>
<br/>
</p>
.....



**2) A famtog(family) enjoying a hot summer day with ice-cold bottles of coca cola**

<p>
<img align="center"  width="500" height="400" src="https://user-images.githubusercontent.com/106384866/235664056-accd992d-7d8a-4a95-96fb-10bf5658f3f4.png">
<br/>
<br/>
</p>
.....



**3) A chice(child) enjoying a strawberry ice cream cone on a hot summer day at the beach**

<p>
<img align="center"  width="500" height="400" src="https://user-images.githubusercontent.com/106384866/235664659-d5c582cb-4e0d-437b-b424-4632f6a68999.png">
<br/>
<br/>
</p>
.....

**4) A bowl of uxz(chocos) on a wooden table with some uxz(chocos) lying on the table**

<p>
<img align="center"  width="500" height="500" src="https://user-images.githubusercontent.com/110606035/261001294-0b89065a-cefc-491b-9b57-ed6bdad42238.png">
<br/>
<br/>
</p>
.....

For more images click [here](https://drive.google.com/drive/folders/1JWO9mIkBoKXUThiHkSzd4Na2fRF58WNr?usp=share_link)

**Negative Prompts** used in **DreamBooth** :

`deformed, ugly, out of frame, mutilated, disfigured, text, extra limbs, face cut, head cut, extra fingers, extra arms, poorly drawn face, mutation, bad proportions, cropped head, malformed limbs, mutated hands, fused fingers, long neck,cropped, worst quality, low quality, jpeg artifacts, out of frame,watermark, signature, fake,ugly,illustration, painting, drawing, art, sketch, cartoon , floating objects , tongue, poor facial details, poorly rendered hands, mutated body parts,deformed body features, fake food ,fake beverages, fake bottles, fake cans, mutated fingers `


`Result Interpretation` : 
 We used a web UI for interpreting the results. And the results in terms of the child's face was satisfying. The model is able to generate images of the child without overfitting.


# Model Checkpoints

The Checkpoints for chice model can be found  [here](https://drive.google.com/drive/folders/1WYGxIth5cBsWUj84wvhp3CPYvSMRAcU3?usp=share_link)

The Checkpoints for famtog model can be found  [here](https://drive.google.com/drive/folders/1zdl-hmsTwx9DPr4dhl7ih3FHjm8B4iUL?usp=share_link)


# Limitation

* With Dreambooth, StableDiffusion overfits quickly. It's important to find the right learning rate (LR) and training steps for your dataset. Training a higher learning rate for less steps and training a lower learning rate for more steps gives very similar results. We have to find the 'sweet spot' training steps for a given learning rate to get reasonable images.

* Dreambooth needs more training steps for faces. In our experiments with batch size of 2 and LR of 5e-6, around 2000 steps worked well.

* Prior preservation is important to avoid overfitting when training on faces, for other objects it doesn't seem to make a huge difference.

## LoRA

LoRA (Low-Rank Adaptation) is a training technique for fine-tuning Stable Diffusion models. LoRA models operate by applying minute changes to the most critical part of Stable Diffusion models—the cross-attention layers. This is the part where the image and the prompt intersect, and researchers have found that fine-tuning this section yields excellent training results.

**LoRA training**

**Person**:For fine-tuning the SDv1.5 model with LoRA, we created a dataset with 19 images of a particular person.Training Images Must all be of exact dimensions (512×512).All images are different and from different angles and backgrounds. The unique identifier used is "olsen". We gave detailed captions for each image and trained the model with 1900 training steps and 4e-4 learning rate.

**Chocos**: Here we used a relatively small dataset of 9 images resized to 512X512. The unique identifier was "choxz".We gave detailed captions for each image. The base model used was SDv1.5 and trained with 900 steps with 4e-4 learning rate and adafactor optimizers.

### Samples Images Generated using LoRA

**1) A Women Olsen in braids wearing a white dress posing for a camera**

<p>
<img align="center"  width="500" height="500" src="https://user-images.githubusercontent.com/110606035/261555142-06b97d39-b30e-4293-93bb-f35ab506547e.png">
<br/>
<br/>
</p>
.....



**2) A white bowl of chocos on a napkin placed on a wooden table with some chocos on the table**

<p>
<img align="center"  width="500" height="500" src="https://user-images.githubusercontent.com/110606035/260972276-56dc72f6-2af3-4f93-8871-0fc1b67c4492.png">
<br/>
<br/>
</p>
.....


## Textual Inversion

Textual Inversion is a technique that allows us to add new styles or objects to text-to-image models without modifying the underlying model.

![3](https://user-images.githubusercontent.com/110606035/261252441-5cd8c37e-5155-45a3-bdef-34f63b621a8a.png)

Textual inversion learns a new token embedding (v* in the diagram above). A prompt (that includes a token which will be mapped to this new embedding) is used in conjunction with a noised version of one or more training images as inputs to the generator model, which attempts to predict the denoised version of the image. The embedding is optimized based on how well the model does at this task - an embedding that better captures the object or style shown by the training images will give more useful information to the diffusion model and thus result in a lower denoising loss. After many steps (typically several thousand) with a variety of prompt and image variants the learned embedding should hopefully capture the essence of the new concept being taught.

**Textual Inversion training**

**Chocos**: Here we used a relatively small dataset of 9 images resized to 512X512. The unique identifier was "xoxz".We gave detailed captions for each image. The base model used was SDv1.5 and trained with 3000 steps with variable learning rate of 0.05:10, 0.02:20, 0.01:60, 0.005:200, 0.002:500, 0.001:3000 and adafactor optimizers.

### Samples Images Generated using LoRA

**1) A white bowl of chocos on a grey background**

<p>
<img align="center"  width="500" height="500" src="https://user-images.githubusercontent.com/110606035/261001686-a6cd3ecb-d6b9-45fc-9241-65b7ea437463.png">
<br/>
<br/>
</p>
.....


![9](https://user-images.githubusercontent.com/110606035/261229325-c2de9fa4-da18-4629-8f0a-66473e85c9fc.png)
Figure 9: Training Textual Inversion on bowl of chocos
|| Epoch 50
|| Epoch 500
|| Epoch 1500
|| Epoch 2500
|| Epoch 3000

## ControlNet

ControlNet is a neural network structure to control diffusion models by adding extra conditions. It copys the weights of neural network blocks into a "locked" copy and a "trainable" copy. The "trainable" one learns your condition. The "locked" one preserves your model.Thanks to this, training with small dataset of image pairs will not destroy the production-ready diffusion models.
ControlNet helps us to capture the outline of a photo (like an edge detector) and try to generate image on top of those outlines.

![11](https://user-images.githubusercontent.com/110606035/261204604-f57c2cca-3dc3-4cc8-81f8-f03706f6375d.png)

Figure 11: ControlNet

![12](https://user-images.githubusercontent.com/110606035/261208156-d87c131b-59db-4220-8511-b5c877a433aa.png)

Figure 12: A person image with different ethinicity using LoRA + ControlNet


# Future Scope

While the current exploration of our text to image generation model has achieved impressive results, there is still plenty of room for future development and expansion. Some of the potential areas of growth and improvement include:

* **Enhancing image quality:** Although our model generates good-quality images, there is still potential to improve the quality of the images for group of peoples or family. 

* **Incorporating more diverse datasets:** Our current implementation uses a relatively small dataset for training the DreamBooth model (28 images). To improve the model's accuracy and versatility, we could consider incorporating larger and more diverse datasets. For example, we have to include more images which are from different angles and backgrounds.  

* **Hyperparameter Tuning:** Currently we used `sampling method` as "Euler a", "DPM++ SDE Karras " and , "DPM++ 2M Karras". We can consider the other sampling methods available such as "DDLM" ,"PLMS", "UniPC", "Heun" and more.

* **Fine-Tuning** Fine-Tuning can be done further more by changing Learning Rate, number of epochs and changing the base stable diffusion model.

# Conclusion

Text to image generation is a challenging but exciting area of research, and this repository provides a point for exploring this field. 
Using `Negative prompts`, we were able to improve the quality of the images much, especially the images with human faces. But still, there is more room to improve. This made us try other finetuning techniques like DreamBooth, LoRA, ControlNet and Textual Inversion

Stable Diffusion models tend to overfit when fine-tuning on a few images.High learning rates and too many training steps will lead to overfitting. The model will mostly generate images from your training data, no matter what prompt is used. Low learning rates and too few steps will lead to underfitting: the model will not be able to generate the concept we were trying to incorporate. Therefore, we need to select the parameters such as max_training steps and learning rate carefully.

Low learning rates and too few steps will lead to underfitting, this is when the model can not generate the trained concept.
The results of `DreamBooth` in terms of the child face are satisfying while group of peoples or famlily need to be improved. The model is able to generate images of the child without overfitting.The repository includes all the code for various models mentioned, its performance comparisons and can experiment with different parameters for corresponding models.

LoRA fineutuned on SDv1.5 are a good option when you want to train a particular person or an object. Getting good photographs from every angle is import for best results. Then by using the power of prompts and imagination we can place the person or the object at any place of position.

Textual Inversion is also a better option compare to LoRA and Stable Diffusion as the Textual Inversion Checkpoints are only of few kBs ~10kB. The Textual Inversion can also be used with negative prompts thereby enchancing the the resultant images by removing unwanted things in image.

ControlNet is the best when you want the structure or the design in the original input stays preserved.

# Reference

The entire images generated using the all API's can be found in : https://drive.google.com/drive/folders/1QlHrdWwEIANwvMpBTtkbxVQIsUrIHfPV?usp=share_link

Details about DALL E2 can be found here                         : https://openai.com/research/dall-e

Github repo for stable diffusion stable-diffusion-v1-5          : https://github.com/runwayml/stable-diffusion

Github repo for stable diffusion stable-diffusion-v1-4          : https://github.com/CompVis/stable-diffusion

Github repo for stable diffusion stable-diffusion-v2-1          :https://github.com/Stability-AI/stablediffusion

Craiyon AI (formerly DALL·E mini)                               :https://www.craiyon.com/

Training Stable Diffusion with Dreambooth using Diffusers       :https://huggingface.co/blog/dreambooth

