# Raspi4-OpenCV

- 설치 참조 링크 1 : https://make.e4ds.com/make/learn_guide_view.asp?idx=116
- 설치 참조 링크 2 : https://webnautes.tistory.com/916
- 기존 자료 : https://github.com/JinFree/OpenCV_in_Ubuntu


- 상황 : 하위패키지들이 설치되지 않음 -> OpenCV 컴파일 에러 설치 안됨.
- 타임서버 문제인듯 하여 집에가서 재시도 예정

```
/home/pi/opencv/opencv_contrib-4.1.2/modules/xfeatures2d/src/boostdesc.cpp:654:20: fatal error: boostdesc_bgm.i: No such file or directory
           #include "boostdesc_bgm.i"
                    ^~~~~~~~~~~~~~~~~
compilation terminated.
make[2]: *** [modules/xfeatures2d/CMakeFiles/opencv_xfeatures2d.dir/build.make:81: modules/xfeatures2d/CMakeFiles/opencv_xfeatures2d.dir/src/boostdesc.cpp.o] Error 1
make[1]: *** [CMakeFiles/Makefile2:4681: modules/xfeatures2d/CMakeFiles/opencv_xfeatures2d.dir/all] Error 2
make: *** [Makefile:163: all] Error 2
pi@raspberrypi:~/opencv/opencv-4.1.2/build $ 

```
