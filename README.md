# Face Tracking and Projection with Kinect

The above code is a project focused on projecting a face or 'mask' on to another person in real time. This project will track a person's face using an Xbox Kinect V2 made by Microsoft and project using a standard 1080p projector. This project is in conjunction with the Rensselaer Polytechnic Institute Players for their show of Sweeney Todd. The project built using Unity 2018.2.1f1 but should be compatible with all of Unity 2018.2.x. This project can be controlled using either the keyboard or through OSC. The documentation of those can be found bellow. 

## Getting Started

The following documentation will walk you through the deployment of the project as well as any other tools or necessities required for operation of the project in a show or performance environment.

## System Requirements
#### Unity
To use this project, you will need Unity. You can download the newest version of Unity [here](https://unity3d.com/get-unity/download); however, the specific version is Unity 2018.2.1f1 which can be found at the bottom of this [archive](https://unity3d.com/get-unity/download/archive).  This project should be compatible with all Unity 2018.2 versions however it has not been tested outside of the given version.

#### Kinect
This project uses the Kinect v2 SDK. The SDK can be downloaded [here](https://www.microsoft.com/en-us/download/details.aspx?id=44561). Due to this dependency, this program can only be run on Windows 8 and above. There is no plan to remove this dependency.

#### Projector
Any projector can be used for this project. This project outputs to the project as a second display and does not interface directly.

#### Network
This project uses OSC to comunicate remotely. To use OSC you must be able to send and connect between devices over either wifi or ethernet

#### Recommended Computer Hardware
* 64 bit processor
* 4gb of ram
* DX11 capable graphics adapter
* USB 3.0 
* 1.5 Gigabytes of hard disk space

## Deployment
#### Installation
Downloaded the latest bin located in the `bin/` folder or if you would like to you can download the source code in the src folder

#### Kinect Installation
To set up the Kinect, you must supply it power and plug it into any USB 3.0 port on the computer. To test the Kinect, you can run the `Kinect Studio 2.0` which comes with the installation of the  Kinect SDK v2.  

#### Running
Run the executable `Kinect Face Cap.exe` and select which display to output. This display should be your projector. 

## Documentation
#### Key Commands
Please refere to the following for all key commands
##### Display Commands
| Key           | Command      |
| ------------- |:-------------:|
| W      | Move the display closer to the face|
| A      |  Move the display farther from the face|
| S      | Move the display to the left of the face|
| D      | Move the display to the right of the face|
| Q      | Rotate the display counter-clockwise|
| E      | Rotate the display clockwise |
| Z      |  Pan the display left|
| X      |  Pan the display right|

##### Face Commands
| Key           | Command      |
| ------------- |:-------------:|
| Space     | Turn on/off the display|
| P      |  Go to the next texture|

#### OSC implementation
There are two functions in this OSC Implementation.

The first is to turn on and off the display. The display is controlled through the `/osc/display/` address and uses the value `1` to display and `0` to turn off the display.

The second is to control which mask is being displayed. This is used through the `/osc/mask/` address and can either take the number of the mask, i.e. mask one would use the value `1` or the command `next` which would go to the next mask.