# video link will be added once the video published

None of the things in this tutorial won't affect your other installations such as Stable Diffusion

### Part 1 - Preparing training speech files
We will begin with pre-processing the speech training file

First accept the license terms on https://huggingface.co/pyannote/segmentation 

So you must have a free hugging face account to accept terms. Register hugging face : https://huggingface.co/join

To do that we will git clone and install ozen toolkit : https://github.com/devilismyfriend/ozen-toolkit

commit id : f5ea2ce4f95bfa54635ec9deac56cb546aa7d516

```git clone https://github.com/devilismyfriend/ozen-toolkit```

To be able to use this, you need to have installed Anaconda or Miniconda with Python 3.10
Anaconda download and install link : https://www.anaconda.com/download
Miniconda download and install link : https://docs.conda.io/en/latest/miniconda.html

If you fail to install Anaconda here my tutorial where I installed and shown : https://www.youtube.com/watch?v=YJebdQ30UZQ

Then double click and run "Set Up Ozen.bat" file inside directory 

Lets say something went wrong and you want to reinstall or, you had installed this repo before and you want to reinstall, then Anaconda will give you this message

```CondaValueError: prefix already exists: C:\Users\King\miniconda3\envs\ozen```

So open folder ```C:\Users\King\miniconda3\envs``` and delete the ```ozen``` directory 

Then after installation drag and drop the training speech file into Drag_Here.cmd

It will ask you hugging face token get it here : https://huggingface.co/settings/tokens

Merge multiple audio files into a single file : ```ffmpeg -i "concat:input1.mp3|input2.mp3|input3.mp3" -acodec copy output.mp3```


There are several key issues. It uses by default large model. If your GPU is not 12 GB you can either use CPU to transcribe or you can use medium or small model

Whisper tutorial : https://www.youtube.com/watch?v=msj3wuYf3d8

```
tiny	39 M	tiny.en	tiny	~1 GB	~32x
base	74 M	base.en	base	~1 GB	~16x
small	244 M	small.en	small	~2 GB	~6x
medium	769 M	medium.en	medium	~5 GB	~2x
large	1550 M	N/A	large	~10 GB	1x
```

Moreover, its transcribed txt file has encoding problem. So copy a all change encoding and paste again and save as I have shown in the tutorial video. I had to spend quite a bit time to find out this.

If you ever needed to install a missing package manually, to activate anaconda or miniconda venvs you need to open a anaconda cmd and type the generated venv name like

```conda activate ozen```

```pip uninstall torch```

https://pytorch.org/

```pip3 install torch==1.13.1 torchvision torchaudio --index-url https://download.pytorch.org/whl/cu117```

Notepad++ to change transcription file encoding : https://notepad-plus-plus.org/downloads/ 

### Part 2 - Doing training and training settings

We will use DL-Art-School for training. It has a very nice GUI and makes training piece of cake

https://github.com/152334H/DL-Art-School

This also requires Anaconda or Miniconda with Python 3.10

Since we already installed it in the previous step you don't have to install again

If you want to reinstall this then you need to delete the venv generated in miniconda venvs

```C:\Users\King\miniconda3\envs```

Do git clone

```git clone https://github.com/152334H/DL-Art-School```

Double click Setup DLAS.bat 

It will make a venv in anaconda or miniconda and install everything. 

However you may encounter an error like i did related to torch. So we will reinstall torch manually

If you ever needed to install a missing package manually, to activate anaconda or miniconda venvs you need to open a anaconda cmd and type the generated venv name like

```conda activate DLAS```

```pip uninstall torch```

```pip3 install torch torchvision torchaudio --index-url https://download.pytorch.org/whl/cu118```

After installation double click "Start DLAS.cmd" file and it will open the GUI interface

Follow the steps I have shown in the video to start training
