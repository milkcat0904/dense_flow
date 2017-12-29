Extracting dense flow field given a video.
=

#### Depencies:
- LibZip: 
to install on ubuntu ```apt-get install libzip-dev``` on mac ```brew install libzip```

#### For OpenCV 3 Users
Please see the [opencv-3.1](https://github.com/yjxiong/dense_flow/tree/opencv-3.1) branch. Many thanks to @victorhcm for the contributions!

A.下载 Download
=
    $ git clone --recursive http://github.com/yjxiong/dense_flow


B.安装 Install
=

#### 1.在下载包的目录下执行cmd:
        $ mkdir build 
    
        $ cd build
        
        $ cmake .. 
        
#### 2.修改```build```文件夹中的```CMakeCache.txt```文件,将参数置为```OFF```
#### （当执行make -j出现Error:cannot find -lopencv dep_cudart时）

![image](https://github.com/milkcat0904/dense_flow/raw/master/pic/参数.png)

        $ make -j

C.使用
=

    $ ./extract_gpu -f test.avi -x tmp/flow_x -y tmp/flow_y -i tmp/image -b 20 -t 1 -d 0 -s 1 -o dir

    - `test.avi`: input video
    - `tmp`: folder containing RGB images and optical flow images
    - `dir`: output generated images to folder. if set to `zip`, will write images to zip files instead.

D.Warp Flow
=

    The warp optical flow is used in the tsn model


    To extract warp flow, use the command

    $ ./extract_warp_gpu -f test.avi -x tmp/flow_x -y tmp/flow_y -i tmp/image -b 20 -t 1 -d 0 -s 1 -o dir

