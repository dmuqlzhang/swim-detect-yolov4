# swim-detect-yolov4


## Some details
* [darknet-yolov4-install-tutorial](https://github.com/AlexeyAB/darknet#how-to-compile-on-linux-using-make)
* swim-yolov4-weights download: [BaiDuYunPan](https://pan.baidu.com/s/183sC3Xj9NULhvpy-TNhoAA) 提取码->(hzyz)
* yolov4.conv.137 -> GoogleDriver download: [yolov4.conv.137 ](https://drive.google.com/open?id=1cewMfusmPjYWbrnuJRuKhPMwRe_b9PaT)


## How to use this code (test)?
0. installed darknet-yolov4, and put darknet_API.py into ./darknet
1. put cfg into ./darknet
2. download swim-yolov4's weight, and put it in backup folder
3. Call the darknet_API main function:
    ```
    from darknet_API import Detect
    detect = Detect(metaPath=r'./cfg/swim.data', configPath=r'./cfg/yolov4-swim.cfg',\
                    weightPath=r'./backup/yolov4-swim_best.weights',\
                    namesPath=r'./cfg/swim.names')
    image = cv2.imread(r'/home/Datasets/20200714085948.jpg', -1)
    draw_img = detect.predict_image(image, save_path='./pred.jpg')
    ```

    
## How to train yolov4 in darknet (train)?
0. Convert VOC format data to YOLO format data
1. Configure file information such as cfg
2. Call the darknet command:
    ```
    ./darknet detector train cfg/swim.data cfg/yolov4-swim.cfg yolov4.conv.137 -gpus 0 -map -dont_show
    ```

## demo
* ./result: swim-detect demos

|![swim-detect-demo](https://github.com/dmuqlzhang/swim-detect-yolov4/blob/master/result/result_demo.jpg?raw=true)|
|----|


