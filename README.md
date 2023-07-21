# Arcade-map-recognizer
Ai that can recognize arcade maps(Pacman, Galaga and Donkey Kong)

## Download Model Here:
https://drive.google.com/drive/folders/1nGSUHf7eu91Z2qjBtZs05_a4g67G6UAm?usp=sharing  

## How it works

  The program works with image recognition in the jetson interface library. You can see the code there. The pretrained models didn't have classes for arcade games,  so I identified new ones for them. I used the reclassification notebook on google colab to train the model of arcade images I found online. This program can be used for new comers for arcade games to help them idetentify which arcade games are which.

## The Algorithm 

  The program looks at a screenshot from a arcade game, and tells you which one it is from. There are screenshots of each game that I used for the program in the training file, where it uses transfer learing, while the validation images are used to evaluate the accuracy during the training process, afterward you can use the test images.

## How to run

  1.Make sure you have Jetson Nano with the Jetson inference library and Python3 installed on you system

  2.Make a arcade_maps folder in the models directory at jetson-inference/python/training/classification/models
  
  3. Put model_best.pth.tar and resnet18.onnx in jetson-inference/python/training/classification/models/arcade_maps

  4.Set the variables as `NET=models/arcade_maps` and `DATABASE=data/arcade_maps` in the terminal

  5.Open your terminal and type in `imagenet.py --model=$NET/resnet18.onnx --input_blob=input_0 --output_blob=output_0 --labels=$DATASET/labels.txt $DATASET/test/~/~.jpg arcade.jpg`
In the first ~ type in one of the three games, the games being donkey_kong, pacman, or galaga, and in the second ~ type in the name of the jpg.  If you would like to add your own screnshot of one of the games, add it in the test file of the data folder.

  6.If you want to add your own image add the screenshot to the test folder and rename the screeenshot.
