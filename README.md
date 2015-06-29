# Octoduino
[![Build Status](https://travis-ci.org/NETponents/octoduino.svg?branch=master)](https://travis-ci.org/NETponents/octoduino)
## What is it?
Octoduino is a program for the Arduino that allows you to run script files from an SD card.

## What languages are supported?
None right now. We are still in the early stages of development, so we're trying to perfect the underlying framework first. Once we get that out of the way, we can get started working on individual languages.

### Fully supported

### Partially supported

### On the drawing board
- BASIC
- NODE.JS
- Ruby
- Arduino (C++)

## Getting started
Want to get started using Octoduino? Great! Here's how to get started:

### Prerequisites
- A supported MCU*
- A shield that can interface with an SD card
- An SD card, at least 512 MB but 4 GB (some shields don't support larger cards)
- A computer with the Arduino IDE installed and an SD card reader
- USB type B cable (the one that came with your Arduino)

#### *A note about device selection
Any Arduino-certified device that supports shields should work. Please note that Leonardo and Yun are not supported at this time. Some "tiny" Arduinos will not work due to size constraints.

Although not officially supported or tested, any Energia-capable TI MSP430 MCU should also work assuming there is enough space for Octoduino. It may be possible to use external EEPROM depending on the capabilities of the MCU. Also be aware that Octoduino will run MUCH slower on non-ATmega MCUs.

Here is a list of certified Arduino devices that are tested on every build in our CI environment:
- Arduino UNO V3
- Arduino Decimila
- Arduino Mega

### 1. Installing Octoduino
Grab a copy of our code from GitHub:

     git clone http://github.com/NETponents/octoduino.git

Then go ahead and open the sketch using your favorite Arduino IDE. Go ahead and deploy it to your Arduino. If you hit an error, reset your Arduino and make sure that no shields are attached. If you are still hitting errors, file a bug on our GitHub page <http://github.com/NETponents/octoduino/issues>. Be sure to leave information about your Arduino and your IDE!

### 2. Creating the config files
Now that your Arduino is ready to go, let's get the SD card ready. Insert the card into your computer. Make sure the card is COMPLETELY empty. Then format it as 'FAT32' or 'FAT16'. We reccommend 'FAT32' as it is newer and slightly faster. Once that is complete, create a new file named 'octoduino.ini'. Open it using your favorite text editor. Copy the following code, replacing anything between {} with your own parameters (do not include the brackets). If you are unsure of what to put, see the language-specific options in the **~/Docs** folder.

     language={ your language id }
     output=true
     debug={ set to true for debug messages }
     start={ The source file to be executed }

### 3. Uploading your code files
Now you can begin to upload your code files. For a simple NODE.JS program, your SD card would look like this:

     + root
     |-- octoduino.ini
     |-- program.js
     |-+ inc
       |-- library.js

### 4. Run your program
Make sure you have a serial console open to your Arduino. Insert the SD card an reset your Arduino. You should begin to see your program get executed. Yay! If you hit a bug that was not caused by your code, be sure to let us know by filing a bug in our issue tracker.

## Contributing
We welcome contributions of all kinds. This project follows the NETponents RING system.

#### Ring 2
If you are not in rings 1 or 0, you are in ring 2. Ring 2 is the public ring. Here's how contributtions work in Ring 2:
- To make changes, you must fork the project to your own account.
- Since we don't know you, permanant forking of this project is not allowed.
- When you open a PR, you will be given lowest priority (unless it is a bug patch).

#### Ring 1
This is a ring of trusted developers. We give them the **Collaborator** badge on the issues page, and give them some perks:
- To make changes, you still have to fork the project to your own account.
- With a project administrators permission, you may create a permanent fork of the project (as long as you adhere to the terms in LICENSE.md).
- When you open a PR, you will be given medium priority (unless it is a bug patch).
- In the issues section of the project, you will be given the **Collaborator** badge.
- You get added as a member (NOT employee) of the NETponents organization.

#### Ring 0
This ring is closed to the public. This ring contains employees of NETponents. Full admin access is given, however new progress must be done on a separate branch.

### Getting promoted
Put simply, if you show interest in the project, contribute regularly, and follow all the guidelines for contributions, you'll get promoted in no time.

### Contributing guidelines
We are very strict in terms of how everything is documented on GitHub. For full details, please view this projects *~/CONTRIBUTING.md*.
