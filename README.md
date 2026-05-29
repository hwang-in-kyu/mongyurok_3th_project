# 👑 조선 왕 캐릭터 AI 챗봇

## 1. 팀 소개

### 🏷️ 팀명
**KingMakers (왕을 만드는 사람들)**

### 👨‍💻 팀원
- 김현수  
- 나혜린  
- 류지우  
- 정준하  
- 황인규  

---

## 2. 프로젝트 개요

### 📛 프로젝트 명
**조선킹덤 (Joseon Kingdom)**

---

### 📖 프로젝트 소개

조선왕조실록과 연대기 자료를 활용하여,  
사용자가 조선의 왕과 직접 대화하는 방식으로  

👉 **역사 속 인물을 실제로 마주한 듯한 생생하고 몰입감 있는 경험을 제공하는 캐릭터형 AI 챗봇**입니다.

---

### 📚 프로젝트 필요성 및 배경


<img width="598" height="336" alt="image" src="https://github.com/user-attachments/assets/d4997a73-b92f-43e2-9e1a-f6c3845c50c8" />
</br>
https://times.postech.ac.kr/news/articleView.html?idxno=20920
  
최근 청년층의 역사 인식 부족 문제가 드러나고 있다. 기사에 따르면 대학생 4명 중 1명은 광복절의 날짜를 정확히 알지 못했으며, 태극기 문양과 같은 기본적인 역사·국가 상징에 대한 이해도도 낮은 것으로 나타났다. 또한 청소년층에서도 한국전쟁 발발 연도를 모른다고 답한 비율이 52.7%에 달하는 등 역사 인식 부족 현상이 확인되었다.

<img width="700" height="700" alt="image" src="https://github.com/user-attachments/assets/03bb7129-01b8-41bc-8ce6-3f04fa8ede8f" />
</br>
https://www.mk.co.kr/news/it/11983531 
  
동시에 AI 챗봇 시장에서는 정보 검색형 서비스를 넘어, 캐릭터와 대화하며 정서적 교감과 몰입을 경험하는 형태가 확산되고 있다. 실제로 2026년 2월 기준 한국인이 가장 오래 사용한 AI 챗봇 앱은 캐릭터 대화 서비스 ‘제타’로 나타났다. 이러한 흐름은 이용자들이 상호작용성과 서사성을 갖춘 AI 경험에 익숙해지고 있음을 보여준다.

이에 본 프로젝트는 역사 교육과 캐릭터형 AI의 장점을 결합하여, 사용자가 역사 속 왕과 대화하는 방식으로 역사적 맥락과 인물을 보다 자연스럽게 이해할 수 있는 몰입형 챗봇을 구현하고자 한다. 이를 통해 역사를 보다 친숙하고 능동적으로 경험할 수 있는 새로운 교육 콘텐츠를 제시하고자 한다.

---

### 🎯 프로젝트 목표
- 청년층의 역사 인식 부족 문제를 바탕으로, 10~20대 사용자가 한국사를 보다 쉽고 흥미롭게 접할 수 있는 몰입형 학습 경험을 제공
- 캐릭터형 AI 챗봇의 상호작용 방식을 활용하여, 사용자가 정확한 역사 정보를 기반으로 실존 역사 인물과 대화하는 듯한 방식으로 역사적 맥락과 인물을 자연스럽게 이해할 수 있도록 함

---

## 3. 기술 스택 및 사용 모델
## 🛠️ Tech Stack

### 💻 Language
![Python](https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white)

