# Stock_Recommendation using Sentiment Analysis(감정 분석) Project


## Stock_Recommendation by TextBlob


## Motivation

- 지난해 3월 코로나 사태로 인해 증시가 폭락하고 V자 곡선으로 회복하는 과정에서 수많은 개인들이 주식 투자에 관심을 가지고 있습니다. 금융투자협회에 따르면 2021년 3월 기준으로 주식 거래 활동 계좌수가 4000만개를 넘었으며, 이는 국내 대부분의 개인들이 주식 투자를 하고 있음을 보여줍니다. 이러한 개인들은 대부분 주식에 대해 모를 가능성이 크기 때문에 간단하게 라도 추천해줄 수 있는 프로그램을 만들면 좋지 않을까라는 질문에서 이 프로젝트를 시작했습니다.

## Sentiment Analysis 방안들 
- TextBlob 어휘사전

  + TextBlob, "Tutorial: Quickstart"을 참조하여 TextBlob 클래스를 활용하여 감성분석을 수행할 수 있습니다.

- AFINN 어휘사전

  + AFINN 어휘사전은 감성분석에 가장 단순하면서도 많이 사용되는 어휘사전입니다.

- VADER 어휘사전

  + VADER Github에 공개되어 있으며 nltk. sentiment.vader 모듈에 구현되어 있어 이를 불러 사용해도 됩니다.

- SentiWordNet 어휘사전

  + WordNet은 영어에 대한 가장 인기있는 말뭉치 중 하나입니다. WordNet은 자연어처리와 의미론 분석(semantic analysis)에 많이 활용되고, SentiWordNet 어휘사전은 감성분석에 자주 사용됩니다. SentiWordNet 웹사이트를 통해 자세한 사항을 접할 수 있으며 역시 nltk 라이브러리를 활용해서 활용이 가능합니다.

- Bing Lui 어휘사전

  + Bing Lui 어휘사전은 6,800개 단어로 구성되어 있는데 positive-words.txt는 2,000 단어/구문, negative-words.txt에는 4,800 단어/구문이 포함되어 있습니다.

프로젝트에서는 TextBlob을 사용하였다.

## TO DO LIST

- 트위터 크롤링 (완료)
- data cleaning (완료)
- sentiment anaylsis (완료)

## Goal
- 사용자가 언제부터 언제까지 크롤링 할지(예를 들어 2021-06-09부터 2021-06-12내용을 크롤링 하겠다.), 그리고 추천 받고 싶은 회사의 이름을 입력하면 아래 사진들과 같이 추천을 해주는 프로그램을 만드는 것입니다.
<img src = https://github.com/HeeJaeMon123/Stock_Recommendation/blob/main/images/Buy.PNG width="30%" height="30%">

<img src = https://github.com/HeeJaeMon123/Stock_Recommendation/blob/main/images/Not_Buy.PNG width="30%" height="30%">


## How it works? 
- twint를 이용해 크롤링을 합니다. 

  <img src = https://github.com/HeeJaeMon123/Stock_Recommendation/blob/main/images/%ED%81%AC%EB%A1%A4%EB%A7%81%20%EA%B2%B0%EA%B3%BC.PNG width="80%" height="30%">

- Data cleaning

  <img src = https://github.com/HeeJaeMon123/Stock_Recommendation/blob/main/images/data%20cleaning.PNG width="80%" height="30%">

- wordcloud로 중간 작업 출력

  <img src = https://github.com/HeeJaeMon123/Stock_Recommendation/blob/main/images/wordcloud.PNG width="30%" height="30%">

- sentiment analysis 진행(1에 가까울수록 긍정)

  <img src = https://github.com/HeeJaeMon123/Stock_Recommendation/blob/main/images/sentiment.PNG width="30%" height="30%">



## 참고 링크
크롤링시 twint 사용 https://github.com/twintproject/twint

https://github.com/erikajane/Predicting_Stock_With_Twitter_Sentiment
