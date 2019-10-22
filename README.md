# TrackStim
micro-manager plugin to image moving C.Elegans


## Index Of Topics
1. Requrired software
2. Required hardware
3. Building and installing TrackStim
4. Running TrackStim
5. Troubleshooting Common Behaviours
6. Development guide/documentation
7. Setting up the hardware and software from scratch


### Required software

All items except Mac OS X 10.7 can be found in this repository under the ```required software``` directory.
Ask the IT department for Mac OS X 10.7

- Mac OS X 10.7 Lion
- USB to UART Bridge VCP Driver Legacy Version for Mac OSX
- DCAM API for Mac OS X 10.7 v13.11.4451
- Java 6 (this should come with Mac OS X 10.7, but if its not installed, you can download it here: https://support.apple.com/kb/dl1572?locale=en_GB) 
- Micro-manager 1.4.22


### Required hardware
- Hamamatsu orca R2 camera
- Hamamatsu orca R2 camera controller C10600
- Thor Labs CM1-DCH/M SM1A23
- Thor Labs M00267820
- ASI MS-2000-500 xy stage (Serial: 1004-1620-2933-2148, Model: WKU-XYB-Zs-Axioskop2+)
- A mac with a firewire ieee 1394 port/cable

### Building and installing TrackStim

##### Building Trackstim

To build TrackStim download/git clone this folder an then open a terminal window with this folder.

Then, run the following command sequence in the terminal.  Note - you need Java 1.6:

```sh
javac -source 1.5 -target 1.5 -classpath /Applications/Micro-Manager1.4/ij.jar:/Applications/Micro-Manager1.4/plugins/Micro-Manager/MMCoreJ.jar:/Applications/Micro-Manager1.4/plugins/Micro-Manager/MMJ_.jar -Xlint:unchecked TrackStimPlugin.java

jar cvf TrackStim_.jar TrackStimPlugin.class TrackStim_04.class TrackingThread11.class SignalSender01.class
```

This creates ```TrackStim_.jar```.  


##### Installing Trackstim 
Take ```TrackStim_.jar``` and copy it to ```/Applications/Micro-Manager1.4/mmplugins/```.  To confirm that it is installed, open the Micro-Manager -> Plugins menu.  There should be an entry called ```TrackStim```.



### Running TrackStim
1. Open Micro-Manager 1.4
2. Choose the configuration file in this repository i.e (trackstim-mm1.4.21mac.cfg)
3. Click on the group setting ```hamamatsu_property_test```
4. Click on the preset ```NewPreset```
5. Click the "live" button on the left side of the Micro-Manager windows
6. Open Micro-Manager 1.4 -> Plugins menu
7. Choose TrackStim

TODO
- more detail
- guide for static imaging
- guide for calcium imaging
- guide for behaviour analysis

### Troubleshooting Common Behaviours
In it's current state, TrackStim is an unstable program.  Performing multiple acquisitions sequentially may not be possible depending on the settings you use.

If TrackStim does not work when you are are running it or if there are errors when you start it, here are some things you an do:
1. ensure that the camera and stage are both connected to the mac and turned on
2. quit Micro-Manager and TrackStim and open them again
3. if you encounter errors where TrackStim or Micro-Manager won't start, shutdown your computer and restart it.

### Development Guide/Documentation
TODO
- design diagrams
- algorithm documentation
- options documentation
- camera settings documentation

### Setting up the TrackStim system from scratch
1. Install Mac OS X 10.7 
2. Download the first software update (installs a new version of safari that most sites support)
3. Install Google Chrome
4. Install the rest of the required software
5. Open iChat -> Settings -> Camera -> toggle the setting off (e.g. Do not open iChat when the camera turns on) **Important, camera will not be detected by Micro-Manager 1.4 if this is not done** )
6. plug in all of the hardware components
7. build TrackStim
8. install TrackStim


