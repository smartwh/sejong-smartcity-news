# 📰 세종 스마트도시 뉴스 대시보드

## 🎯 개요
- **용도**: 세종 스마트도시팀 내부 뉴스 통합 대시보드
- **기술**: HTML/JavaScript (완전히 클라이언트 사이드)
- **비용**: 완전 무료 (API/토큰 불필요)
- **갱신**: 자동 30분 주기

---

## ✨ 주요 기능

| 기능 | 설명 |
|------|------|
| **4가지 카테고리** | 세종뉴스 / 스마트도시 / AI·기술 / 정책·공모 |
| **최신 15일 기사** | 최신부터 15일 이전까지의 기사만 자동 필터링 |
| **실시간 갱신** | 30분마다 자동 새로고침 |
| **직접 링크** | 기사 클릭 → 원본 신문사 웹사이트 |
| **깔끔한 UI** | 반응형 디자인 (모바일/태블릿/PC) |
| **가독성** | 제목 + 2줄 요약 + 발행시간 + 출처 |

---

## 🚀 배포 방법 (3가지 옵션)

### **옵션 1: GitHub Pages (추천 - 5분)**

#### 1단계: GitHub 저장소 생성
```bash
1. https://github.com/new 방문
2. Repository name: "sejong-smartcity-news" 입력
3. Description: "세종 스마트도시 뉴스 대시보드"
4. Public 선택 (팀에서 접근 가능하도록)
5. "Create repository" 클릭
```

#### 2단계: 파일 업로드
```bash
1. 저장소 → "Add file" → "Upload files"
2. sejong_smartcity_news.html 업로드
3. "Rename" → "index.html"로 변경
4. Commit message: "Initial commit: news dashboard"
5. Commit 클릭
```

#### 3단계: GitHub Pages 활성화
```bash
1. 저장소 Settings → "Pages"
2. Source: "Deploy from a branch" 선택
3. Branch: "main" 선택
4. Folder: "/ (root)" 선택
5. Save 클릭
```

#### 4단계: 공유
```
https://[your-github-username].github.io/sejong-smartcity-news/
```

이 URL을 팀에 공유하세요! 🎉

---

### **옵션 2: 로컬 서버 실행**

#### Python 사용
```bash
# 파일이 있는 디렉토리에서
python -m http.server 8000

# 브라우저에서 접속
http://localhost:8000
```

#### Node.js 사용
```bash
# 설치 (처음 한 번만)
npm install -g http-server

# 실행
http-server .

# 브라우저에서 접속
http://localhost:8080
```

---

### **옵션 3: 팀 내부 서버**

서버에 파일을 올리고 팀 인트라넷에 배포할 수도 있습니다.

---

## ⚙️ 뉴스원 수정하기

### 내용 변경하려면?

HTML 파일을 텍스트 에디터로 열고, 아래 부분을 찾아서 수정하세요:

```javascript
// ~줄 82 근처
const categories = {
    '새 카테고리명': {
        sources: [
            { name: '뉴스사명', url: 'https://rss-url.xml' },
        ],
        keywords: ['키워드1', '키워드2']  // 선택사항
    }
};
```

### 예시: 새 뉴스원 추가

```javascript
'스마트도시 동향': {
    sources: [
        { name: '세종의소리', url: 'https://www.sjsori.com/rss/allArticle.xml' },
        { name: '세종매일', url: 'https://www.sjmaeil.com/rss.xml' },  // 추가됨
        { name: '구글뉴스(스마트)', url: '...' }
    ],
    keywords: ['스마트도시', '스마트시티']
}
```

### 예시: 카테고리 추가

```javascript
'교육 정책': {
    sources: [
        { name: '정책브리핑', url: 'https://www.korea.kr/rss/policy.xml' }
    ],
    keywords: ['교육', '학교', '학생']
}
```

---

## 📋 사용 팁

### 팀에 소개할 때
```
"세종 스마트도시팀용 통합 뉴스 대시보드입니다.
매일 30분 주기로 최신 기사를 자동으로 가져옵니다.
기사 제목을 클릭하면 원본 신문사에서 전문을 읽을 수 있습니다."
```

### 자주 묻는 질문

**Q: 얼마나 자주 갱신되나요?**
A: 30분마다 자동 갱신됩니다. (변경 가능)

**Q: 왜 최신 15일 기사만 보여주나요?**
A: 팀의 실무 효율성을 위해 최신 2주간의 관련 뉴스만 표시합니다.
   - 더 오래된 기사가 필요하면 코드의 "15"를 "30" 등으로 변경하세요.

**Q: 토큰이나 비용이 드나요?**
A: 완전 무료입니다. API 키 불필요.

**Q: 내가 원하는 뉴스원만 보고 싶은데?**
A: HTML 파일의 categories 항목을 수정하면 됩니다.

**Q: 모바일에서도 보나요?**
A: 네! 반응형으로 만들어져 모든 기기에서 봅니다.

**Q: 보도자료를 자동으로 가져올 수 있나요?**
A: RSS가 있다면 가능합니다. (정책브리핑, 뉴스와이어 등)

**Q: 15일 기간을 조정하고 싶은데?**
A: HTML 코드에서 "15 * 24 * 60 * 60 * 1000" 부분을 찾아 숫자 15를 변경하세요.
   - 30일: 30 * 24 * 60 * 60 * 1000
   - 7일: 7 * 24 * 60 * 60 * 1000

---

## 🔧 기술 상세

- **언어**: HTML, CSS, JavaScript
- **라이브러리**: 없음 (순수 Vanilla JS)
- **호환성**: Chrome, Firefox, Safari, Edge (최신 버전)
- **데이터 소스**: RSS 피드 (뉴스사 공식 제공)

---

## 📞 문제 해결

### RSS가 안 나옵니다
1. URL이 정확한지 확인
2. 해당 뉴스사 홈페이지 → RSS 페이지 재확인
3. 브라우저 개발자 도구 (F12) → Console 확인

### CORS 오류 발생
- Google News RSS를 사용하면 문제 없습니다
- 일부 사이트는 제한이 있을 수 있습니다

### 갱신 주기 변경
```javascript
// 코드에서 찾기: updateInterval = setInterval(loadNews, 30 * 60 * 1000);
// 30 * 60 * 1000 = 30분
// 15분으로 하려면: 15 * 60 * 1000
// 1시간으로 하려면: 60 * 60 * 1000
```

---

## 📝 라이선스

- 개인/팀 내부 용도: 자유롭게 사용 가능
- 수정/배포/재판매 금지
- RSS 피드 이용약관 준수

---

## 🎓 학습 자료

- [RSS란 무엇인가](https://ko.wikipedia.org/wiki/RSS)
- [Google News RSS](https://support.google.com/news/answer/4628842)
- [정책브리핑 RSS](https://www.korea.kr/etc/rss.do)

---

**문제가 있거나 요청사항이 있으면 말씀해주세요! 🙋**

*마지막 업데이트: 2026년 4월*
