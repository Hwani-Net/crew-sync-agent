# 🚀 Crew Sync Agent - Deployment Guide

## 📋 **단계별 배포 가이드**

### **1단계: GitHub 레포지토리 생성**

1. **GitHub 웹사이트** (<https://github.com>) 접속
2. **"New repository"** 클릭
3. **Repository name**: `crew-sync-agent`
4. **Description**: `Dynamic Team Collaboration MCP Server for Smithery`
5. **Public** 선택 (Smithery 배포 필수)
6. **"Create repository"** 클릭

### **2단계: 로컬 Git 설정**

터미널에서 다음 명령어들을 실행하세요:

```bash
# 현재 디렉토리: C:\A2A\A2A\my_agent_system

# GitHub 레포지토리 연결 (your-username을 실제 GitHub 사용자명으로 변경)
git remote add origin https://github.com/your-username/crew-sync-agent.git

# 브랜치 이름을 main으로 설정
git branch -M main

# GitHub에 푸시
git push -u origin main
```

### **3단계: Smithery 배포**

#### 방법 1: Smithery CLI 사용

```bash
# Smithery CLI 설치
npm install -g smithery

# 로그인
smithery login

# 배포
smithery deploy https://github.com/your-username/crew-sync-agent
```

#### 방법 2: Smithery 웹 인터페이스

1. **Smithery 웹사이트** (<https://smithery.ai>) 접속
2. **"Deploy MCP Server"** 클릭
3. **GitHub 레포지토리 URL** 입력: `https://github.com/your-username/crew-sync-agent`
4. **Deploy** 클릭

### **4단계: 환경 변수 설정**

Smithery 대시보드에서 다음 환경 변수들을 설정:

| 변수명 | 설명 | 필수 여부 |
|--------|------|-----------|
| `OPENAI_API_KEY` | OpenAI API 키 | 선택사항 |
| `ANTHROPIC_API_KEY` | Anthropic API 키 | 선택사항 |
| `GOOGLE_API_KEY` | Google API 키 | 선택사항 |
| `COHERE_API_KEY` | Cohere API 키 | 선택사항 |
| `AI_SERVICE` | 기본 AI 서비스 (openai/anthropic/google/cohere) | 선택사항 |
| `MODEL_NAME` | 기본 모델명 (예: gpt-4) | 선택사항 |
| `MAX_CREW_SIZE` | 최대 크루 크기 (기본값: 10) | 선택사항 |

### **5단계: 배포 확인**

#### 로컬 테스트

```bash
python test_crew_sync.py
```

#### 배포된 서버 테스트

```python
# 배포 후 Smithery에서 제공하는 URL로 MCP 클라이언트 연결 테스트
# 예: @your-username/crew-sync-agent
```

## 🔧 **필요한 파일들 체크리스트**

현재 디렉토리에 다음 파일들이 준비되어 있습니다:

- ✅ `mcp_server.py` - MCP 서버 구현
- ✅ `smithery.yaml` - Smithery 설정
- ✅ `Dockerfile` - Docker 컨테이너 정의
- ✅ `.dockerignore` - Docker 빌드 제외 파일
- ✅ `requirements.txt` - Python 의존성
- ✅ `README.md` - 프로젝트 개요
- ✅ `README_SMITHERY.md` - Smithery 배포 상세 가이드
- ✅ `test_crew_sync.py` - 테스트 스크립트

## 🔒 **보안 체크리스트**

- ✅ API 키 환경 변수로만 관리
- ✅ `.dockerignore`에 민감한 파일 제외
- ✅ `.gitignore`에 `.env` 파일 포함
- ✅ Docker 비루트 사용자 실행
- ✅ 코드에 하드코딩된 키 없음

## 🚨 **주의사항**

1. **Public Repository**: Smithery 배포를 위해 반드시 public으로 설정
2. **API Keys**: 절대 코드에 직접 포함하지 말고 Smithery 환경 변수 사용
3. **Testing**: 로컬에서 먼저 충분히 테스트 후 배포
4. **Documentation**: README.md 파일로 사용법 명확히 기술

## 🎯 **배포 완료 후 할 일**

1. **MCP 클라이언트 연결**: Claude Desktop 등에서 연결 테스트
2. **팀 동기화 테스트**: sync_crew 도구로 협업 테스트
3. **동적 멤버 추가**: add_crew_member로 팀 확장 테스트
4. **우선순위 기능**: priority 파라미터로 작업 우선순위 설정 테스트

## 📞 **문제 해결**

### 일반적인 문제들

**Q: Git push 시 권한 오류**
A: GitHub Personal Access Token 설정 필요

**Q: Smithery 배포 실패**
A: 레포지토리가 public인지, smithery.yaml 파일이 올바른지 확인

**Q: MCP 클라이언트 연결 안 됨**
A: 배포 상태 확인, 환경 변수 설정 점검

---

**준비 완료! 이제 GitHub 레포지토리를 생성하고 위 단계를 따라 배포해보세요! 🚀**
