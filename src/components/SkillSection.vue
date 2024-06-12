<script setup>

import { skillText } from '@/constants';

</script>

<template>
  <section id="skill">
    <div class="skill__inner">
      <div class="skill__title">
        <h2>프론트엔드를 향한 <em>나의 여정</em></h2>
      </div>
      <div class="skill__desc">
        <div v-for="(text, key) in skillText" :key="key"> 
          <span>{{ key + 1 }}.</span>
          <h3>{{ text.title }}</h3>
          <p>{{ text.desc }}</p>
        </div>
      </div>
    </div>
  </section>
</template>

<style lang="scss" scoped>
#skill {
  min-height: 100vh;
}
.skill__inner {
  padding: 16px;
  display: flex;
  justify-content: space-between;

  @media (max-width:800px) {
    flex-direction: column;
  }

  .skill__title {
    position: sticky;
    width: 48%;
    height: 5vw;
    top: 100px;
    left: 0;

    @media (max-width:800px) {
      width: 100%;
      background-color: var(--mainBg-color);
    }

    h2 {
      font-size: 4vw;
      font-weight: bold;
      line-height: 1;
      text-transform: uppercase;
      font-family: var(--mainKor-font);
      color: var(--black100);
      border-bottom: 0.4vw solid var(--black100);

      @media (max-width:800px) {
        font-size: 8vw;
    }
      

      em {
        font-size: 1.25rem;
        font-weight: 400;
        line-height: 1.1;

        @media (max-width:800px) {
        font-size: 1.5rem
    }
      }
    }
  }

  .skill__desc {
    width: 50%;

    @media (max-width:800px) {
      width: 100%;
    }

    span {
      font-size: 5vw;
      line-height: 0.8;
      font-weight: 900;
      font-family: var(--mainNum-font);
      display: block;
      margin-bottom: 1vw;

      @media (max-width:800px) {
      margin-top: 50px;
      font-size: 9vw;
      display: block;
    }

    }
    
    h3 {
      font-size: 1.5rem;
      text-decoration: underline;
      text-underline-position: under;
      margin-bottom: 1vw;

      @media (max-width:800px) {

    }
    }

    p {
      margin-bottom: 30vh;
      font-size: 1.1rem;
      color: var(--black300);
      line-height: 1.8;

      @media (max-width:800px) {
      margin-top: 10px;
      font-size: 3vw;
      display: block;
    }
    }
  }

 
}

</style>