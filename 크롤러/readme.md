
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
