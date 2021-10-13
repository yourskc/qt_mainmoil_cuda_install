# qt_mainmoil_cuda_install

A Qt_mainmoil_cuda installer run on NVIDIA Jetson TX2 or PC with Ubuntu 18.04


<img src="document/images/screen2.gif">


##1. NVIDIA Jetson TX2

1. NVIDIA Jetson TX2 Force Recovery Mode
 
>	1. Press and hold down the Force Recovery button.

>	2. Press and hold down the Power button.

>	3. Release the Power button, then release the Force Recovery button.

2. NVIDIA SDK Manager and JetPack 4.6

>	Connect host and target with USD cable

>	Download and run NVIDIA SDK Managesr on host(Ubuntu 18.04) 

>	https://developer.nvidia.com/embedded/jetpack

>	https://developer.nvidia.com/nvidia-sdk-manager

By default OpenCV 4.1.1 and CUDA 10.2 already be installed on the target 
NVIDIA Jetson TX2

3. Download 

>	git clone https://github.com/yourskc/qt_mainmoil_cuda_install.git

>	cd qt_mainmoil_cuda_install
 
4. Install Qt5 runtime 

>	sudo apt install qt5-default

5. Install 

>	cd tx2

>	sudo ./install.sh

6. Run

>	mainmoil_cuda 

browse to and open the sample data image.jpg 


##2. PC with Ubuntu 18.04


1. Install Opencv from source ( recommand 4.3.0 )

>	The basic guide to install the latest OpenCV.

>	https://linuxize.com/post/how-to-install-opencv-on-ubuntu-18-04/

In the build step, please use the parameters

	cmake -D CMAKE_BUILD_TYPE=RELEASE \
	-D CMAKE_INSTALL_PREFIX=/usr/local \
	-D OPENCV_GENERATE_PKGCONFIG=ON \
	-D INSTALL_PYTHON_EXAMPLES=ON \
	-D INSTALL_C_EXAMPLES=ON \
	-D OPENCV_ENABLE_NONFREE=ON \
	-D WITH_CUDA=ON \
	-D WITH_CUDNN=ON \
	-D OPENCV_DNN_CUDA=ON \
	-D ENABLE_FAST_MATH=1 \
	-D CUDA_FAST_MATH=1 \
	-D CUDA_ARCH_BIN=6.1 \
	-D WITH_CUBLAS=1 \
	-D OPENCV_EXTRA_MODULES_PATH=../../opencv_contrib/modules \
	-D HAVE_opencv_python3=ON \
	-D PYTHON_EXECUTABLE=/usr/bin/python3 \
	-D WITH_GSTREAMER=ON \
	-D BUILD_EXAMPLES=ON ..


*notice : for CUDA_ARCH_BIN parameter, please check the architecture version for your 

particular ( https://developer.nvidia.com/cuda-gpus ), for examples, 6.1 for Geforce 

GTX 1060, 6.2 for Jetson TX2, 7.5 for Gefore RTX 2080 Ti.

2. Install CUDA 10.2 ( necessory, even if without NVIDIA graphic card )

>	https://developer.nvidia.com/cuda-10.2-download-archive

3. Install Qt5 runtime 

>	sudo apt install qt5-default

4. Install 

>	cd ubuntu

>	sudo ./install.sh

5. Run

>	mainmoil_cuda 

>	in case of can't find OpenCV library, you can

>	export LD_LIBRARY_PATH=/usr/local/lib

>	or sudo add the line "LD_LIBRARY_PATH=/usr/local/lib" to /etc/environment then reboot


<a href="https://youtu.be/FlaG7w-JT9Q"> Demo Video 01</a>

[![IMAGE ALT TEXT HERE](https://img.youtube.com/vi/FlaG7w-JT9Q/0.jpg)](https://youtu.be/FlaG7w-JT9Q)

<a href="https://youtu.be/sx6WaPc6Tkg"> Demo Video 02</a>

[![IMAGE ALT TEXT HERE](https://img.youtube.com/vi/sx6WaPc6Tkg/0.jpg)](https://youtu.be/sx6WaPc6Tkg)







