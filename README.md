
# 🎤 Voice Authentication Smart System (ECAPA-TDNN + Wav2Vec2 + Pitch Ensemble)

> 화자 인식을 기반으로 한 개인화 보안 시스템  
> 프로필 생성부터 자동 로그인, 2차 인증, AI 음성 탐지까지!

---

## 🧠 프로젝트 개요

이 프로젝트는 사용자의 **고유한 음성 특징**을 바탕으로 스마트 도어락, 홈 IoT 등의 보안 시스템에 응용 가능한 **음성 기반 인증 시스템**입니다.  
**ECAPA-TDNN**과 **Wav2Vec2 + Pitch 임베딩**을 앙상블하여 **높은 정확도와 강건성**을 확보했습니다.

---

## ✨ 주요 기능

| 기능 | 설명 |
|------|------|
| 👤 프로필 생성 | 10~15초 문장 5개를 녹음해 음성 임베딩 생성 |
| 🗑️ 프로필 삭제 | UI에서 바로 삭제 가능 |
| 🔐 자동 로그인 | 녹음된 음성과 등록된 프로필을 비교해 로그인 |
| ✅ 2차 인증 | 랜덤 문장을 말함으로써 인증 신뢰도 향상 |
| 🤖 AI 음성 탐지 | 합성 음성(TTS, Deepfake)을 차단 |
| 🎨 넷플릭스 스타일 UI | 직관적인 사용자 인터페이스 구현 (PyQt5)

---

## 🧱 사용된 기술

- **PyTorch**, **SpeechBrain (ECAPA-TDNN)**
- **Transformers** (`facebook/wav2vec2-base`)
- **Librosa** (Pitch 추출)
- **PyQt5** (GUI)
- **Sounddevice**, **Soundfile** (녹음/저장)

---

## 📁 프로젝트 구조

```
📦 voice-auth-system/
 ┣ profiles/                  # 사용자 프로필 폴더
 ┣ ai_detector.py             # AI 음성 탐지기 (ResNet 기반)
 ┣ voice_login_main.py        # 메인 UI 및 기능 코드
 ┣ ecapa_model/               # ECAPA 모델 저장 경로
 ┣ README.md                  # 프로젝트 설명
```

---

## 🚀 실행 방법

```bash
# 1. 필요한 라이브러리 설치
pip install -r requirements.txt

# 2. 프로젝트 실행
python voice_login_main.py
```

---

## 🛡️ 보안 구조

1. **1차 인증**: 등록된 음성과 새로 녹음한 음성 비교
2. **2차 인증**: 무작위 문장 발화 후 유사도 재검사
3. **AI 탐지**: 기계적으로 합성된 음성 탐지 및 차단

---

## 🗣️ 프로필 생성 시 녹음 문장 예시

```
음성으로 문을 열겠습니다. 지금부터 인증을 시작합니다.
이 문장을 정확히 말하면 잠금장치가 해제됩니다.
지금 들리는 이 목소리는 저만 사용할 수 있는 보안 열쇠입니다.
스마트 도어 시스템을 통해 집에 안전하게 들어가고 싶습니다.
이제 제 음성으로 문을 열 수 있는 시대가 왔습니다. 열어주세요.
```

---

## 📌 개발 히스토리 요약

- 🔸 ECAPA-TDNN + Cosine Similarity 기반 1차 구현
- 🔸 Wav2Vec2 + Pitch 임베딩 추가 (앙상블 구조 적용)
- 🔸 긴 문장 5개 녹음 → 평균 임베딩 저장
- 🔸 UI 기반 프로필 생성/삭제/로그인 구성
- 🔸 2차 인증 및 AI 합성 음성 차단 기능 완성

---

## 🙋‍♂️ 개발자

- 👨‍💻 박성재, 심성관 | 정보통신학과 4학년
- 🎓 졸업 작품으로 진행  
- ✉️ [miamo0426@gmail.com] (이메일은 수정해 주세요!)
- 📝 [개발 메모장](https://docs.google.com/document/d/1E5yThehOcIESbAIq4tZq2XeCy7G4xBIGsNDsIICj2ls/edit?usp=sharing) 

---

## 📌 향후 확장 방향 (Ideas)

- 📱 라즈베리파이 연동
- 🧠 GPT 기반 대화형 음성 비서 결합
- 🔐 보안성 강화
