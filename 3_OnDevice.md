# 3. onDevice AI

## 1. onDevice 모델 배포
- 기기 내 머신러닝에 최적화됨, 5가지 핵심 제약사항 해결 
  - 지연 시간(서버까지의 왕복 없음)
  - 개인 정보 보호(기기에 개인 정보를 남기지 않음)
  - 연결성(인터넷 연결이 필요하지 않음)
  - 크기(모델 및 바이너리 크기 축소)
  - 전력 소비(효율적인 추론 및 네트워크 연결 불필요)
- [모바일 및 에지 기기에 머신러닝 모델 배포](https://www.tensorflow.org/lite?hl=ko&_gl=1*1toboom*_up*MQ..*_ga*MTQ4OTI4NDY5MC4xNzEwNjU3OTg0*_ga_W0YLR4190T*MTcxMDY1Nzk4NC4xLjAuMTcxMDY1Nzk4NC4wLjAuMA..)



## 2. [머신러닝 모델 최적화](https://www.tensorflow.org/model_optimization?hl=ko&_gl=1*1rup946*_up*MQ..*_ga*MTQ4OTI4NDY5MC4xNzEwNjU3OTg0*_ga_W0YLR4190T*MTcxMDY1Nzk4NC4xLjAuMTcxMDY1ODQ2MC4wLjAuMA..)
- 에지 기기에서는 메모리 또는 계산 능력이 제한된 경우가 많습니다. 
- 이러한 제약 조건 내에서도 실행될 수 있도록 다양한 최적화를 모델에 적용할 수 있습니다. 
- 또한 일부 최적화를 통해 추론 가속화를 위해 특수 하드웨어를 사용할 수 있습니다.
- [모델 최적화](https://www.tensorflow.org/lite/performance/model_optimization?hl=ko&_gl=1*adxx7l*_up*MQ..*_ga*MTQ4OTI4NDY5MC4xNzEwNjU3OTg0*_ga_W0YLR4190T*MTcxMDY1Nzk4NC4xLjAuMTcxMDY1ODMxMC4wLjAuMA..)


## 3. [하드웨어 가속](https://www.tensorflow.org/lite/performance/delegates?_gl=1*enudx3*_up*MQ..*_ga*MTQ4OTI4NDY5MC4xNzEwNjU3OTg0*_ga_W0YLR4190T*MTcxMDY1Nzk4NC4xLjAuMTcxMDY1ODMxMC4wLjAuMA..) 
- On-Device AI에서 하드웨어 가속화는 빠른 응답 시간, 저전력 소비, 고성능을 제공
- 다양한 하드웨어 가속화 기술을 활용하여 특정 응용에 최적화된 솔루션을 구현
- On-Device AI에서는 실시간 응답과 저전력 소비를 위해 딥러닝 모델을 효율적으로 실행해야 합니다. 이를 위해 <r>일반적인 CPU보다 빠르고 효율적인 하드웨어 가속기가 필요</r>합니다.
- 장점
  - 높은 성능: 병렬 처리 및 특화된 연산을 통해 딥러닝 모델을 빠르게 실행할 수 있습니다.
  - 저전력 소비: 효율적인 하드웨어 가속기는 전력 소비를 최소화하여 모바일 및 임베디드 디바이스에서도 사용 가능합니다.
  - 실시간 응답: 딥러닝 모델을 빠르게 실행하여 실시간 응답을 제공할 수 있습니다.
- 기술
  - <g>GPU (Graphics Processing Unit)</g>: 병렬 처리 능력을 활용하여 딥러닝 모델을 가속화합니다. 대용량 데이터 처리에 효과적입니다.
  - <g>TPU (Tensor Processing Unit)</g>: 텐서 연산에 특화된 하드웨어로, 고속의 행렬 곱셈 연산을 통해 딥러닝 모델을 가속화합니다. 특히 구글에서 개발한 TPU는 클라우드 환경에서 널리 사용됩니다.
  - PGA (Field-Programmable Gate Array): 프로그램 가능한 하드웨어로, 딥러닝 모델을 최적화하고 사용자 정의 연산을 지원합니다. 저전력 소비와 높은 유연성을 제공합니다.
  - ASIC (Application-Specific Integrated Circuit): 특정 응용 프로그램에 특화된 집적회로로, 딥러닝 모델을 하드웨어 수준에서 최적화하여 높은 성능과 효율성을 제공합니다.
- 적용
  - 스마트폰 및 태블릿: 모바일 기기에서 AI 기능을 실행할 때 <r>GPU 및 DSP (Digital Signal Processor)를 사용하여 하드웨어 가속화</r>를 구현합니다.
  - 자율 주행 자동차: FPGA 또는 ASIC을 사용하여 실시간 이미지 처리 및 센서 데이터 분석을 가속화합니다.
  - 스마트 홈 기기: 음성 인식 및 영상 감지를 위해 ASIC 또는 TPU를 활용하여 하드웨어 가속화를 적용합니다

<details>
<summary>적용사례</summary>

  - Apple - Neural Engine :
    - Apple은 A11 Bionic 칩부터 Neural Engine을 탑재하여 On-Device AI를 가속화합니다. Neural Engine은 머신 러닝 모델의 추론 작업을 하드웨어적으로 처리하며, 얼굴 인식, 음성 인식, 이미지 분류 등 다양한 작업에 사용됩니다. 이러한 Neural Engine의 사용으로 iPhone 및 iPad에서의 AI 응용 프로그램의 성능과 효율성이 향상되었습니다.
  - Samsung - Exynos AI :
    - 삼성은 Exynos 칩셋 시리즈에 AI 기능을 탑재하여 On-Device AI를 가속화합니다. Exynos AI는 비전 및 음성 인식, 자연어 처리 등의 작업에 특화된 하드웨어 가속기를 제공합니다.  이를 통해 갤럭시 시리즈 기기에서의 AI 기능이 향상되었으며, 카메라 기능, 보안 시스템, 음성 비서 등에 적용되었습니다.
  - Qualcomm - Hexagon DSP : 
    - 퀄컴은 Snapdragon 시리즈의 Hexagon DSP를 사용하여 On-Device AI를 가속화합니다. Hexagon DSP는 이미지 신호 처리, 음성 인식, 동영상 처리 등 다양한 AI 응용 분야에 적용됩니다. 이를 통해 안드로이드 스마트폰 및 태블릿에서 AI 기능이 향상되었으며, 카메라, 보안, 음성 인식 등에 널리 사용됩니다.
  - Huawei - Kirin NPU
    - 화웨이는 Kirin 칩셋 시리즈에 NPU(Neural Processing Unit)를 탑재하여 On-Device AI를 가속화합니다. Kirin NPU는 이미지 및 비디오 분석, 자연어 처리, 음성 인식 등 다양한 AI 작업을 지원합니다. 이를 통해 화웨이 스마트폰 및 태블릿에서의 AI 기능이 향상되었으며, 사용자 경험을 향상시키는 데 기여하고 있습니다.
</details>

---
### Reference
- [Youtube : Hardware acceleration for on-device Machine Learning](https://www.youtube.com/watch?v=iSt3fT1YsKE)


## 4. Qualcomm
- Qualcomm은 Snapdragon 시리즈의 Hexagon DSP(Digital Signal Processor)를 중심으로 On-Device AI를 가속화합니다. 이를 통해 다양한 AI 작업을 하드웨어적으로 처리하고 에너지 효율적으로 실행할 수 있습니다. Qualcomm의 On-Device AI 기술은 다음과 같은 기술들을 사용합니다.

- Hexagon DSP:
  - Hexagon DSP는 Qualcomm의 디지털 신호 처리 기술로, 다양한 AI 작업을 효율적으로 처리합니다.
  Hexagon DSP는 전용 하드웨어 가속기로, 이미지 처리, 음성 인식, 동영상 분석 등의 작업을 병렬로 처리하여 성능을 극대화합니다.
- Hexagon Vector eXtensions (HVX):
  - HVX는 Hexagon DSP의 확장 기능으로, <r> SIMD(Single Instruction, Multiple Data) 연산을 지원</r>합니다. HVX는 높은 병렬성을 제공하여 복잡한 머신 러닝 모델을 빠르게 실행할 수 있습니다.
  <details>
    <summary>주요내용</summary>  

  - 통합 및 최적화:
      - Qualcomm은 Snapdragon 시리즈의 일부로 HVX를 통합하여 효율적인 하드웨어 및 소프트웨어 최적화를 수행합니다. 이는 Snapdragon 기기에서의 성능과 효율성을 보장합니다.
      - 타사 제조사의 경우, 자체 DSP 또는 GPU에 유사한 SIMD 연산 기능을 추가할 수 있지만, Qualcomm의 통합된 설계와 최적화 수준에 도달하기는 어려울 수 있습니다.
  - 성능 및 효율성:
      - Qualcomm은 HVX를 Snapdragon 시리즈의 일부로 포함하여 전체 시스템의 성능과 효율성을 최적화합니다. 이는 모바일 디바이스에서의 AI 및 그래픽 작업에 대한 최상의 성능을 제공합니다.
      - 타사 제조사의 경우, 별도의 하드웨어 유닛을 추가해야 하거나, GPU 또는 CPU에서 추가적인 소프트웨어 최적화를 수행해야 합니다. 이로 인해 성능 및 에너지 효율성 면에서 Qualcomm의 통합된 설계와 비교할 때 제한적일 수 있습니다.
  - 생태계 및 지원:
    - Qualcomm은 Snapdragon 생태계를 바탕으로 개발자들에게 Snapdragon DSP 및 HVX를 활용한 AI 응용 프로그램을 개발할 수 있는 풍부한 지원을 제공합니다. 이는 개발자들이 빠르고 쉽게 최신 기술을 활용할 수 있도록 합니다.
    - 타사 제조사의 경우, 자체 DSP 또는 GPU에 대한 개발자 지원이 제한적일 수 있습니다. 또한, 타사 제조사의 생태계는 Qualcomm의 Snapdragon 생태계만큼 풍부하지 않을 수 있습니다.
    
  </details>
- Tensor Accelerator: 
  - 텐서 가속기는 딥 러닝 모델의 텐서 연산을 가속화하는 전용 하드웨어 유닛입니다. 이를 통해 텐서 연산을 효율적으로 수행하여 모델의 추론 속도를 높이고 에너지 소모를 줄일 수 있습니다.
  <details>
    <summary>주요내용</summary>
  
  - 텐서 연산에 특화된 설계: Tensor Accelerator는 텐서 연산을 하드웨어 수준에서 효율적으로 처리할 수 있도록 최적화된 설계를 가지고 있습니다. 이를 통해 딥 러닝 모델의 학습 및 추론 작업을 가속화할 수 있습니다.
  - 고성능 및 저전력: Tensor Accelerator는 고성능을 제공하면서도 저전력으로 동작할 수 있도록 설계되었습니다. 이는 모바일 디바이스와 같은 에너지 제약이 있는 환경에서 중요한 요소입니다.
  - 텐서 형식 지원: Tensor Accelerator는 다양한 텐서 형식을 지원하여 다양한 딥 러닝 모델을 처리할 수 있습니다. 예를 들어, 다차원 배열 형식인 텐서를 효율적으로 처리할 수 있습니다.
  - 하드웨어 및 소프트웨어 통합: Tensor Accelerator는 주로 하드웨어 수준에서 동작하지만, Qualcomm과 같은 기업은 이를 통합 소프트웨어와 함께 제공하여 개발자가 쉽게 활용할 수 있도록 지원합니다.
  </details>
- Qualcomm AI Engine:
  - Qualcomm은 Hexagon DSP, CPU, GPU 및 NPU(Neural Processing Unit)를 통합하여 AI Engine을 제공합니다.
  AI Engine은 다양한 하드웨어 리소스를 동시에 활용하여 복잡한 AI 작업을 효율적으로 처리합니다.
- 통합 소프트웨어 및 SDK:
  - Qualcomm은 개발자들이 Snapdragon 기반 디바이스에서 On-Device AI를 개발할 수 있도록 통합된 소프트웨어 및 SDK를 제공합니다.
  이를 통해 개발자들은 편리하게 디바이스 내에서 AI 모델을 실행하고 최적화할 수 있습니다.


