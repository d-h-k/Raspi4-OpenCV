# Raspi4-OpenCV

## 맷플랏 설치
- 데탑
```
pip install matplotlib
```





- 라즈4
```
pip3 install matplotlib
```



## 에필로그
> 참고사이트
- https://blog.xcoda.net/97 
- http://wearedev.net/217?PHPSESSID=06e960d955e2edd5a897ab3699ec5500 
- https://github.com/sunkyoo/T_Academy_Python_OpenCV 
- https://www.youtube.com/watch?v=95d_MwXCGhc&list=RDCMUCtV98yyffjUORQRGTuLHomw&index=3 

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
- OpenCV 설치는 크게 두가지 방법으로 나뉨 
  - 하나는, 직접 빌드하는 방법/ 다른하나는 바이너리 파일을 설치하는 방법으로
  - 라즈베리파이4로 나오면서, 변경점이 조금 있어서 직접 빌드하는 방법은 현제 문제가 있음
  - 바이너리 다운받는거는 데스크탑 환경에 주로 제공되는데, 다행이 최근에 업데이트된 버전에서 OpenCV4를 라즈베리4에서 설치 가능하도록 패치됨(우왕굿..)
- 하지만, 빌드하면 장점이, @@@가 있음
- 빌드해서 환경구성하면 최소 4시간인데, 빡세게 OpenCV돌릴려면 이런것도해야하긴 하다.. 근데.. 
## 환경설정
> 라즈4에 OpenCV4 설치, 20-05-29 기준
- 업데이트 한번
```
sudo apt-get update
```
- 의존성 패키지 설치
```
sudo apt install -y libxine2  libqtgui4 libjasper1 libqt4-test libqt4-opengl
```
- 댜운로드 릴리즈 download this release file, opencv4.2.0.deb.tar
```
wget https://github.com/dltpdn/opencv-for-rpi/releases/download/4.2.0_buster_pi3b/opencv4.2.0.deb.tar
```
- 압축풀기
```
tar -xvf opencv4.2.0.deb.tar
```
- 다운받은 데비안 패키지 설치
```
sudo apt-get install -y ./OpenCV*.deb
```
- 버전확인
```
pkg-config --modversion opencv4
```
- 실행 결과
  - 4.2.0

- 파이썬을 실행해봅시다
```
python3
```
- 파이썬 아이들에서 아래 코드 실행(실패시...)
```
import cv2
cv2.__version__
```
- 위 줄을 입략햐 아래 명령어가 나옴을 확인
- '4.2.0'

```
OpenCV의 이미지 기본
기술 요구 사항
이미지 기본에 대한 이론적 소개
이미지 처리의 주요 문제
이미지 처리 단계
이미지 공식
픽셀, 색상, 채널, 이미지 및 색상 공간의 개념
파일 확장자
OpenCV의 좌표계
OpenCV에서 픽셀 액세스 및 조작
BGR 이미지를 사용하여 OpenCV에서 픽셀 액세스 및 조작
그레이 스케일 이미지로 OpenCV에서 픽셀 액세스 및 조작
OpenCV의 BGR 주문
요약
질문
추가 자료
```