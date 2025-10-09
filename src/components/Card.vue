<script setup>
import { ref } from "vue";
import correctBig from "../assets/Fill 302.png";
import wrongBig from "../assets/Close.png";
import correctSmall from "../assets/Tick Square.png";
import wrongSmall from "../assets/Close Square.png";

const word = "unadmitted";
const translation = "недопущенный";
const isFlipped = ref(false);
const result = ref(null);

const flipCard = () => {
  isFlipped.value = !isFlipped.value;
};

const handleCorrect = () => {
  result.value = "correct";
};

const handleWrong = () => {
  result.value = "wrong";
};
</script>

<template>
  <div class="card" @click="flipCard">
    <div class="card__container" :class="{ flipped: isFlipped }">
      <div class="card__side card__side-front">
        <div class="card__wrapper">
          <p class="card__title">{{ word }}</p>
          <p class="card__text-bottom">перевернуть</p>
          <p class="card__text-top">01</p>
        </div>
      </div>

      <div class="card__side card__side-back">
        <div class="card__wrapper">
          <p class="card__title">{{ translation }}</p>
          <div v-if="result" class="card__top-icon">
            <img
              :src="result === 'correct' ? correctBig : wrongBig"
              :alt="result"
              class="top-icon-img"
            />
          </div>

          <div v-if="!result" class="card__icons">
            <button class="card__icons-button" @click.stop="handleWrong">
              <img :src="wrongSmall" alt="wrong" />
            </button>
            <button class="card__icons-button" @click.stop="handleCorrect">
              <img :src="correctSmall" alt="correct" />
            </button>
          </div>

          <p v-if="result" class="card__text-bottom">завершено</p>
          <p class="card__text-top">01</p>
        </div>
      </div>
    </div>
  </div>
</template>

<style scoped>
.card {
  width: 250px;
  height: 376px;
  perspective: 1000px;
  cursor: pointer;
}

.card__container {
  width: 100%;
  height: 100%;
  position: relative;
  transform-style: preserve-3d;
  transition: transform 0.6s ease;

  box-shadow: 0 4px 12px rgba(0, 0, 0, 0.2);
  border-radius: 16px;
  display: flex;
  justify-content: center;
  align-items: center;
}

.card__container.flipped {
  transform: rotateY(180deg);
}

.card__side {
  position: absolute;
  width: 100%;
  height: 100%;
  backface-visibility: hidden;
  display: flex;
  justify-content: center;
  align-items: center;
}

.card__side-back {
  transform: rotateY(180deg);
}

.card__wrapper {
  width: 212px;
  height: 320px;
  border: 2px solid #cce8ff;
  border-radius: 12px;
  margin: 28px 19px;
  flex-direction: column;
  position: relative;
  display: flex;
  justify-content: center;
  align-items: center;
}

.card__title {
  font-weight: 400;
  font-family: var(--font);
  font-size: 18px;
}

.card__text-bottom {
  position: absolute;
  bottom: -20px;
  font-weight: 700;
  font-family: var(--font);
  text-transform: uppercase;
  font-size: 12px;
  background: #fff;
}

.card__text-top {
  position: absolute;
  top: -23px;
  left: 14px;
  background: #fff;
  font-weight: 400;
  font-size: 14px;
  font-family: var(--font);
}

.card__icons {
  position: absolute;
  bottom: -13px;
  display: flex;
  gap: 32px;
}

.card__icons-button {
  background: #fff;
  border: none;
  cursor: pointer;
  width: 24px;
  height: 24px;
  border-radius: 50%;
  display: flex;
  align-items: center;
  justify-content: center;
  transition: transform 0.2s ease, background-color 0.2s ease;
}

.card__top-icon {
  position: absolute;
  top: -15px;
  left: 50%;
  transform: translateX(-50%);
  width: 28px;
  height: 28px;
  background: #fff;
  border-radius: 50%;
  display: flex;
  align-items: center;
  justify-content: center;
  box-shadow: 0 2px 6px rgba(0, 0, 0, 0.1);
  z-index: 10;
}

.top-icon-img {
  width: 32px;
  height: 32px;
  object-fit: cover;
}
</style>
