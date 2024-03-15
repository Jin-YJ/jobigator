<template>
  <div class="background">
    <img :src="backgroundImage" alt="Background Image" class="background-image" />
    <div class="blur-effect">
      <!-- 중앙 캐릭터 이미지 -->
      <div class="character">
      </div>
      
      <!-- 가운데 줄 모양의 div 추가 -->
      <div class="line">
        
        
        <div class="speech-bubble right-bubble">여기에 메시지를 입력하세요.</div>
        <!-- Man 이미지에 다른 클래스 "man-character" 추가 -->
        <img :src="manImg" alt="Man Image" class="man-character" />
        <div class="speech-bubble left-bubble">여기에 메시지를 입력하세요.</div>
        <!-- Jobigator 텍스트에 다른 클래스 "jobigator-text" 추가 -->
        <div class="jobigator-text">
          Jobigator
        </div>
      </div>

      <div class="footer-content"></div>
    </div>
  </div>
</template>

<script>
import backgroundImg from '@/assets/background1.png'; // 이미지를 임포트합니다
import manImg from '@/assets/man.png'; // 이미지를 임포트합니다

import '@/assets/styles/font.css'; // font.css 파일을 import

export default {
  name: 'mainPage',
  data() {
    return {
      backgroundImage: backgroundImg, // 임포트한 이미지를 데이터 속성에 할당합니다
      manImg : manImg,
    }
  }
}
</script>

<style>

.background {
  /* 페이지 전체 크기 설정 */
}

.background-image {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  object-fit: cover; /* 이미지를 화면에 맞게 자동 조정 */
  z-index: 0; /* 다른 콘텐츠 위에 위치하도록 설정 */
  opacity: 0.8;
}

.blur-effect {
  backdrop-filter: blur(10px);
  /* 블러 효과 및 크기 설정 */
}

.character {
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  width: 20%;

  
  /* 여기서 이미지 경로 및 크기 설정이 필요하다면 추가하세요. */
}

/* 가운데 줄 모양의 div 스타일링 */
.line {
  position: relative;
  top: 12%; /* 위에서 25% 위치에 배치 */
  left: 0;
  width: 100%;
  height: 60%; /* 줄의 높이 설정 */
  background-color: rgba(255, 255, 255, 0.5); /* 반투명한 흰색 배경 설정 */
  z-index: 1; /* 다른 콘텐츠 위에 위치하도록 설정 */
}

.footer-content {
  position: relative;
  bottom: 0;
  width: 100%;
  /* 하단 요소 스타일링 */
}

/* "man-character" 클래스에 스타일 추가 */
.man-character {
  width: 20%;
  height: 80%;
  margin-bottom: -3%;
  display: absolute;

  /* 원하는 스타일 추가 */
}

/* "jobigator-text" 클래스에 스타일 추가 */
.jobigator-text {
  /* 원하는 스타일 추가 */
  font-family: 'BungeeSpice', sans-serif; /* 'BungeeSpice' 글꼴 사용 */
  font-size: 80px;
}

/* 말풍선 공통 스타일 */
.speech-bubble {
  display: inline-block; /* 인라인 블록 설정 */
  position: relative; /* 상대 위치 설정 */
  padding: 10px;
  border-radius: 10px;
  background: #f0f0f0;
  margin: 0 10px; /* 말풍선 간의 마진 설정 */
  z-index: 2; /* 말풍선이 다른 요소들 위에 오도록 z-index 설정 */
}

/* 말풍선 꼬리 스타일 */
.speech-bubble:after {
  content: '';
  position: absolute;
  border-style: solid;
  border-width: 10px;
  display: block;
}

/* 좌측 말풍선 꼬리 */
.left-bubble:after {
  top: 20px;
  left: -18px; /* 꼬리 위치 조정 */
  border-color: transparent #f0f0f0 transparent transparent;
}

/* 우측 말풍선 꼬리 */
.right-bubble:after {
  top: 20px;
  right: -18px; /* 꼬리 위치 조정 */
  border-color: transparent transparent transparent #f0f0f0;
}

.left-bubble {
  top: -400px; /* 위치를 상위로 10% 올림 */
  width: 15%;
  height: 20%;
  /* 나머지 속성은 그대로 유지 */
}
.right-bubble {
  top: -auto;
  width: 15%;
  height: 20%;
}

</style>