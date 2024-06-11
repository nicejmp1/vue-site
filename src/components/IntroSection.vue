<template>
    <section id="intro">
      <div class="intro__inner">
        <h2 class="intro__title" ref="title">pront Developer</h2>
        <div class="intro__lines" aria-hidden="true">
          <span class="line"></span>
          <span class="line"></span>
          <span class="line"></span>
          <span class="line"></span>
          <span class="line"></span>
          <span class="line"></span>
          <span class="line"></span>
        </div>
        <div class="intro__text">
          <div class="text">
            <div>Success</div>
            <div>is the result of</div>
            <div>consistent effort</div>
          </div>
          <div class="img">
            <img src="https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcTlUXDrp4EVb8-gJOn5DkWhamBJnvEbQPbkYA&s">
          </div>
        </div>
        <div class="intro__lines bottom" aria-hidden="true">
          <span class="line"></span>
          <span class="line"></span>
          <span class="line"></span>
          <span class="line"></span>
          <span class="line"></span>
          <span class="line"></span>
          <span class="line"></span>
        </div>
      </div>
    </section>
  </template>
  
  <script>
  import { gsap } from "gsap";
  import { onMounted, ref } from 'vue';
  
  export default {
    setup() {
      const title = ref(null);
  
      onMounted(() => {
        const titleChars = title.value.textContent.split("");
        title.value.innerHTML = titleChars.map(char => `<span>${char}</span>`).join("");
  
        gsap.fromTo(title.value.children, 
          { opacity: 0, y: -50 },
          { opacity: 1, y: 0, stagger: 0.3, ease: "bounce.out" }
        );
      });
      
  
      return {
        title
      };
    }
  }
  </script>
  
  <style lang="scss" scoped>

@keyframes lineGrow {
  from {
    transform: scaleX(0);
  }
  to {
    transform: scaleX(1);
  }
}

  #intro {
    height: 100vh;
    background-color: #fff5db;
  
    .intro__inner {
      width: 100%;
      height: 100%;
      display: flex;
      align-items: center;
      justify-content: center;
      flex-direction: column;
      padding: 16px;
  
      .intro__title {
        font-size: 9vw;
        line-height: 1;
        font-weight: 800;
        white-space: nowrap;
        text-transform: uppercase;
        letter-spacing: -0.2vw;
        padding-bottom: 20px;
        display: flex;
        overflow: hidden;
        color: #ee9c63;
      }
  
      @media (max-width: 800px) {
        .intro__title {
          display: none;
        }
      }
  
      .intro__lines {
        width: 100%;
        display: flex;
        align-items: center;
        flex-direction: column;
  
        .line {
          display: block;
          height: 1px;
          background-color: #282926;
          transform-origin: center;
          transform: scaleX(0);
          margin-bottom: 0.5vw;
          animation: lineGrow 3s forwards; /* 애니메이션 설정 */
  
          &:nth-child(1) {
            height: 3px;
            width: 40%;
            animation-delay: 3.5s;
          }
          &:nth-child(2) {
            height: 6px;
            width: 50%;
            animation-delay: 3s;

          }
          &:nth-child(3) {
            height: 9px;
            width: 60%;
            animation-delay: 2.5s;
          }
          &:nth-child(4) {
            height: 12px;
            width: 70%;
            animation-delay: 2s;

          }
          &:nth-child(5) {
            height: 15px;
            width: 80%;
            animation-delay: 1.5s;
          }
          &:nth-child(6) {
            height: 18px;
            width: 90%;
            animation-delay: 1s;
          }
          &:nth-child(7) {
            height: 21px;
            width: 100%;
            animation-delay: 0.5s;
          }
        }
  
        &.bottom {
          display: none;
        }
      }
  
      @media (max-width: 800px) {
      .intro__lines.bottom {
        display: flex; /* flexbox 사용 */
        align-items: center;
        flex-direction: column;

        .line {
          display: block;
          height: 1px;
          background-color: #282926;
          transform-origin: center;
          transform: scaleX(0);
          margin-top: 0.5vw;
          animation: lineGrow 3s forwards;

          &:nth-child(7) {
            height: 3px;
            width: 40%;
            animation-delay: 3.5s;
          }
          &:nth-child(6) {
            height: 6px;
            width: 50%;
            animation-delay: 3s;
          }
          &:nth-child(5) {
            height: 9px;
            width: 60%;
            animation-delay: 2.5s;
          }
          &:nth-child(4) {
            height: 12px;
            width: 70%;
            animation-delay: 2s;
          }
          &:nth-child(3) {
            height: 15px;
            width: 80%;
            animation-delay: 1.5s;
          }
          &:nth-child(2) {
            height: 18px;
            width: 90%;
            animation-delay: 1s;
          }
          &:nth-child(1) {
            height: 21px;
            width: 100%;
            animation-delay: 0.5s;
          }
        }
          
    }
 }
  
      .intro__text {
        width: 100%;
        height: 40vh;
        background-color: #282926;
        color: var(--white);
        display: flex;
        align-items: center;
        justify-content: center;
        flex-direction: column;
        position: relative;
  
        .text {
          font-size: 4vw;
          line-height: 1;
          font-weight: 900;
          text-transform: uppercase;
          text-decoration: underline;
          text-align: center;
          position: relative;
          z-index: 1000;
          transition: all 0.3s;
          cursor: all-scroll;
          color: #3a6984;
        }
  
        .img {
          position: absolute;
          left: 50%;
          top: 50%;
          transform: translate(-50%, -50%);
          width: 30vh;
          height: 30vh;
          border-radius: 50%;
          overflow: hidden;
          filter: grayscale(100%);
          transition: all 0.3s;
        }
  
        @media (max-width: 800px) {
          .text {
            font-size: 6vw;
          }

          .img {
            width: 26vh;
            height: 26vh;
          }
        }
  
        &:hover .text {
          opacity: 0;
        }
  
        &:hover .img {
          filter: none;
        }
      }
    }
  }
  
  @keyframes bounceIn {
    to {
      opacity: 1;
      transform: translateY(0);
    }
  }
  </style>
  