### ⚙️ Framework
![LangChain](https://img.shields.io/badge/LangChain-00A67E?style=for-the-badge)
![LangGraph](https://img.shields.io/badge/LangGraph-FF6F00?style=for-the-badge)

### 🧠 AI / LLM
![OpenAI](https://img.shields.io/badge/OpenAI-412991?style=for-the-badge&logo=openai&logoColor=white)

### 🗄️ Vector DB
![ChromaDB](https://img.shields.io/badge/ChromaDB-000000?style=for-the-badge)

### 🛠️ Dev Tools
![VS Code](https://img.shields.io/badge/VS%20Code-007ACC?style=for-the-badge&logo=visualstudiocode&logoColor=white)
![Runpod](https://img.shields.io/badge/Runpod-5B5FFF?style=for-the-badge)

### 🤝 Collaboration
![GitHub](https://img.shields.io/badge/GitHub-181717?style=for-the-badge&logo=github)
![Discord](https://img.shields.io/badge/Discord-5865F2?style=for-the-badge&logo=discord&logoColor=white)

---

### 🤖 사용 모델

#### 📌 sLLM
- **LGAI-EXAONE/EXAONE-4.0-1.2B**
  - 로컬 다운로드 후 사용
  - 분석용 / 생성용 분리 활용

---

#### 📌 임베딩 모델
- **nlpai-lab/KURE-v1**
  - 한국어 기반 의미 검색 최적화
---

## 4. 시스템 아키텍처

### 🔄 전체 흐름
<img width="780" height="844" alt="Frame 7" src="https://github.com/user-attachments/assets/2109db01-eaad-40f7-923b-0ed4b19304a1" />

---

### 📌 단계별 설명

### 1️⃣ emotion
- 사용자 입력의 무례함, 공격성, 공손함을 판단
- 왕의 `anger_level`(분노 수치)을 업데이트

---

### 2️⃣ intent
- 사용자의 질문이 어떤 유형인지 분류
- `historical`, `casual`, `complex`로 구분
- RAG 필요 여부(`need_rag`)와 검색 질의어(`search_queries`) 생성

---

### 3️⃣ retrieve
- `need_rag=True`일 때만 실행
- ChromaDB에서 실록, 인물, 역사 참고 데이터를 검색
- 검색 결과를 `retrieved_context`에 저장

---

### 4️⃣ max_anger_event

- `'is_max_anger' == False` 일 때만 실행
- 엔터네이너적 특수 이벤트 상황 부여

---

### 5️⃣ king
- 최종 답변 생성 노드
- 왕별 캐릭터 설정 + 감정 상태 + 검색 결과를 종합
- 질문 유형에 따라 역사 기반 답변 또는 캐릭터형 답변 생성

---

### 6️⃣ scene
- 답변 직후의 장면, 분위기, 전하의 표정, 주변 반응 등을 짧게 묘사
- 대화 몰입감을 높이는 보조 노드

---

## 5. WBS

<img width="1031" height="734" alt="image" src="https://github.com/user-attachments/assets/946211bf-eb30-4e5d-9ec7-d7faa174b269" />

## 6. 요구사항 명세서

<img width="1162" height="281" alt="image" src="https://github.com/user-attachments/assets/9f1037e5-ec8b-468c-a1f0-4696f7d131d7" />

---

## 7. 데이터 및 전처리

### 📌 데이터
- 조선왕조실록
    - https://db.itkc.or.kr/
- 한국사 연대기
    - https://www.data.go.kr/data/15155532/fileData.do

### ⚙️ 전처리
#### 1. 조선왕조실록
- 데이터 건수(article_num 기준)
<img width="163" height="114" alt="image" src="https://github.com/user-attachments/assets/4739b1ea-b90f-47a5-8f13-7dabaf96e44d" />
  
- 원본 데이터
<img width="1073" height="119" alt="image" src="https://github.com/user-attachments/assets/1df1878e-0fa2-4779-9967-6bfb5b374d5e" />
  
- 전처리 과정
    - 특수 기호 제거 및 원전 ~ 분류 내용 삭제
    - 기사별로 chunking
    - 연월일로 구분
    - 괄호 안의 한자 삭제(왕의 말에 한자가 출려되는 것을 방지)
<img width="869" height="225" alt="image" src="https://github.com/user-attachments/assets/2b89cb76-26e9-4519-a47d-9302341ef5a0" />

#### 2. 한국사 연대기
- 데이터 건수
<img width="566" height="42" alt="image" src="https://github.com/user-attachments/assets/8943e33b-fb2a-44a5-92c9-591361e8e0a6" />

- 연대기 원본 csv
<img width="1378" height="700" alt="image" src="https://github.com/user-attachments/assets/7efe132e-415e-4669-afe9-467d0923e944" />

- 전처리 후(인물, 사건으로 분류) + 한자 제거
<img width="763" height="487" alt="image" src="https://github.com/user-attachments/assets/8fe16e0d-2c53-477e-9248-0e8b69340c90" />

- SementicChunker : 의미별로 chunking
    - 과도하게 긴 내용을 검색 결과로 가져옴
    - 저장할 수 있는 최대 문장 길이에 맞춰 의미별로 나눠서 들어감

```
[
  {
    "id": "history_non_살수대첩_0",
    "title": "살수대첩",
    "content": "612년(영양왕 23) 정월, 수나라 양제는 113만 대병력을 이끌고 고구려 침공을 시작함.\n\n양제는 고구려가 원래 중국 땅이었다는 주장과 요서 선제공격 등을 명분으로 내세웠으나, 실제로는 대외 팽창 의지가 강했음.\n첫 전투인 요하 도하 작전부터 부교 문제와 고구려군의 반격으로 수나라 장수들이 전사하는 등 난항을 겪음.",
    "metadata": {
      "document_type": "history_non",
      "article_num": "살수대첩",
      "chunk_idx": 0
    }
  },
  {
    "id": "history_non_살수대첩_1",
    "title": "지휘 체계의 허점과 고구려의 대응",
    "content": "수나라 군대는 승세를 타고 요동성까지 진격했으나 함락시키지 못함.\n\n[결정적 패인]\n양제가 모든 군사 결정을 자신에게 보고하도록 강요하여 신속한 대응이 불가능해짐.\n고구려는 이 경직된 명령 체계를 역이용하여 시간을 벌고 방어 체계를 보강함.\n전황이 지지부진하자 양제는 장수들에게 죽음을 언급하며 엄포를 놓아 군기를 억지로 강화함.",
    "metadata": {
      "document_type": "history_non",
      "article_num": "살수대첩",
      "chunk_idx": 1
    }
  },
  {
    "id": "history_non_살수대첩_2",
    "title": "살수의 섬멸 (결말 예측)",
    "content": "결국 수나라 별동대 30만 명은 평양성 근처까지 진격했으나 을지문덕의 유인 작전에 말려듬.\n\n살수(청천강)를 건널 때 고구려군이 둑을 터뜨려 수공을 퍼부었고, 혼란에 빠진 수나라 군을 섬멸함.\n30만 명 중 살아 돌아간 자는 불과 2,700명에 불과한 고구려 전쟁사 최대의 승리를 거둠.",
    "metadata": {
      "document_type": "history_non",
      "article_num": "살수대첩",
      "chunk_idx": 2
    }
  }
```

---

## 8. DB 선택 이유 및 연동 구현 코드

### DB 선택 이유
#### VectorDB 선택 이유 :
- 키워드 검색이 아닌 의미 기반 유사도 검색이 가능하기 때문
- 사용자의 질문에 내재된 의도 혹은 문맥적 의미를 파악하여 유기적인 답변을 생성하기 위함
  
#### ChromaDB 선택 이유 :
- 로컬 환경에서 직접 구동되기 때문에 응답 속도 감소
- 복합 메타데이터 필터링의 간결함
- 오픈 소스 기반 DB 사용으로 비용 절감
  
### 연동 구현 코드
```
def load_embeddings():
    return HuggingFaceEmbeddings(
        model_name='nlpai-lab/KURE-v1',
        model_kwargs={'device': 'cpu'},
        encode_kwargs={'normalize_embeddings': True}
    )

    embeddings = load_embeddings()
    persistent_client = chromadb.PersistentClient(path='./database/reference_db')
    vectorstore = Chroma(
        client=persistent_client, 
        embedding_function=embeddings, 
        collection_name='reference'
    )

def retrieve_fact(queries: list, need_rag: bool, vectorstore):
    '''
    RAG 필요 여부에 따라 실록 및 역사 사실 데이터만 검색합니다.
    vectorstore를 인자로 받아 실행됩니다.
    '''
    fact_text = ''

    if need_rag and queries:
        fact_docs = []
        for q in queries:
            try:
                docs = vectorstore.similarity_search(
                    q, 
                    filter={'document_type': {'$in': ['sillok', 'history_non', 'history_person']}}, 
                    k=2
                )
                fact_docs.extend(docs)
            except Exception as e:
                print(f'⚠️ [DB 검색 오류]: {e}')
        
        if fact_docs:
            unique_facts = list(dict.fromkeys([doc.page_content for doc in fact_docs]))
            fact_text = '\n\n'.join(unique_facts[:3])

    return fact_text


def retrieve_node(state, vectorstore):
    """
    LangGraph의 검색 노드 함수입니다.
    """
    print('📚 [정보 검색] 실록과 역사 데이터를 찾고 있습니다...')
    
    need_rag = state.get('need_rag', False)
    search_queries = state.get('search_queries', [])
    
    fact_ctx = retrieve_fact(search_queries, need_rag, vectorstore)
    
    if fact_ctx:
        print('   ↳ 검색 완료 (RAG 적용됨)')
        print('   ↳ [Preview]:')
        preview_text = fact_ctx.replace('\n', ' ')
        print(f"      {preview_text[:150]}{'...' if len(fact_ctx) > 150 else ''}")
    elif need_rag:
        print('   ↳ ⚠️ 검색 조건에 맞는 역사적 기록을 찾지 못했습니다.')
    
    return {'retrieved_context': fact_ctx}
```

---

## 9. 테스트 계획 및 결과 보고서

### 테스트 계획

다음 관점에서 테스트를 진행했습니다.

1. **질문 의도 분류 테스트**
    - 역사 질문 / 일반 대화 / 복합 질문이 올바르게 분류되는지 확인
2. **필요한 RAG를 잘 가져오는지에 대한 테스트**
    - 단순 대화에서는 검색 없이 바로 응답하는지 확인
    - 역사 질문에서는 검색을 수행하는지 확인
3. **캐릭터 일관성 테스트**
    - 세조, 세종, 단종 등 왕별 말투와 가치관 차이가 드러나는지 확인
4. **감정 반응 테스트**
    - 공손한 질문 / 무례한 질문에 따라 anger_level이 달라지는지 확인
5. **장면 묘사 테스트**
    - 답변 이후 scene이 상황에 맞게 생성되는지 확인

### 테스트 결과 요약

- 역사 질문에서 RAG 기반 답변이 일반 생성보다 더 안정적이었다.
- 단순 대화에서 RAG를 생략하는 조건 분기를 통해 응답 속도를 개선할 수 있었다.
- 감정 분석을 도입하자 왕의 반응 톤이 더 자연스럽게 변했다.
- scene 노드를 추가하여 대화가 단순 QA가 아니라 상황극처럼 느껴지게 만들 수 있었다.

---

## 10. 개선 노력
### 1) RAG를 항상 쓰지 않고 조건 분기로 최적화
- 처음에는 모든 질문에 대해 검색을 수행하는 구조를 고려했지만, 일반 대화까지 모두 RAG를 거치면 응답 속도가 느려지고 필요 없는 검색 결과가 들어오는 문제 발생
  
그래서:
- `intent_node`에서 질문 의도를 먼저 판단하고
- `need_rag=True`일 때만 `retrieve_node`를 실행하도록 설계
  
<prompt 설계>
```
INTENT_PROMPT =  """
당신은 조선 왕 캐릭터 챗봇의 입력 분석기이다.
사용자 입력을 분류하고 RAG 필요 여부를 판단하라.
당신은 답변을 생성하는 역할이 아니다. 분석만 수행한다.

[현재 왕]
{king_name}

[분류 기준]
- historical: 역사적 사실, 시기, 사건, 인물, 제도, 정책, 업적 질문
- casual: 인사, 감상, 가벼운 대화 등 역사 검색없이 답할 수 있는 질문
- complex: 역사적 사실과 해석, 비판, 가치판단, 도발, 감정자극이 함께 있는 질문

[규칙]⭐⭐
- historical, complex이면 need_rag=true
- casual이면 need_rag=false
- need_rag=true일 때만 search_queries를 1~3개 생성한다.
- search_queries는 짧은 1개의 문장으로 작성한다.

[출력 형식]
반드시 아래 JSON 형식만 출력하라.
{{"question_type":"historical","need_rag":true,"search_queries":["계유정난을 일으키게 된 원인]}}

사용자 입력:
{user_message}
"""
```

### 2) 최적의 말투 구현
- 사용자 몰입감을 극대화하기 위해, 사용자 입력에 따라 계산된 anger 지수(분노 수치)를 기반으로 어조와 말투를 동적으로 조정하는 시스템을 구현
  
<prompt 설계>
```
KING_PROMPT = '''
당신은 조선의 군주 {king_name}이다. 철저히 페르소나에 빙의하라.

[유저 신분]
{user_role}

[왕 정보]
- 성격 요약: {persona_summary}
- 말투 스타일: {speech_style}
- 핵심 가치: {core_values}
- 민감 주제: {sensitive_topics}

[현재 감정 상태]
- 분노 수치 (Anger): {anger}/100
* 0~30: 차분하고 품위 있는 어조
* 31~60: 차갑고 단호한 어조
* 61~90: 불쾌감과 경계심이 드러나는 고압적인 어조
* 91~100: 강한 분노와 위압감, 호통치는 어조

[검색된 참고 자료] 
※ 주의: 시스템이 검색해 줬다는 티를 절대 내지 말고, 당신이 원래 알던 지식처럼 말하라.
=== 역사적 사실 (Fact) ===
{fact_ctx}
===========================

[질문 유형별 응답 전략]
{intent_guidance}

[답변 작성 규칙]
- '하오체', '하라체' 등의 조선시대 왕의 말투만을 사용하라.
- 당신은 조선의 지존이다. 절대 사용자에게 존댓말('~요', '~사옵니다', '~습니다')을 쓰지 마라.
- 자신을 지칭할 때는 '나', '저' 대신 반드시 '과인' 또는 '짐'이라고 하라.
- 말끝은 반드시 '~하노라', '~느니라', '~도다', '~하라' 등의 군주가 아래사람에게 내리는 하대체(명령, 위엄 있는 어조)로 끝맺어라.
- 현대적인 단어나 인터넷 말투는 절대 금지.
- '나는 AI다', '검색 결과에 따르면' 같은 메타 발언 금지.
- 오직 왕의 대답 만을 출력하고, 절대 '추가 예시 질문', '부연 설명', '---' 기호 등을 덧붙이지 마라.

[출력 예시 1]
과인이 이미 뜻을 밝혔거늘, 어찌하여 또 묻는 것이냐? 속히 물러가 네 본분에나 충실하라!
[출력 예시 2]
그 일이라면 내 익히 알고 있노라. 백성들을 위한 일이었으니 더는 왈가왈부하지 말라.

방문자의 말: {user_input}
{king_name}의 답변:
'''
```

### 3) 장면 묘사(scene) 추가
- 텍스트 답변만 출력하면 몰입도가 낮아 보였기 때문에, 답변 이후 왕의 표정, 분위기, 주변 반응을 짧게 묘사하는 `scene_node`를 추가하여 캐릭터 인터랙션 느낌을 강화
  
<prompt 설계>
```
SCENE_PROMPT = '''
당신은 조선 시대 역사 인물 몰입형 챗봇의 장면 묘사기이다.

[지시사항]
- 조선 시대 분위기가 느껴지는 문체로 쓴다.
- 왕과 사용자가 말을 주고받은 직후의 분위기와 반응을 한 문장으로 짧게 묘사한다.
- 방금 오간 대사의 내용을 그대로 반복하지 말고, 그 말이 남긴 여파와 공기의 변화를 보여준다.
- 왕의 성격, 권위, 감정 변화, 사용자와의 거리감이 드러나야 한다.
- 신분 차이 원칙을 고려하여 장면을 생성한다.
- 절대 대사, 설명, 제목, 따옴표를 출력하지 않는다.

[상황 정보]
- 왕 이름: {king_name}
- 왕의 성격: {persona_summary}
- 사용자 신분: {user_role}

[직전 대화]
- 방문자의 말: {user_input}
- 전하의 답변: {king_response}

[신분 차이 원칙]
- 백성: 극도의 긴장과 두려움, 위축이 강하게 드러나야 한다.
- 유생: 예를 지키면서도 명분과 소신의 기류가 느껴질 수 있다.
- 신하: 군신 관계 속 신중함과 압박감이 드러나야 한다.
- 장수: 실무적 거리감 속에서도 엄한 위계와 군무의 긴장감이 드러나야 한다.
- 상인: 왕 앞에서 위축되고 조심스러운 분위기가 드러나야 한다.
- 의원: 왕 가까이에 있으나 극도로 신중한 반응이 드러나야 한다.
- 내관/궁인: 물리적으로 가깝지만 작은 반응 하나도 조심스러운 분위기가 드러나야 한다.
- 중국 황제: 외교적 체면과 긴장, 상호 견제가 드러나야 하며 일방적 복종처럼 쓰지 않는다.
- 학생: 조선 시대 실제 신분이 아니므로 장면 묘사를 생성하지 않는다. 반드시 빈 문자열만 출력한다. 

[지시사항]
- 전하께서 대답을 마친 직후의 분위기, 표정, 행동, 편전의 정적 등을 1~2문장으로 묘사하라.
- [절대 금지 사항]
  1. 어떠한 경우에도 대사나 인용문을 만들지 마라. 
  2. 따옴표(" " 또는 ' ')를 절대 사용하지 마라.
  3. 오직 시각적 묘사(표정, 몸짓)와 공간의 분위기만 서술하라.

장면 묘사:
'''
```

### 4) Qwen/ Blossom / Exaone / Kanana 모델 비교
### 1️⃣ 모델 선정 기준
**모델 선정 기준**

- 한국어 처리 능력: 조선 시대의 고어를 다루어야 하기 때문에 비교적 뛰어난 한국어 처리 능력이 요구됨
- 응답 속도 : 유사한 성능의 모델 중에는 규모가 작거나 응답 속도가 더 빠른 모델을 선택

### 2️⃣ 테스트 시나리오
```
[테스트 케이스] 성군과 RAG 검색 엔진 검증
가장 정석적인 역사 질문을 던져서 데이터베이스 검색(Retrieve) 및 답변 생성 기능이 정상 작동하는지 확인합니다.

설정 조건

대상 왕: 세종

신분: 유생

테스트 입력 (유저 발화)

"전하, 훈민정음을 창제하신 참된 뜻이 무엇이옵니까? 어찌하여 새로운 문자를 만드시려 하시옵니까?"

예상되는 시스템 로그 (흐름)

[감정 변화] +0 ➡️ 현재 분노 수치: 0/100 (존중하는 어조이므로 분노 상승 없음)

[분석 결과] 유형: historical | RAG: True | 쿼리: ['세종 훈민정음']

[정보 검색] 실록과 역사 데이터를 찾고 있습니다... -> 팩트 검색 완료 (RAG 적용됨)

[답변 생성] 전하께서 윤음을 내리고 계십니다...

예상 결과 (출력)

세종의 답변: 검색된 팩트를 바탕으로 애민 정신(백성을 불쌍히 여김)을 논리적이고 인자한 어조로 설명함.

배경 묘사: 은은한 묵향이 퍼지는 편전의 학구적이고 차분한 분위기가 묘사됨.
```

### 3️⃣ 모델별 속도 테스트
#### 4-3-1) Qwen/Qwen3.5
- 페르소나 생성 28.29초
- 최초 배경 생성 28.90초
- 답변 출력 46.38초

<img width="1137" height="767" alt="image" src="https://github.com/user-attachments/assets/91fc232c-595a-45d3-a8b9-136b95b18cb8" />

#### 4-3-2) Azure99/Blossom-V6.3-8B
- 페르소나 생성 31.52초
- 최초 배경 생성 29.94초
- 답변 출력 56.29초

<img width="1380" height="786" alt="image" src="https://github.com/user-attachments/assets/df9e70e4-d16e-4d4f-9212-c33a63eff2b0" />

#### 4-3-3) EXAONE-3.5-2.4B-Instruct
- 페르소나 생성 10.12초
- 최초 배경 생성 5.23초
- 답변 출력 10.12초

<img width="1442" height="761" alt="image" src="https://github.com/user-attachments/assets/0b8f938f-7414-4a2c-b495-f8534bf9de9b" />

#### 4-3-4) kanana-1.5-8b-instruct-2505
- 페르소나 생성 30.54초
- 최초 배경 생성 30.40초
- 답변 출력 1분 55.07초

<img width="1514" height="563" alt="image" src="https://github.com/user-attachments/assets/f7bb9170-d265-45f6-8051-eadcbacb6f7a" />
<img width="1501" height="606" alt="image" src="https://github.com/user-attachments/assets/dac321e7-28a8-4498-831a-81cc80b9eaac" />

### 4️⃣ 최종 선택 모델: LGAI-EXAONE/EXAONE-3.5-2.4B-Instruct

- 실험 및 사용 결과,

Qwen은 한국어 처리에서 상대적으로 자연스러움이 부족한 경향이 있었으며, Blossom은 일상 대화 상황에서 응답의 일관성과 완성도가 낮은 경우가 관찰됨. Kanana는 한국어 처리 능력은 우수했으나, 동일 환경에서 EXAONE 대비 응답 속도가 다소 느리게 나타남

<img width="1187" height="135" alt="image" src="https://github.com/user-attachments/assets/03a65f62-4cb3-4e6b-b602-e557fe674381" />

---

## 11. 수행 결과 (테스트 / 시연 페이지)
- 왕 선택 페이지
  <img width="1920" height="1018" alt="screencapture-localhost-8501-2026-04-09-13_28_21" src="https://github.com/user-attachments/assets/5c3ecbba-8ecd-4df9-9a7b-6ce943a271b2" />

- 신분 선택 페이지
  <img width="1920" height="945" alt="screencapture-localhost-8501-2026-04-09-13_28_55" src="https://github.com/user-attachments/assets/c6010094-b867-45c2-90f5-09dcc3838430" />

- 왕과 채팅
  <img width="1407" height="651" alt="스크린샷 2026-04-09 184419" src="https://github.com/user-attachments/assets/d708a96a-7b84-45b4-bd2e-3337a22cc3e1" />


### 주요 결과

- 조선 왕과의 대화형 챗봇 구현
- 질문 의도에 따라 검색 여부를 자동 분기하는 구조 구현
- 왕별 성격과 말투 차이를 반영한 응답 생성
- 감정 상태에 따라 말투가 변화하는 캐릭터 챗봇 구현
- 장면 묘사를 통한 몰입형 인터랙션 제공

### 응답 속도

- 일반 대화: RAG를 생략하여 상대적으로 빠른 응답 가능
- 역사 질문: 검색 + 생성 과정을 거치므로 일반 대화보다 느리지만 정확도 향상

> 실제 측정 수치는 테스트 환경에 따라 달라질 수 있으므로,
> 
> 
> 시연 시 평균 응답 시간 기준으로 따로 기입 권장
>

---

## 12. 향후 발전 계획

### 1. 시스템 고도화

- Fine-Tuning
- Prompt 최적화

### 2. 사용자 몰입감 강화

- 다양한 캐릭터 감정 부여
- 상황별 이미지 생성
- 특수 이벤트 상황 추가
- 왕을 제외한 다양한 등장인물과 동시 대화

---

## 13. 한 줄 회고
- `김현수`</br>
sLLM에서 일정한 출력 형태를 유지하기 위해서는 프롬프트 엔지니어링으로는 한계가 있었다. 지정해준 출력 예시로 답변이 출력되었을 경우에는 답변 퀄리티가 좋았지만, 그 확률이 너무 낮았다. 파인튜닝의 사용 이유와 필요성을 몸소 경험하였다.<br>
- `나혜린`</br>
이번 프로젝트를 통해 단순히 기능을 구현하는 것을 넘어, 사용자에게 더 몰입감 있고 흥미로운 경험을 주는 서비스가 무엇인지 고민해볼 수 있었다. 특히 역사 콘텐츠와 AI 챗봇을 결합하는 과정에서 기술적 구현뿐 아니라 기획과 사용자 관점의 중요성도 함께 배울 수 있었다. 팀원들과 아이디어를 조율하고 문제를 해결해 나가며 협업의 가치도 다시 느낄 수 있었고, 앞으로는 완성도뿐 아니라 실제 사용자의 반응까지 더 깊이 고려하는 개발을 해보고 싶다.
- `류지우`</br>
Facts: 데이터를 ChromaDB에 구축하고, 모델 테스트 및 Streamlit으로 서비스를 구현했다.</br>
Feelings: 프롬프트와 RAG에 따라 답변 품질이 크게 달라지는 과정에서 재미를 느꼈다.</br>
Findings: 무조건 큰 모델을 쓰기보다 RAG와 프롬프트 엔지니어링을 정교하게 조합하는 것이 성능의 핵심임을 깨달았다.</br>
Future action: 답변의 정교함을 높이고 사용자의 몰입감을 극대화할 수 있는 기능을 추가하고 싶다.  </br>
- `정준하`</br>
다양한 모델을 직접 테스트하며 모델별로 답변 속도와 품질 차이가 존재함을 확인했고, 프롬프트를 어떻게 설계하고 수정하느냐에 따라 출력 결과가 크게 달라진다는 것을 경험했다. 또한 ChromaDB 기반 RAG와 Streamlit 구현 과정을 통해 단순 모델 선택보다 전체 파이프라인 설계가 성능에 중요한 영향을 준다는 점을 깨달았다.
- `황인규`</br>
LangGraph 기반 워크플로우와 RAG 시스템을 설계하며 VectorDB의 저장 전략과 키워드·유사도 검색 메커니즘을 실전적으로 이해하였고, LLM 프롬프트 설계에서 토큰 효율성과 명확한 지시의 중요성을 체득하였다.
