/* 
  세종 스마트도시팀 뉴스 대시보드
  설정 가이드
  
  ▌주요 기능▐
  - 최신부터 15일 이전까지의 뉴스만 자동 필터링
  - 30분마다 자동 새로고침
  - 4개 카테고리로 분류된 뉴스 표시
  
  ▌수정 방법▐
  아래 CATEGORIES 객체를 편집하여 뉴스원을 추가/삭제/변경할 수 있습니다.
  
  ▌각 항목 설명▐
  - name: 뉴스원 이름 (대시보드에 표시됨)
  - url: RSS 피드 URL
  - keywords: 특정 키워드만 필터링 (선택사항, 없으면 모든 기사 표시)
  
  ▌15일 기간 조정하기▐
  코드에서 "15 * 24 * 60 * 60 * 1000" 부분을 찾아 15를 다른 숫자로 바꾸세요:
  - 7일: 7 * 24 * 60 * 60 * 1000
  - 30일: 30 * 24 * 60 * 60 * 1000
  - 60일: 60 * 24 * 60 * 60 * 1000
*/

export const CATEGORIES = {
    '세종 지역뉴스': {
        description: '세종시 전체 뉴스',
        sources: [
            { name: '세종의소리', url: 'https://www.sjsori.com/rss/allArticle.xml' },
            { name: '구글뉴스(세종)', url: 'https://news.google.com/rss/search?q=%EC%84%B8%EC%A2%85&hl=ko&gl=KR&ceid=KR:ko' }
        ]
    },
    
    '스마트도시 동향': {
        description: 'Smart City 관련 뉴스',
        sources: [
            { name: '세종의소리', url: 'https://www.sjsori.com/rss/allArticle.xml' },
            { name: '구글뉴스(스마트)', url: 'https://news.google.com/rss/search?q=%EC%8A%A4%EB%A7%88%ED%8A%B8%EB%8F%84%EC%8B%9C&hl=ko&gl=KR&ceid=KR:ko' }
        ],
        keywords: ['스마트도시', '스마트시티', '스마트', 'smart city', '행복도시']
    },
    
    'AI·기술·혁신': {
        description: 'AI와 기술 혁신 뉴스',
        sources: [
            { name: '구글뉴스(AI)', url: 'https://news.google.com/rss/search?q=AI%20%E1%84%80%E1%85%B5%E1%84%89%E1%85%AE%E1%86%AF&hl=ko&gl=KR&ceid=KR:ko' },
            { name: '구글뉴스(기술)', url: 'https://news.google.com/rss/search?q=%EA%B8%B0%EC%88%A0%20%ED%98%81%EC%8B%A0&hl=ko&gl=KR&ceid=KR:ko' }
        ],
        keywords: ['AI', '인공지능', '기술', '디지털', '혁신', '데이터']
    },
    
    '정책·공모·공고': {
        description: '정부 정책 및 공모/공고',
        sources: [
            { name: '정책브리핑', url: 'https://www.korea.kr/rss/policy.xml' },
            { name: '세종의소리', url: 'https://www.sjsori.com/rss/allArticle.xml' }
        ],
        keywords: ['공모', '공고', '사업', '정책', '공시', '모집', '지원']
    }
};

/*
  ▌RSS 피드 찾기 팁▐
  
  1. 사이트 방문 → "RSS" 또는 아이콘 찾기
  2. 브라우저 개발자 도구 (F12) → "Network" → "Type: xhr" 필터
  3. Google News 검색 후: news.google.com/rss/search?q=검색어 형식
  
  ▌주요 세종 뉴스원▐
  - 세종의소리: https://www.sjsori.com/rss/allArticle.xml
  - 세종매일: 별도 확인 필요
  - 세종포스트: 별도 확인 필요
  - 정책브리핑: https://www.korea.kr/rss/policy.xml
  
  ▌도움말▐
  문제가 있으면 헤이지니님께 알려주세요!
*/
