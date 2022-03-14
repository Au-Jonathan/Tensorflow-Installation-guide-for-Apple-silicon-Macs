# Tensorflow-Installation-guide-for-Apple-silicon-Macs
This is a step by step guide for people who want to install Tensorflow module on their M1 Macs 

Reference Articles:
[How To Install TensorFlow on M1 Mac (The Easy Way) | by Prabhat Kumar Sahu | Medium](https://caffeinedev.medium.com/how-to-install-tensorflow-on-m1-mac-8e9b91d93706)
[Tensorflow Plugin - Metal - Apple Developer](https://developer.apple.com/metal/tensorflow-plugin/)

# Step 1: Install Homebrew
Go to the website [The Missing Package Manager for macOS (or Linux) — Homebrew](https://brew.sh), copy the following into terminal:

![Screen Shot 2022-03-14 at 16 30 46](https://user-images.githubusercontent.com/91990283/158277567-bf090563-1613-4738-8a12-89da910a7043.png)

Your code should look like this: /bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"

# Step 2: Install Xcode by typing the following in terminal
xcode-select --install

# Step 3: Install Miniforge
Download “Conda env” from the link, drag it to your download folder
[Tensorflow Plugin - Metal - Apple Developer](https://developer.apple.com/metal/tensorflow-plugin/)

![Screen Shot 2022-03-14 at 16 34 50](https://user-images.githubusercontent.com/91990283/158277919-1e6563a2-cc45-4599-a0c8-af719211557e.png)

Follow the instruction on the web: copy the codes into terminal:
![Screen Shot 2022-03-14 at 16 36 23](https://user-images.githubusercontent.com/91990283/158278010-2dc41b63-7e9a-4daf-a4b5-2ecbc9fd0769.png)

chmod +x ~/Downloads/Miniforge3-MacOSX-arm64.sh

sh ~/Downloads/Miniforge3-MacOSX-arm64.sh

![Screen Shot 2022-03-14 at 16 38 27](https://user-images.githubusercontent.com/91990283/158278232-d67b83ae-27a4-4047-a8a9-b037633fdd77.png)

Keep pressing yes/enter to go on for the installation, until it ask you “Do you wish the installer to initialize Miniforge3?”
I typed no as I don’t want it to initialize every time.

# Step4: Activate the new environment miniforge3 that we have just created, then install tensorflow 

source ~/miniforge3/bin/activate

conda install -c apple tensorflow-deps

python -m pip install tensorflow-macos

python -m pip install tensorflow-metal

conda install -c conda-forge -y pandas jupyter

conda install numpy 

(At a later stage it may complain not having NumPy so we can install it beforehand) 

# Step 5: Launch Jupiter notebook and test it out 
jupyter notebook
In the notebook, try the following:
import tensorflow as tf

print(“Num GPUs Available: “, len(tf.config.experimental.list_physical_devices(‘GPU’)))

It should not return any error 

Remember to activate this environment everytime you wanna use tensorflow, Using the default one with Anaconda will always return me a dead kernel once I started to import tensorflow in Jupiter notebook 

source ~/miniforge3/bin/activate
jupiter notebook 
