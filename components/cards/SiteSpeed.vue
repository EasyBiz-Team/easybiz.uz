<template>
  <div class="sitespeed">
    <div class="sitespeed-header">
      <h2 class="sitespeed-title">Site Speed</h2>
      <!-- <div class="sitespeed-buttons">
        <button class="sitespeed-button">Month</button>
        <button class="sitespeed-button">6 Month</button>
        <button class="sitespeed-button">Year</button>
      </div> -->
    </div>
    <div class="sitespeed-block">
      <div class="sitespeed-card-content">
        <div class="sitespeed-circle">
          <h2>639</h2>
          <span>mc</span>
        </div>
        <div class="sitespeed-cards">
          <div class="sitespeed-card">
            <h2 class="card-speed">42</h2>
            <span class="card-description">Requires</span>
          </div>
          <div class="sitespeed-card">
            <h2 class="card-speed">42</h2>
            <span class="card-description">Requires</span>
          </div>
          <div class="sitespeed-card">
            <h2 class="card-speed">42</h2>
            <span class="card-description">Requires</span>
          </div>
          <div class="sitespeed-card">
            <h2 class="card-speed">42</h2>
            <span class="card-description">Requires</span>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script setup lang="ts">
import { onMounted } from 'vue';

const calculate = (el: string, property: string, media: number) => {
  const element = document.querySelector(el) as HTMLElement;
  const rect = element?.getBoundingClientRect();

  const size = {
    currentHeight: rect?.height || 0,
    width: rect?.width || 0,
    targetHeight: rect?.width,
  }


  if (window.innerWidth <= media) {
    element.style[property] = `${size.targetHeight / 10}rem`;
  }
}


onMounted(() => {
  calculate('.sitespeed .sitespeed-circle', 'height', 1024);
})

</script>

<style scoped lang="scss">
.sitespeed {
  width: 100%;
  max-width: 100%;
  display: flex;
  flex-direction: column;
  border: #e0e0e0 0.1rem solid;
  border-radius: 1rem;

  &-buttons {
    display: flex;
    gap: 1rem;
  }

  &-button {
    background: #0a65f7;
    color: #fff;
    border: 0;
    border-radius: 0.4rem;
    padding: 1rem 2rem;
    text-align: center;
    font-size: 1.6rem;
  }

  &-header {
    display: flex;
    align-items: center;
    justify-content: space-between;
    border-bottom: #e0e0e0 0.1rem solid;
    padding: 2rem 2.6rem;

    @media(max-width: 768px) {
      padding: 2rem 1.6rem;
    }
  }

  &-title {
    font-size: 2rem;

    @media(max-width: 768px) {
      font-size: 1.8rem;
    }
  }

  &-more {
    border: 0;
  }

  &-card {
    &-content {
      width: inherit;
      height: inherit;
      display: flex;
      justify-content: space-between;
      align-items: center;
      padding: 2rem 5rem;

      @media(max-width: 768px) {
        flex-direction: column;
        padding: 2rem;
      }

      & div {
        max-width: 45%;

        @media(max-width: 500px) {
          max-width: 100%;
        }
      }

      & .sitespeed {
        &-circle {
          width: 20rem;
          height: 20rem;
          border-radius: 50%;
          display: flex;
          align-items: center;
          justify-content: center;
          flex-direction: column;
          background: rgba(37, 99, 235, 0.05);
          border-top: 0.2rem solid rgba(37, 99, 235, 1);
          border-right: 0.2rem solid rgba(37, 99, 235, 1);
          border-bottom: 0.2rem solid rgba(37, 99, 235, 1);

          @media(max-width: 1024px) {
            width: 100%;
            border-width: .5rem;
          }


          & h2,
          h3,
          h4,
          h5,
          h6,
          span {
            color: rgba(37, 99, 235, 1);
            font-size: 2.4rem;

            @media(max-width: 1024px) {
              font-size: 4rem;
              line-height: 110%;
            }
          }

          & span {
            font-size: 1.2rem;

            @media(max-width: 1024px) {
              font-size: 3rem;
              line-height: 100%;
            }

          }
        }

        &-cards {
          display: flex;
          align-items: flex-start;
          justify-content: flex-start;
          flex-wrap: wrap;
          max-width: 55%;
          row-gap: 10px;
          column-gap: 10px;

          @media(max-width: 1024px) {
            flex-direction: row;
          }

          @media(max-width: 768px) {
            max-width: 80%;
            width: 100%;
            margin-top: 2rem;
          }

          @media(max-width: 500px) {
            max-width: 100%;
          }

          @media(max-width: 400px){
            flex-direction: column;
          }

          &>div.sitespeed-card {
            background: rgba(37, 99, 235, 0.05);
            border: 0.1rem solid rgba(37, 99, 235, 1);
            color: rgba(37, 99, 235, 1);
            border-radius: 0.4rem;
            padding: 1.6rem;
            font-size: 1.2rem;
            line-height: 120%;
            display: flex;
            flex-direction: column;
            align-items: center;
            row-gap: 1.2rem;
            max-width: calc(100% / 2 - 10px);
            width: 100%;

            @media(max-width: 768px) {
              max-width: calc(100% / 2 - .5rem);
              height: 15rem;
              justify-content: center;
              row-gap: .6rem;
            }

            @media(max-width: 400px) {
              max-width: calc(100%);
            }

            &>h2,
            h3,
            h4,
            h5,
            h6,
            p {
              font-size: 2.2rem;

              @media(max-width: 768px) {
                font-size: 3rem;
                line-height: 100%;
              }
            }

            & span {
              font-size: 1.4rem;

              @media(max-width: 768px) {
                font-size: 1.6rem;
                line-height: 100%;
              }
            }
          }
        }
      }
    }
  }

  &-block {
    width: 100%;
    height: 100%;
  }
}

.card-speed {
  font-size: 1.6rem;
  line-height: 2rem;
}

.card-description {
  font-size: 1.3rem;
  line-height: 2rem;
}
</style>
