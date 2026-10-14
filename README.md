[index.html](https://github.com/user-attachments/files/33415333/index.html)
<!DOCTYPE html>
<html lang="ko">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>디지털 명함 | 영업관리 전문가</title>
  <style>
    /* DESIGN.md 색상 및 타이포그래피 */
    :root {
      --primary: #134B5F;      /* 청록 (주색) */
      --accent: #D9741F;       /* 주황 (강조) */
      --text: #1E2A30;         /* 먹색 (본문) */
      --muted: #6B7A80;        /* 회색 (보조) */
      --border: #D5DDE0;       /* 가는 선 */
      --bg-light: #EEF3F5;     /* 옅은 청록 면 */
      --bg-card: #FFFFFF;      /* 카드 흰 바탕 */
      --bg-page: #F5F7F8;      /* 종이 회색 면 */
    }

    * {
      box-sizing: border-box;
      margin: 0;
      padding: 0;
      font-family: "Malgun Gothic", "Apple SD Gothic Neo", sans-serif;
      word-break: keep-all;
    }

    body {
      background-color: var(--bg-page);
      color: var(--text);
      display: flex;
      justify-content: center;
      padding: 20px 14px;
      line-height: 1.5;
    }

    .card-container {
      width: 100%;
      max-width: 440px;
      background: var(--bg-card);
      border: 1px solid var(--border);
      border-radius: 12px;
      overflow: hidden;
      box-shadow: 0 4px 14px rgba(19, 75, 95, 0.08);
    }

    /* 상단 비주얼 커버 영역 */
    .profile-hero {
      position: relative;
      width: 100%;
      background: linear-gradient(180deg, #134B5F 0%, #1A3945 100%);
      display: flex;
      justify-content: center;
      align-items: center;
      padding: 24px 20px 18px;
    }

    .profile-img-wrap {
      width: 154px;
      height: 154px;
      border-radius: 50%;
      overflow: hidden;
      border: 4px solid #FFFFFF;
      box-shadow: 0 4px 10px rgba(0, 0, 0, 0.2);
      background-color: #FFFFFF;
    }

    .profile-img-wrap img {
      width: 100%;
      height: 100%;
      object-fit: cover;
      display: block;
    }

    /* 프로필 소개 영역 */
    .profile-info {
      padding: 20px 22px 14px;
      text-align: center;
      border-bottom: 1px solid var(--border);
    }

    .kicker {
      font-size: 13px;
      font-weight: bold;
      color: var(--accent);
      margin-bottom: 4px;
      display: block;
    }

    .name-title {
      display: flex;
      align-items: baseline;
      justify-content: center;
      gap: 8px;
      margin-bottom: 8px;
    }

    .name {
      font-size: 24px;
      font-weight: bold;
      color: var(--primary);
    }

    .position {
      font-size: 15px;
      font-weight: bold;
      color: var(--text);
    }

    .one-line-intro {
      font-size: 14px;
      color: var(--text);
      font-weight: 500;
      margin: 10px 0 14px;
      background: var(--bg-light);
      padding: 10px 14px;
      border-radius: 6px;
      border-left: 3px solid var(--primary);
      text-align: left;
    }

    /* 키워드 태그 */
    .tag-container {
      display: flex;
      flex-wrap: wrap;
      gap: 6px;
      justify-content: center;
      margin-top: 6px;
    }

    .tag {
      background: #FFFFFF;
      border: 1px solid var(--border);
      color: var(--primary);
      font-size: 12px;
      font-weight: bold;
      padding: 4px 10px;
      border-radius: 14px;
    }

    /* 주요 연락 액션 버튼 */
    .action-section {
      padding: 16px 22px;
      display: flex;
      flex-direction: column;
      gap: 10px;
    }

    .btn-main {
      width: 100%;
      background-color: var(--primary);
      color: #FFFFFF;
      border: none;
      border-radius: 6px;
      padding: 13px;
      font-size: 15px;
      font-weight: bold;
      cursor: pointer;
      display: flex;
      align-items: center;
      justify-content: center;
      gap: 8px;
      box-shadow: 0 2px 4px rgba(19, 75, 95, 0.15);
      transition: background-color 0.2s;
      text-decoration: none;
    }

    .btn-main:hover {
      background-color: #0E3949;
    }

    .btn-grid {
      display: flex;
      gap: 8px;
    }

    .btn-sub {
      flex: 1;
      background: #FFFFFF;
      border: 1px solid var(--border);
      border-radius: 6px;
      padding: 11px;
      font-size: 13px;
      font-weight: bold;
      color: var(--primary);
      text-align: center;
      text-decoration: none;
      cursor: pointer;
      transition: all 0.2s;
      display: flex;
      align-items: center;
      justify-content: center;
    }

    .btn-sub:hover {
      background: var(--bg-light);
      border-color: var(--primary);
    }

    /* 상세 업무 섹션 (DESIGN.md 2열/단계 규칙) */
    .detail-section {
      padding: 18px 22px;
      border-top: 1px solid var(--border);
    }

    .section-title {
      font-size: 14px;
      font-weight: bold;
      color: var(--primary);
      margin-bottom: 12px;
      display: flex;
      align-items: center;
      justify-content: space-between;
    }

    .duty-list {
      display: flex;
      flex-direction: column;
      gap: 10px;
    }

    .duty-item {
      display: flex;
      gap: 10px;
      align-items: flex-start;
      background: var(--bg-page);
      border: 1px solid var(--border);
      border-radius: 6px;
      padding: 10px 12px;
    }

    .duty-num {
      font-size: 13px;
      font-weight: bold;
      color: var(--accent);
      min-width: 22px;
    }

    .duty-text strong {
      font-size: 13px;
      color: var(--primary);
      display: block;
      margin-bottom: 2px;
    }

    .duty-text span {
      font-size: 12px;
      color: var(--muted);
    }

    /* 내가 만든 도구 목록 */
    .portfolio-section {
      padding: 18px 22px;
      border-top: 1px solid var(--border);
      background: #FAFCFD;
    }

    .tool-list {
      display: flex;
      flex-direction: column;
      gap: 8px;
    }

    .tool-link {
      display: flex;
      justify-content: space-between;
      align-items: center;
      background: #FFFFFF;
      border: 1px solid var(--border);
      border-radius: 6px;
      padding: 12px 14px;
      text-decoration: none;
      color: var(--text);
      transition: all 0.2s;
    }

    .tool-link:hover {
      border-color: var(--primary);
      box-shadow: 0 2px 6px rgba(19, 75, 95, 0.1);
    }

    .tool-info strong {
      font-size: 14px;
      color: var(--primary);
      display: block;
      margin-bottom: 2px;
    }

    .tool-info span {
      font-size: 11px;
      color: var(--muted);
    }

    .tool-arrow {
      font-size: 15px;
      font-weight: bold;
      color: var(--accent);
    }

    /* 꼬리말 */
    .footer {
      padding: 16px 20px 20px;
      text-align: center;
      font-size: 11px;
      color: var(--muted);
      border-top: 1px solid var(--border);
      background: var(--bg-page);
    }

    /* 토스트 알림 */
    .toast {
      position: fixed;
      bottom: 24px;
      left: 50%;
      transform: translateX(-50%);
      background: var(--text);
      color: #FFFFFF;
      padding: 8px 16px;
      border-radius: 20px;
      font-size: 13px;
      opacity: 0;
      pointer-events: none;
      transition: opacity 0.3s;
      z-index: 999;
    }

    .toast.show {
      opacity: 0.95;
    }
  </style>
</head>
<body>

<div class="card-container">
  <!-- 상단 커리어우먼 프로필 히어로 -->
  <div class="profile-hero">
    <div class="profile-img-wrap">
      <img src="profile.png" alt="프로필 사진">
    </div>
  </div>

  <!-- 프로필 소개 -->
  <div class="profile-info">
    <span class="kicker">스마트 업무자동화 & 영업관리</span>
    <div class="name-title">
      <span class="name">김프로</span>
      <span class="position">영업관리팀 과장</span>
    </div>

    <div class="one-line-intro">
      "데이터 기반의 정확한 견적 산출부터 철저한 납기 조율까지, 성과를 만드는 현장 중심 실무자입니다."
    </div>

    <!-- 전문 영역 태그 -->
    <div class="tag-container">
      <span class="tag">#견적산출</span>
      <span class="tag">#납기공정조율</span>
      <span class="tag">#데이터집계분석</span>
      <span class="tag">#현장보고서</span>
    </div>
  </div>

  <!-- 주요 연락 액션 -->
  <div class="action-section">
    <!-- 연락처 저장 (vcf 다운로드) -->
    <button class="btn-main" onclick="downloadVCard()">
      연락처에 저장하기 (.vcf)
    </button>

    <div class="btn-grid">
      <a href="tel:010-0000-0000" class="btn-sub">전화 걸기</a>
      <button class="btn-sub" onclick="copyEmail()">이메일 복사</button>
    </div>
  </div>

  <!-- 전문 핵심 역량 -->
  <div class="detail-section">
    <div class="section-title">
      <span>주요 업무 및 전문 분야</span>
      <span style="font-size: 12px; color: var(--accent); font-weight: normal;">Core Strengths</span>
    </div>

    <div class="duty-list">
      <div class="duty-item">
        <span class="duty-num">01</span>
        <div class="duty-text">
          <strong>수주 및 계약 프로세스 총괄</strong>
          <span>산업용 보일러 및 설비 견적 산출, 본사 승인 및 계약 조건 검토</span>
        </div>
      </div>

      <div class="duty-item">
        <span class="duty-num">02</span>
        <div class="duty-text">
          <strong>현장 납기 및 설치 공정 조율</strong>
          <span>지사별 설치 일정 트래킹, 지연 요인 사전 해소 및 완벽한 준공 지원</span>
        </div>
      </div>

      <div class="duty-item">
        <span class="duty-num">03</span>
        <div class="duty-text">
          <strong>데이터 기반 성과 분석 및 본사 보고</strong>
          <span>월별 실적 모니터링, 취소·미수금 리스크 분석 및 분기 전략 수립</span>
        </div>
      </div>
    </div>
  </div>

  <!-- 내가 만든 것 (포트폴리오 링크) -->
  <div class="portfolio-section">
    <div class="section-title">
      <span>내가 만든 업무 도구</span>
      <span style="font-size: 11px; color: var(--muted); font-weight: normal;">Web Tools</span>
    </div>

    <div class="tool-list">
      <a href="lotto.html" class="tool-link">
        <div class="tool-info">
          <strong>로또 번호 추첨기 & 점심 메뉴</strong>
          <span>암호학적 난수 추출, 일별 행운 번호 및 점심 메뉴 추천</span>
        </div>
        <div class="tool-arrow">→</div>
      </a>

      <a href="csv-tool.html" class="tool-link">
        <div class="tool-info">
          <strong>CSV 엑셀 자동 정리 도구</strong>
          <span>서버 전송 없는 브라우저 보안 데이터 전처리 및 엑셀 변환</span>
        </div>
        <div class="tool-arrow">→</div>
      </a>
    </div>
  </div>

  <!-- QR 코드 섹션 (내 모바일 명함 바로가기) -->
  <div class="qr-section" style="padding: 18px 22px; border-top: 1px solid var(--border); text-align: center; background: #FFFFFF;">
    <div class="section-title" style="justify-content: center; margin-bottom: 8px;">
      <span>모바일 명함 QR 코드</span>
    </div>
    <div style="font-size: 12px; color: var(--muted); margin-bottom: 12px;">
      스마트폰 카메라로 스캔하면 이 명함 주소로 바로 연결됩니다.
    </div>
    <div style="display: inline-block; padding: 10px; background: #FFFFFF; border: 1px solid var(--border); border-radius: 8px; box-shadow: 0 2px 6px rgba(19, 75, 95, 0.08);">
      <img src="https://api.qrserver.com/v1/create-qr-code/?size=150x150&data=https%3A%2F%2Fhyolove630-lang.github.io%2Fhyolove630%2F&color=13-75-95" 
           alt="모바일 명함 QR 코드" 
           width="140" 
           height="140" 
           style="display: block; border-radius: 4px;">
    </div>
    <div style="margin-top: 10px;">
      <a href="https://hyolove630-lang.github.io/hyolove630/" 
         target="_blank" 
         rel="noopener noreferrer"
         style="font-size: 12px; color: var(--primary); font-weight: bold; text-decoration: underline; word-break: break-all;">
        https://hyolove630-lang.github.io/hyolove630/
      </a>
    </div>
  </div>

  <!-- 꼬리말 -->
  <div class="footer">
    회사 및 연락처 정보는 실습용 가상 데이터입니다.<br>
    Copyright © 2026. All rights reserved.
  </div>
</div>

<div class="toast" id="toast">이메일 주소가 복사되었습니다.</div>

<script>
  // vCard (.vcf) 생성 및 다운로드 함수
  function downloadVCard() {
    const vcardData = [
      "BEGIN:VCARD",
      "VERSION:3.0",
      "N:김;프로;;;",
      "FN:김프로 과장",
      "ORG:한국미우라;영업관리팀",
      "TITLE:영업관리팀 과장",
      "TEL;TYPE=CELL:010-0000-0000",
      "EMAIL;TYPE=WORK:pro_kim@example.com",
      "NOTE:산업용 설비 견적 및 납기 조율 전문",
      "END:VCARD"
    ].join("\r\n");

    const blob = new Blob([vcardData], { type: "text/vcard;charset=utf-8;" });
    const url = URL.createObjectURL(blob);
    const link = document.createElement("a");
    link.href = url;
    link.setAttribute("download", "김프로_영업관리.vcf");
    document.body.appendChild(link);
    link.click();
    document.body.removeChild(link);
    URL.revokeObjectURL(url);
    showToast("연락처 파일(.vcf)이 다운로드되었습니다.");
  }

  // 이메일 주소 복사
  function copyEmail() {
    const email = "pro_kim@example.com";
    navigator.clipboard.writeText(email).then(() => {
      showToast("이메일(pro_kim@example.com)이 복사되었습니다.");
    }).catch(() => {
      showToast("복사에 실패했습니다.");
    });
  }

  function showToast(msg) {
    const toast = document.getElementById('toast');
    toast.textContent = msg;
    toast.classList.add('show');
    setTimeout(() => {
      toast.classList.remove('show');
    }, 1800);
  }
</script>

</body>
</html>
