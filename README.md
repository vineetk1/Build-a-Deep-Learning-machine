# Interact with Keras Model
This software is an interactive command-line program. It interacts with user-generated deep-learning keras-based models. The user does the following:
1. Build a deep-learning model using Keras 
1. Interact with the model using this interactive command-line program
## Table of contents
<!-- vim-markdown-toc GFM -->
* [Requirements](#requirements)
* [Restrictions](#restrictions)
* [Installation](#installation)
* [Usage](#usage)
	* [Start the program](#start-the-program)
	* [Help](#help)
	* [Shell](#shell)
	* [Session](#session)
	* [Load](#load)
	* [Model](#model)
	* [Layers](#layers)
	* [IO (Input/Output)](#io-inputoutput)
	* [Quit, Exit, EOF](#quit-exit-eof)
* [Contribute to improve the software and add new features](#contribute-to-improve-the-software-and-add-new-features)
* [License](#license)

<!-- vim-markdown-toc -->
## Requirements
python >= 3.5, keras >= 2.0.2, numPy >= 1.12.1  
Lower versions may work. 
## Restrictions
* Currently works with Keras Sequential Model
* Software development and testing is done on Linux OS
## Installation
Clone this repository
```
$> git clone https://github.com/vineetk1/interact-keras-model.git
```
The directory structure is as follows. The "interactKerasmodel.py" file has the main program.
```
$> cd interact-keras-model
$> ls
classes  interactKerasModel.py  LICENSE.txt  README.md
$> cd classes
$> ls
CommonModel.py  IO.py  Layers.py  Model.py  Session.py
```
## Usage
### Start the program
Run this interactive program from any directory. Note the message on "help". Enter commands following the prompt ">>" sign. 
```
$> python3 ~/interact-keras-model/interactKerasModel.py
Using TensorFlow backend.
interactKerasModel version 0.7.0, Copyright (C) 2017, Interact with Keras based model. GPL-3.0+ open-source license.
Type "help" or "?" to list commands
>>
```
### Help
Type "help". A number of commands are listed.
```
>>help
Documented commands (type help <topic>):
========================================
EOF  exit  help  io  layers  load  model  quit  session  shell
>>
```
Get help on any command. Help on the "session" command shows its usage, its description, and description of its arguments. 
