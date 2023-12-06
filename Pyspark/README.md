## 1. Pyspark를 이용한 지하철역별 상/하차 인원 합계 계산 코드 구현 중(12.03)
- 현재 한글 인코딩 문제로 인해 아직 온전한 데이터를 이용한 기능 구현은 못했으며,<br>
23.12.04 안에 해결할 예정.
- 인코딩 문제가 해결되면 우리가 이용해야 할 모든 데이터를 Input하여,<br>
모든 년도 데이터에 승하차 인원의 합계 컬럼을 추가할 예정.<br>
![합계출력](https://github.com/wambatcodeeee/23-Data-Analytics-Project/assets/103747580/29453e5a-2f79-43b6-ae52-e6975a0f83c2)

## 2. Pyspark를 이용한 년도별 지하철역별 상/하차 인원 합계 계산 코드 구현 완료(12.04~12.05)
- 한글 인코딩 문제 해결 완료
- 22-23년도 수송일자+역명을 기준으로 시간별 상/하차 인원의 합과 하루동안 총 유동인구를 구하는 데이터 정제 구현 완료.
- 22-23년도 데이터만 정제되도록 코드를 작성한 이유는 년도별 데이터들 마다 다른 컬럼, 컬럼명, 결측치 등을 지니고 있기 때문.
  - 22-23년도 데이터 컬럼<br>
    22년도 데이터의 경우 컬럼 개수와 컬럼명은 같으나 2022-01-01~2022-05-31 사이의 24시 이후 컬럼의 값이 null임,<br>
    24시 이후의 값들은 전체적인 값들 사이에서 유의미한 값이 아님으로 판단되기에 0으로 대체함.
  ![image](https://github.com/wambatcodeeee/23-Data-Analytics-Project/assets/103747580/46a3deef-10e0-4974-a570-1c7112d7712e)
  - 19년도 데이터 컬럼(총합 컬럼이 추가적으로 존재)
  ![image](https://github.com/wambatcodeeee/23-Data-Analytics-Project/assets/103747580/0d72f0b0-b42f-4509-a065-ae3fab6cd2a5)
  - 20년도 데이터 컬럼(컬럼명이 다름)
  ![image](https://github.com/wambatcodeeee/23-Data-Analytics-Project/assets/103747580/4b6eeb78-4a2e-4e5d-94eb-395676a751fe)
  - 21년도 데이터 컬럼(24시 이후 컬럼이 없고, 총합 컬럼이 존재)
  ![image](https://github.com/wambatcodeeee/23-Data-Analytics-Project/assets/103747580/26f4db67-59c3-4c5f-9f20-bf746695e288)
- 다음 날 남은 데이터들의 정제 및 컬럼명 통일 작업에 들어갈 예정.
- 정제 결과
![정제결과](https://github.com/wambatcodeeee/23-Data-Analytics-Project/assets/103747580/27941608-b788-4a3e-8b6c-1acff4ae8ea0)

## 3. 모든 년도의 데이터에 대한 정제가 가능하도록 코드 리팩토링 완료(12.06)
- 08-23년도 까지의 모든 데이터 정제 가능해짐.
- "24시 이후" 컬럼이 비어있는 경우는 0으로 대체하는 작업을 수행함.
- 역명 컬럼에 "왕십리(성동구청)"과 같이 괄호와 괄호안에 문자열이 있는 값들을 발견,<br>
  regexp_replace 함수를 이용하여 문제를 해결함.
- 실행결과
  ![정제결과1](https://github.com/wambatcodeeee/23-Data-Analytics-Project/assets/103747580/cdab52ce-cd9b-4768-8864-e61bbe5fca1d)

