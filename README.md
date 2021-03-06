# InMoov-442
Dual kinematics/graphics repository for a plug-in for the choreonoid humanoid robotics simulation tool found at http://choreonoid.org

Done (partially) as coursework for CSE442 Software Engineering @ UB

## Installing our Choreonoid plugin

- ### Install Ubuntu 14.04 or Ubuntu 16.04

- ### Clone Choreonoid and our project repository:

  - Open the terminal and run
  
    > sudo apt-get install git

    > git clone -b beta https://github.com/TheNergaL/inmoov-442.git

    > git clone https://github.com/s-nakaoka/choreonoid.git
    
- ### Install necessary libraries and update repository

  - Ensure that you are inside the choreonoid directory and run

    > git pull

    > misc/script/install-requisites-ubuntu-14.04.sh
  
    - ##### Note that this may take some time to run this script. You will also be prompted to enter your sudo password. If you are running a free virtual machine, the password should available from the publisher site. If you run Ubuntu native, enter your sudo password.

- ### Copy plugin into choreonoid directory

  - Go into the inmoov-442 directory and run
    > cp -r MVP ~/choreonoid/sample/
    
  - You can manually copy the MVP folder in the inmoov-442 directory into the /choreonoid/sample/ directory
  
  - ### Configure Choreonoid CMAKE build flags to include plugin

  - Again, ensure you are in the choreonoid directory and run

    > cmake .
  
    > ccmake .
    
    - This should open a list of possible CMake build flags. If you are instead prompted with a message to install ccmake, do so.
  
    - Navigate down the ccmake list to the BUILD_InMoovPlugin and flag it to ON by pressing the ENTER key (if it is not already flagged for  building).
  
    - Save the configuration by pressing C and then generate the configuration by pressing G.
  
- ### Build and run Choreonoid

  - Again, ensure you are in the choreonoid directory here and run
  
    > make
  
      - ##### Note that this will take a considerable amount of time
      
  - Run Choreonoid after using this command

    > ./bin/choreonoid /sample/MVP/InMoov.cnoid
    
    
- Plugin and models should now be loaded

  - Plugin buttons are on the toolbar of choreonoid near the top
  - Buttons must be pressed multiple times to continue walking simulation

  - "SR1" buttons can only be used with the SR1 model. Use it by clicking on SR1 on the left of choreonoid to highlight it.
  - "SR1 Walk" simulates a walking animation for SR1 model.
  - "SR1 RotateRLEG" rotates SR1 model's right leg counter clockwise.
  - "SR1 RotateLLEG" rotates SR1 model's left leg counter clockwise.

  - "LEGS" buttons must be used with the LEGS model. Use it by clicking on LEGS on the left of choreonoid to highlight it.
  - "LEGS Walk" simulates a walking animation for LEGS model.
  - "LEGS Reset" resets the LEGS model back to neutral/standing position.

### The Choreonoid simulator should be up and running


Now the program is running with our working plug-in.

If at any point you encounter an error with these commands, visit http://choreonoid.org/en/manuals/1.5/install/build-ubuntu.html for debugging information.
