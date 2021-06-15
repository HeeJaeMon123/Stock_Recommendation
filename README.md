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

프로젝트에서는 TextBlob을 사용하였습니다.

## TO DO LIST

- 트위터 크롤링 (완료)
- Data Cleaning (완료)
- Sentiment Anaylsis (완료)

## 소개 및 결과 이미지
- 사용자가 언제부터 언제까지 크롤링 할지(예를 들어 2021-06-09부터 2021-06-12내용을 크롤링 하겠다.), 그리고 추천 받고 싶은 회사의 이름을 입력하면 감정분석을 진행하고 긍정적 tweet의 개수가 부정적 tweet의 개수의 3배 보다 많으면 추천을 해주는 프로그램을 만드는 것입니다.
<img src = https://github.com/HeeJaeMon123/Stock_Recommendation/blob/main/images/Buy.PNG width="30%" height="30%">

<img src = https://github.com/HeeJaeMon123/Stock_Recommendation/blob/main/images/Not_Buy.PNG width="30%" height="30%">

## 특징
- 감정 지수(점수)는 -1~1까지 있는데 1에 가까울수록 긍정, -1에 가까울수록 부정입니다. 여기서 저만의 지표를 만들었는데 소개에서 말했듯이 만약 감정 점수가 0.2이상 이라면 pos_score를 1씩 증가시키고 -0.2이하라면 neg_score를 1씩 증가시키고 pos_score가 neg_score의 3배 보다 많으면 YES_BUY + 회사이름을 wordcloud에 출력


## How it works? (기능 부분)
- twint를 이용해 크롤링을 합니다. 

  <img src = https://github.com/HeeJaeMon123/Stock_Recommendation/blob/main/images/%ED%81%AC%EB%A1%A4%EB%A7%81%20%EA%B2%B0%EA%B3%BC.PNG width="80%" height="30%">

- Data cleaning(학습에 도움 되지 않는 단어들(링크, 리트윗) 제거, 모든 tweet 소문자로 만들어주기, lemmatize 진행, stopwords 제거)

  <img src = https://github.com/HeeJaeMon123/Stock_Recommendation/blob/main/images/data%20cleaning.PNG width="80%" height="30%">

- Wordcloud로 중간 작업 출력

  <img src = https://github.com/HeeJaeMon123/Stock_Recommendation/blob/main/images/wordcloud.PNG width="30%" height="30%">

- Data cleaning finish(회사이름 , 회사 ceo 이름 제거)

  <img src = https://github.com/HeeJaeMon123/Stock_Recommendation/blob/main/images/finish.PNG width="80%" height="30%">


    
- Wordcloud로 출력

  <img src = https://github.com/HeeJaeMon123/Stock_Recommendation/blob/main/images/10.PNG width="30%" height="30%">

    위의 그림에서 ev나 de, e 같은 불용어 처럼 보이는 것을 제거하지 않은 이유는 (lol같이) 제가 모르는 감탄사 일수도 있을것 같아 제거하지 않았습니다. 

- Sentiment Analysis 진행(1에 가까울수록 긍정)

  <img src = https://github.com/HeeJaeMon123/Stock_Recommendation/blob/main/images/sentiment.PNG width="30%" height="30%">



## 참고 링크
크롤링시 twint 사용 https://github.com/twintproject/twint

https://github.com/erikajane/Predicting_Stock_With_Twitter_Sentiment (data cleaning, 그래프 참고)
