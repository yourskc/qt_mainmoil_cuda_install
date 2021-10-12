# qt_mainmoil_cuda_install

A Qt_mainmoil_cuda installer run on NVIDIA Jetson TX2 or PC with Ubuntu 18.04.

##1. NVIDIA Jetson TX2

1.1 install JetPack 4.6

Hardware reset Jetson TX2, prepare a Ubuntu 18.04 host, 

follow the instructions to setup NVIDIA Jetson TX2 by using 

NVIDIA SDK Manager:

https://developer.nvidia.com/embedded/jetpack

By default OpenCV 4.1.1 and CUDA 10.2 already be installed on the target 
NVIDIA TX2

1.2 Download 

>	git clone https://github.com/yourskc/qt_mainmoil_cuda_run
>	cd qt_mainmoil_cuda_run
 
1.3 Install Qt5 runtime ( if you have installed Qt5 before, please skip )

>	sudo apt install qt5-default

1.4 Install 

>	cd tx2
>	sudo ./install.sh

1.5 Run

>	mainmoil_cuda 

browse to and open the sample data image.jpg 


##2. PC with Ubuntu 18.04


2.1 Install Opencv from source ( recommand 4.3.0 or newer )

2.2 Install CUDA 10.2

2.3 Install Qt5 runtime ( if you have installed Qt5 before, please skip )

>	sudo apt install qt5-default

2.4 Install 

>	cd ubuntu
>	sudo ./install.sh

2.5 Run

>	mainmoil_cuda 






