<div 일직선을 이루다="중심">


## 개요
YOLOv8 Aimbot은 1인칭 슈팅 게임을 위한 AI 기반 조준 봇입니다. YOLOv8 모델인 PyTorch 및 기타 다양한 도구를 활용하여 게임 내 적을 자동으로 목표로 삼고 조준합니다. 저장소에 있는 AI 모델은 Warface, Destiny 2, Battlefield 2042, CS와 같은 인기 있는 1인칭 슈팅 게임의 25,000개 이상의 이미지에 대해 훈련되었습니다.GO와 CS2.
> [!경고]
>본인의 위험을 무릅쓰고 사용하세요, 차단될 수 있다는 보장은 없습니다!

> [!참고] 
> 이 애플리케이션은 엔비디아 그래픽 카드에서만 작동합니다. AMD 지원이 테스트 중입니다. [AI_enable_] 참조AMD](https://github.com/SunOner/yolov8_aimbot?tab=readme-ov-file#ai) 옵션.
> 시작과 보다 생산적이고 안정적인 운영을 위한 추천 그래픽 카드는 rtx 20 시리즈부터 시작합니다.

## 요구사항
- 모든 설치 후 에임봇을 시작하려면 'py run.py ' 또는 'py launcher.py '를 입력하여 GUI 설정을 엽니다.

## 테스트 환경
### YOLOv8 Aimbot은 다음 환경에서 테스트되었습니다.
<표>
  <thead><tr> safe Windows</th><td>10, 11(우선순위)</td></thead>
  <thead><tr> safficles python:</th><td>3.11.6</td></tr></thead>
  <thead><tr><th>CUDA:</th><td>12.4</td></tr></thead>
 <thead><tr>swalls텐서RT:</th><td>10.0</td></tr></thead>
 <thead><tr> "Ultralytics:</th><td>8.2</td></tr></thead>
  <thead><tr> saughter Boosty AI 모델:</th><td>0.5.2</td></tr></thead>
</표>

## 옵션
Aim bot의 동작은 [`config]를 통해 구성할 수 있습니다.

### 개체 검색 창 해상도:
- detection_window_폭 'int': 개체 검색 창의 수평 해상도입니다.
- detection_window_height 'int': 개체 검색 창의 수직 해상도입니다.


### 목표:
-body_y_offset 'float': 헤드가 감지되지 않을 경우 본체 감지 상자 내부의 y 좌표를 보정할 수 있습니다.
-hideout_targets 'bool': 범위의 표적(예: 다각형의 워페이스 또는 조준랩)을 사격할 수 있습니다.
-disable_headshot 'bool': 헤드 타겟팅을 비활성화합니다.

### 단축키:
-hotkey_targeting 'str': 목표물을 조준합니다. 예를 들어 'hotkey_targeting = RightMouseButton, X2MouseButton'과 같은 멀티 키를 지원합니다.
-hotkey_exit 'str': Exit.
-hotkey_pause 'str': AIM을 일시 중지합니다.
-hotkey_reload_config 'str': 다시 로드 구성.

### 마우스:
-mouse_dpi 'int': 마우스 DPI.
-mouse_sensitivity 'float': 조준 감도.
-mouse_fov_width 'int': 게임 내 시야각의 현재 수평 값입니다.
-mouse_fov_높이 'int': 게임 내 시야각의 현재 수직 값입니다.
-mouse_lock_target 'bool': True: 한 번 누르면 영구적으로 목표물을 조준할 수 있고, 다시 누르면 조준이 꺼집니다. 거짓: 버튼을 눌러 지속적으로 목표물을 조준합니다.
-mouse_auto_aim 'bool': 자동 타깃팅.
-마우스_ghub 'bool': 마우스 이동에 로지텍 GHUB 이용을 사용합니다. 값이 False이면 Native win32 라이브러리가 이동에 사용됩니다.

### 촬영:
-auto_shoot 'bool': 자동 촬영.
-트리거봇 'bool': 대상이 범위에 있으면 자동으로 대상을 촬영하고 'mouse_auto_shoot' 옵션을 활성화해야 하며 조준도 자동으로 꺼집니다.
-force_bool을 클릭합니다. 조준경이 물체 내에 위치하지 않더라도 촬영이 수행됩니다.

### 아두이노:
-arduino_move 'bool': 마우스를 움직이도록 명령을 arduino에게 보냅니다.
-arduino_shoot 'bool': 마우스로 발사하라는 명령을 arduino에게 보냅니다.
-arduino_port 'str': 아두이노 COM port. COM1 또는 COM2를 사용합니다... 또는 auto.
-arduino_baudrate 'int': 사용자 정의 아두이노 보레이트.
-arduino_16_bit_mouse 'bool': 16비트 데이터를 arduino 포트로 전송하여 마우스를 이동시킵니다.

### AI:
-AI_model_name 'str' : AI 모델명
-AI_model_image_size 'int' : AI 모델 이미지 크기
-AI_conf 'float': 몇 %의 AI가 이것이 올바른 목표라고 확신합니까?
-AI_device 'int' 또는 'str': 실행할 디바이스, '0', '1'... 또는 'cpu'.
-AI_enable_AMD 'bool': AMD GPU를 지원합니다. ROCm, [Zluda](https://github.com/vosen/ZLUDA) 및 PyTorch를 설치합니다. [AMD docs](https://rocm.docs.amd.com/projects/install-on-windows/en/latest/how-to/install.html) 참조.
-AI_mouse_net 'bool': 신경망을 사용하여 마우스 움직임을 계산합니다.

### 디버그 창:
-show_window 'bool': 시각적 피드백을 위해 OpenCV2 창을 표시합니다.
-show_detection_speed 'bool': 디버그 창 내부의 속도 정보를 표시합니다.
-show_window_fps 'bool': 모서리에 FPS를 표시합니다.
-show_box 'bool': 탐지 가능한 개체를 표시합니다.
-show_lables 'bool': 탐지된 개체의 이름을 표시합니다.
-show_conf 'bool': 검출을 위한 객체 신뢰 임계값을 표시합니다.
-show_target_line 'bool': 마우스 피니시 라인을 표시합니다.
-show_target_prediction_line 'bool': 마우스 예측 라인을 표시합니다.
-debug_window_always_on_top 'bool': 디버그 창은 항상 다른 창 위에 있습니다.
-spron_window_pos_x 'int': 디버깅 창이 시작되면 x 위치가 됩니다.
-spron_window_pos_y 'int': 디버깅 창이 시작되면 y 위치가 표시됩니다.
-debug_window_scale_퍼센트 'int': 디버그 창의 크기를 조정합니다.
-디버깅 창의 이름은 window_name 파일에 쓸 수 있습니다.txt 그들은 무작위로 선택될 것입니다.

## AI 모델
-*.pt: 기본 AI 모델.
-*.onnx: 이 모델은 프로세서에서 실행되도록 최적화되어 있습니다.
-*.엔진: 앞의 두 가지 모델보다 빠른 최종 수출 모델입니다.

## .pt 모델을 .engine으로 내보내기
1.콘솔 창에서 모든 명령이 실행됩니다.
2.먼저 다음 명령을 사용하여 aimbot 디렉토리로 이동합니다.
'''cmd
cd C:\Users\your_username\downloads\yolov8_aimbot-main
```
3.그런 다음 .pt 형식에서 .engine 형식으로 모델을 내보냅니다.
'''cmd
yolo 내보내기 모델="models/sunxds_0.4.1.pt " 형식=엔진 장치=0 imgsz=480 half=True
```
 -"model="model_path/model_name.pt": path to model.
 -'format=engine': 텐서RT 모델 형식.
 -'half=true': 반정밀 부동 소수점 형식을 사용합니다.
 -'device=0': GPU id.
 -'workspace=8': GPU max video memory.
 -"verbose=false": 디버그 내용. 편리한 기능, 내보내기 시 오류를 나타낼 수 있습니다.

## 참고 사항 / 권장 사항
-사용할 게임에서 초당 프레임의 최대 값을 제한합니다. 또한 화면 해상도를 높게 설정하지 마십시오. 그래픽 카드에 과부하가 걸리지 않도록 합니다.
-게임에서 높은 그래픽 설정을 설정하지 마십시오.
-비디오 카드를 로드하는 브라우저를 제한합니다(예를 들어 (물론 슈퍼 슈퍼 그래픽 카드가 없는 경우).
-텐서를 사용해 보십시오.가속을 위한 RT. .pt 모델은 좋지만 엔진만큼 속도가 빠르지는 않습니다.
-cv2 디버그 창을 끄면 시스템 리소스가 절약됩니다.
-개체 검색 창 해상도를 높이지 마십시오. 검색 속도에 영향을 줄 수 있습니다.
-응용 프로그램을 시작했는데 아무 일도 일어나지 않으면 응용 프로그램이 작동하고 있을 수 있습니다. F2 키로 닫고 파일에서 'show_window' 옵션을 'True'로 변경하여 응용 프로그램이 작동하는지 확인합니다.

## 프로젝트 지원


## 면허증.
