# nlp_for_korean
한국어 자연어처리를 위한 repo

1.make_korean_tokenizer

Korean corpus에 pretokenizer(mecab)로 교착어의 조사, 복합명사를 분절한 후 huggingface의 tokenizers와 sentencepiece로

subword를 학습한 후 속도를 비교


![initial](https://github.com/keep-steady/NLP_for_korean/blob/main/1.make_korean_tokenizer/img/img2.png)

![initial](https://github.com/keep-steady/NLP_for_korean/blob/main/1.make_korean_tokenizer/img/img1.png)

![initial](https://github.com/keep-steady/NLP_for_korean/blob/main/1.make_korean_tokenizer/img/img3.png)



# Konlpy 사용법

konlpy_사용법.ipynb

### install
python -m pip install konlpy # https://konlpy.org/ko/v0.5.2/install/#ubuntu

### 사용법
https://mr-doosun.tistory.com/22

### 결과 비교 - Okt가 단어를 글자단위로 분해해서 적절해 보인다
- Hannanum(6.87s/1000sentence) : ['37', '.', '다음', '은', '3D', '애니메이션', '제작', '을', '위하', 'ㄴ', '계획', '의', '일부', '이', '다', '.', '윗글', '을', '바탕', '으로', '하', 'ㄹ', '때', '적절', '하', '지', '않', '은', '것', '은', '?', '[', '3점', ']']

- Kkma(1min 57s/1000sentence) : ['37', '.', '다음', '은', '3', 'D', '애니메이션', '제작', '을', '위하', 'ㄴ', '계획', '의', '일부', '이', '다', '.', '윗', '글', '을', '바탕', '으로', '하', 'ㄹ', '때', '적절', '하', '지', '않', '은', '것', '은', '?', '[', '3', '점', ']']

- komoran(3.23/1000sentence) : ['37', '.', '다음', '은', '3D', '애니메이션', '제작', '을', '위하', 'ㄴ', '계획', '의', '일부', '이', '다', '.', '윗', '글', '을', '바탕', '으로', '하', 'ㄹ', '때', '적절', '하', '지', '않', '은', '것', '은', '?', '[', '3', '점', ']']

- Okt(11.2s/1000sentence) : ['37', '.', '다음', '은', '3', 'D', '애니메이션', '제작', '을', '위', '한', '계획', '의', '일부', '이다', '.', '윗', '글', '을', '바탕', '으로', '할', '때', '적절하지', '않은', '것', '은', '?', '[', '3', '점', ']']
