# Tensorflow-Installation-guide-for-Apple-silicon-Macs
This is a step by step guide for people who want to install Tensorflow module on their M1 Macs 

Reference Articles:
[How To Install TensorFlow on M1 Mac (The Easy Way) | by Prabhat Kumar Sahu | Medium](https://caffeinedev.medium.com/how-to-install-tensorflow-on-m1-mac-8e9b91d93706)
[Tensorflow Plugin - Metal - Apple Developer](https://developer.apple.com/metal/tensorflow-plugin/)

Step 1: Install Homebrew, Xcode 
Go to the website [The Missing Package Manager for macOS (or Linux) — Homebrew](https://brew.sh), copy the following into terminal: 

/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"

Step 2: type the following in terminal
xcode-select --install

Step 3: Install Miniforge
Download “Conda env” from the link, drag it to your download folder
[Tensorflow Plugin - Metal - Apple Developer](https://developer.apple.com/metal/tensorflow-plugin/)

Follow the instruction on the web: copy the codes into terminal:
chmod +x ~/Downloads/Miniforge3-MacOSX-arm64.sh

sh ~/Downloads/Miniforge3-MacOSX-arm64.sh

Keep pressing yes/enter to go on for the installation, until it ask you “Do you wish the installer to initialize Miniforge3?”
I typed no as I don’t want it to initialize every time.

Step4: Activate the new environment miniforge3 that we have just created, then install tensorflow 

source ~/miniforge3/bin/activate

conda install -c apple tensorflow-deps

python -m pip install tensorflow-macos

python -m pip install tensorflow-metal

conda install -c conda-forge -y pandas jupyter

conda install numpy 

(At a later stage it may complain not having NumPy so we can install it beforehand) 

Step 5: Launch Jupiter notebook and test it out 
jupyter notebook
In the notebook, try the following:
import tensorflow as tf
print(“Num GPUs Available: “, len(tf.config.experimental.list_physical_devices(‘GPU’)))

It should not return any error 

Remember to activate this environment everytime you wanna use tensorflow, Using the default one with Anaconda will always return me a dead kernel once I started to import tensorflow in Jupiter notebook 

source ~/miniforge3/bin/activate
jupiter notebook 
