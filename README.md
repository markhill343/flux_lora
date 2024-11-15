![FluxDevFp8_00448_](https://github.com/user-attachments/assets/cab044b8-28bc-4f90-a2d2-d219664c966e)# Diving into Consistent Product Image Creation with Flux

Hey everyone!

I've been using my downtime before starting my master's thesis to dive into the world of local fine-tuning of generative models. 🎓 This post is all about **creating LoRAs for product images using Fluxgym**, and I thought it'd be fun to share my journey with you!

---
![Screenshot from 2024-11-15 15-05-57](https://github.com/user-attachments/assets/7492bccb-7857-472a-ac88-ecc105504e44)

## So, What's a LoRA Anyway?

Before we jump in, let's break it down:

- **LoRA (Low-Rank Adaptation)**: Think of it as a way to fine-tune large models efficiently by adding a small number of trainable parameters. It's like giving your model a quick, focused lesson without having to retrain the whole thing.
- **Fine-Tuning**: Adjusting all the parameters of a pre-trained model—which can be a real time and resource sink.

Basically, **LoRAs let you customize models without the heavy lifting**, making it way more accessible.

---

## Getting Started: What You'll Need

### Hardware:

- **GPU**: Preferably an NVIDIA GPU with **12GB VRAM** or more.

### Software:

- **Operating System**: **Ubuntu** with **CUDA** and **PyTorch** installed.
- **Fluxgym**: Our main tool for creating LoRAs. Grab it here: [Fluxgym GitHub Repository](https://github.com/cocktailpeanut/fluxgym)
- **Kohya's SD Scripts**: The brains behind Fluxgym's UI. Check them out: [Kohya's SD Scripts GitHub Repository](https://github.com/kohya-ss/sd-scripts/tree/sd3)
- **ComfyUI**: For loading the LoRA and generating images afterward. Find it here: [ComfyUI GitHub Repository](https://github.com/comfyanonymous/ComfyUI)

### Data:

- **10-30 Images **:
![10](https://github.com/user-attachments/assets/8faf2178-b52c-4e9a-9eb4-2e7f12d122cd)

---

## Step 1: Preparing Your Images

First up, gather images of your product. For the best results:

- **Crop the Images**: Focus on the product itself. **512x512 pixels** works great.
- **Backgrounds**: You can try a clean, consistent background or mix it up with diverse ones. Feel free to experiment and see what works best!

---

## Step 2: Generating Image Captions

Captions are super important for guiding the model. Here's what you can do:

- **Use the Same Caption**: Fluxgym can handle it if you want to keep things simple.
- **Provide Varied Descriptions**: Give each image a unique caption to enrich the training data.

**Pro Tip:** Use **Florence 2**, built right into Fluxgym, to automatically generate image captions. It saves time and keeps things consistent. **Just make sure to double-check the captions afterward—sometimes they might be a bit off!**

---

## Step 3: Setting Up Fluxgym

Let's get Fluxgym up and running:

1. **Install Fluxgym** by following the instructions on the [GitHub page](https://github.com/cocktailpeanut/fluxgym).
2. **Adjust the Settings** to suit your needs:
   - **Learning Rate**: I went with **1e-4 ~ 8e-4**.
   - **Repeat Count**: How many times each image is trained per epoch.
   - **Number of Epochs**: I chose **10**.

Feel free to tweak these settings—they can affect training time and how well your model performs.

---

## Step 4: Training Your LoRA

Now for the exciting part!

- **Start Training**: Kick off the process
- **Monitor Progress**: On my 4070 Ti, it took about **1 hour**.
- **Energy Consumption**: Approximately **0.124 kWh**—pretty efficient!

---

## Step 5: Loading into ComfyUI

Time to see your model in action:

- **Load it into ComfyUI**:
- **Generate Some Examples**: Watch your custom model bring your product to life!

*Check the end of this post for GitHub links and the ComfyUI workflow attached.*

I was thrilled to see the rubber duck rendered in various styles and settings. The possibilities are endless!
![Screenshot from 2024-11-15 14-42-35](https://github.com/user-attachments/assets/03a37837-2528-40dc-a225-015864f45b47)
![FluxDevFp8_00454_](https://github.com/user-attachments/assets/8186efc8-359e-4f02-a0a2-3672fbc740ba)
![FluxDevFp8_00448_](https://github.com/user-attachments/assets/b5ebcc11-a058-4221-a837-3c12c08a80a1)
![FluxDevFp8_00452_](https://github.com/user-attachments/assets/7a2635c0-22cf-421a-b33a-e06fd76727d7)
![FluxDevFp8_00450_](https://github.com/user-attachments/assets/99880d04-7c77-4088-9395-6e895c55723a)

---

## Wrapping Up

This journey into local LoRA creation has been both educational and a ton of fun. Being able to customize generative models locally opens up so many possibilities for product imagery and more.



---

## Useful Links:

- **Fluxgym GitHub Repository**: [https://github.com/cocktailpeanut/fluxgym](https://github.com/cocktailpeanut/fluxgym)
- **Kohya's SD Scripts**: [https://github.com/kohya-ss/sd-scripts/tree/sd3](https://github.com/kohya-ss/sd-scripts/tree/sd3)
- **ComfyUI GitHub Repository**: [https://github.com/comfyanonymous/ComfyUI](https://github.com/comfyanonymous/ComfyUI)

Feel free to reach out if you have questions or want to share your own experiences. **Happy fine-tuning!** 🚀

--
