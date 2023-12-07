# 한밭대학교 SW중심대학 산학연계프로젝트 - 생성 모델 워터마킹 연구

## **팀 구성**
### 지도교수
 - 장한얼 교수님

### 기업체 
 - 박주한 대표

### 참여학생
 - 30211054 이인수
 - 20191785 이지상
 - 20191766 김동수
 - 20211915 오서연
 - 20191747 이지준
 - 20191120 이용빈
 - 20191780 육정훈

## Project Background
- ### 필요성
  - 생성 모델이 만든 콘텐츠 저작권 및 구매자 정보를 확인하기 위해 생성 모델 워터마킹 기술을 연구하여 창작자의 정보를 비가시적으로 삽입 및 추출한다.
- ### 기존 해결책의 문제점
  - 기존 워터마킹 기술은 생성 모델에 최적화되지 않음
  - 온라인 유통 시에 발생하는 왜곡에 대해서 강인한 워터마킹 기술 필요
  
## System Design
  - ### System Requirements
    - 생성 모델 워터마킹 연구 및 성능 평가
    
## Case Study
  - ### Description
    - 본 과제에서는 생성 모델 zero-bit 워터마킹 연구를 수행하였다.
    - Zero-bit 워터마킹이란 워터마크 존재 시 1, 없으면 0으로 출력하는 이진 분류 과업이다.
    - 생성 모델 zero-bit 워터마킹은 생성 모델이 생성한 이미지이면 1, 아니면 0으로 출력하는 과업이다. 즉, 생성 이미지 판별 문제로 정의할 수 있다.
    - 온라인 상에서 빈번하게 발생하는 이미지 크기 변환과 절삭에 대해서 강인한 생성 이미지 판별 연구를 수행하였다.
  - ### Method
    - 1) 아래 그림과 같이 이미지 크기 변환과 절삭을 이용하여 데이터 증대를 수행한다.
      - ![image](https://github.com/HBNU-SWUNIV/INDPROJ23-aimlab/assets/14088046/986817d6-96a8-447a-899d-81a28727582d)
      - ![image](https://github.com/HBNU-SWUNIV/INDPROJ23-aimlab/assets/14088046/87e56c53-0c07-47ef-b11a-f06adf20eaf9)
    - 2) 생성 이미지에서 발생하는 고주파 대역의 비정상적인 특징을 효과적으로 탐지하기 위해 고속 푸리에 변환(FFT)과 이산 코사인 변환(DCT)를 사용하여 데이터 전처리를 수행한다.
      - ![image](https://github.com/HBNU-SWUNIV/INDPROJ23-aimlab/assets/14088046/52020172-dc4a-43d7-b98c-3ae73150afc7)
      - ![image](https://github.com/HBNU-SWUNIV/INDPROJ23-aimlab/assets/14088046/662ffa4c-cfce-427f-918b-4cb529e5633f)
    - 3) 데이터 증대한 이미지와 주파수 변환한 이미지를 입력값으로 사용하는 생성 이미지 zero-bit 워터마킹 모델(EfficientNet-B0)을 학습한다.
      - ![image](https://github.com/HBNU-SWUNIV/INDPROJ23-aimlab/assets/14088046/f77211c4-5994-4a5b-b1cc-712b7caedb6a)
  - ### Experimental Results
    - 1) 아래 표는 이미지 크기 변환과 절삭을 이용하여 데이터 증대를 수행한 실험결과이다.
      - ![image](https://github.com/HBNU-SWUNIV/INDPROJ23-aimlab/assets/14088046/5114484a-d038-4a82-841e-6e6e00c90c48)
    - 2) 아래 표는 고속 푸리에 변환(FFT) 사용 유무에 따른 zero-bit 워터마킹 실험결과이다.
      - ![image](https://github.com/HBNU-SWUNIV/INDPROJ23-aimlab/assets/14088046/c34b188d-e8f4-4a04-b51f-4baf5d0386da)
    - 3) 아래 표는 이산 코사인 변환(DCT) 사용 유무에 따른 zero-bit 워터마킹 실험결과이다.
      - ![image](https://github.com/HBNU-SWUNIV/INDPROJ23-aimlab/assets/14088046/945a2e90-b23d-42d5-a0bc-e92d88b4a1d5)
    - 4) 아래 그림은 고속 푸리에 변환(FFT) 사용 유무에 따른 주파수 이미지 비교 결과이다.
      - ![image](https://github.com/HBNU-SWUNIV/INDPROJ23-aimlab/assets/14088046/d7fe7359-d16d-4fb9-a560-c2cb7396c152)
    - 5) 아래 그림은 이산 코사인 변환(DCT) 사용 유무에 따른 주파수 이미지 비교 결과이다.
      - ![image](https://github.com/HBNU-SWUNIV/INDPROJ23-aimlab/assets/14088046/2de15204-4dff-4ed8-88e5-1bab1b339043)
  
## Conclusion
  - 고속 푸리에 변환과 이산 코사인 변환 실험 결과로 주파수 영역에서의 변환을 통해 생성 이미지의 패턴과 특성을 더 잘 감지하고 이를 기반으로 생성 이미지 zero-bit 워터마킹을 수행할 수 있음을 확인하였다.
  
## Project Outcome
- ### 2023년 한국디지털포렌식학회 동계학술대회 발표
- ### 2023년 한국디지털포렌식학회 동계학술대회 학회장상 수상
