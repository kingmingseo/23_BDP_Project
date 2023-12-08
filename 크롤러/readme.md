
<h2>특정 검색어와 날짜에 따른 뉴스title, 뉴스Link, 뉴스Content 크롤러 제작</h2>

![검색](https://github.com/kingmingseo/23_BDP_Project/assets/101965138/f95a34d2-311b-4036-be83-692f898da29f)
![검색결과](https://github.com/kingmingseo/23_BDP_Project/assets/101965138/ebd37b14-9f9d-4282-89ce-4ae3495ec3fc)
![실제 결과](https://github.com/kingmingseo/23_BDP_Project/assets/101965138/53e6874f-f8fb-4172-9889-f54ceac8a618)

<hr>
<h2>특정 검색어와 날짜가 입력 대신 csv의 컬럼 데이터로 대체하고 원하는 형식으로 들어가게 업데이트</h2>

![image](https://github.com/kingmingseo/23_BDP_Project/assets/101965138/4471fd0c-2940-4a94-ab9e-4d3d70cfcd4c)

csv 파일의 역명과 날짜를 통해서 뉴스기사를 크롤링 하도록 수정

하나의 날짜와 역명을 기준으로 title에 여러 기사들의 제목을 리스트 내부에서 '|' 문자로 구분 , 뉴스 링크는 뉴스 title과 인덱스로 일대일 대응하며 동일하게 리스트에 차곡 차곡 push

이제 pyspark를 통해 데이터를 정제하고 이상치 기준에 따라 이상치를 구분해 낸 뒤 
이상치로 밝혀진 역과 날짜로 크롤링을 하면 그 날의 지하철 유동인구가 유난히 적거나 많았던 원인을 기사를 통해 알아 낼 수 있다. 

<hr>
<h2>네이버에 요청하는 request를 줄이고 referer를 추가(밴 방지), 뉴스 데이터가 없는 경우에는 view탭의 글을 크롤링 하도록 기능 추가구현 </h2>
데이터의 이상치를 분석해 본 결과 어떠한 행사나 사건때문에 확실히 인원이 많았던 날이 있는데, 뉴스 기사가 없어서 원인을 파악하지 못한<br>
경우가 있음. -> 뉴스데이터가 없으면 여러 사람들이 글을 올리고 리뷰하고 후기를 남기는 view탭의 글들을 활용 
실행결과<br>
![image](https://github.com/kingmingseo/23_BDP_Project/assets/101965138/090d0b85-c9b0-469b-9990-a9119192a2f7)

예시로 10개의 날짜를 크롤링 한 결과 뉴스가 있으면 뉴스데이터 없으면 view탭의 블로그나 글들을 크롤링해오는 것을 확인할 수 있다.
