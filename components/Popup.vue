<template>
  <div class="popup">
    <img
      src="/popupCross.svg"
      alt
      class="popup__cross"
      @click="$emit('closeClick')"
    />
    <quiz />
  </div>
</template>

<script>
import Qiuz from '@/components/Quiz';
export default {
  components: {
    quiz: Qiuz,
  },
};
</script>

<style scoped>
.popup {
  padding: 0;
  display: flex;
  flex-direction: column;
  position: fixed;
  left: 50%;
  top: 50%;

  background: #fff;
  z-index: 2;
  transform: translate(-50%, -50%);
}
.popup__headings {
  display: flex;
  flex-direction: row;
  justify-content: space-between;
}
.popup__cross {
  width: 100%;
  position: fixed;
  top: 35px;
  left: calc(100% - 50px);
  width: 20px;
  height: 20px;
  cursor: pointer;
}
.popup__title {
  font-weight: 600;
  font-size: 32px;
  line-height: 36px;
  color: #000;
}
.popup__question {
  font-weight: normal;
  font-size: 18px;
  line-height: 24px;
  color: #666;
  margin-top: 40px;
}
.popup__question_main {
  font-style: 500;
  color: #000;
}
.popup__form {
}
.popup__input {
  border: none;
  border-bottom: 1px solid #e7e7e7;
  width: 100%;
  padding-bottom: 10px;
  margin-top: 110px;
}
.popup__input::placeholder {
  font-size: 18px;
  line-height: 24px;
  color: #666;
}
.popup__form-container {
  display: flex;
  flex-direction: row;
  align-items: center;
  margin-top: 200px;
}
.popup__goback {
  margin-right: 30px;
  font-family: Inter;
  font-style: normal;
  font-weight: normal;
  font-size: 16px;
  line-height: 19px;
  color: #c0c0c0;
  cursor: default;
  text-decoration: none;
}
.goback_active {
  color: #666;
  cursor: pointer;
}
.popupButton {
  margin-right: 30px;
}
.popup__policy {
  display: none;
  font-family: Inter;
  font-style: normal;
  font-weight: normal;
  font-size: 14px;
  line-height: 17px;
  color: #666;
}
.showPolicy {
  display: inline;
}
.popup__policy-link {
  color: #666;
}

@media (max-width: 1440px) {
}
@media (max-width: 1280px) {
}
@media (max-width: 1024px) {
}
@media (max-width: 768px) {
  .popup {
    max-width: 580px;
    width: 95%;
    height: 520px;
  }
}

@media (max-width: 500px) {
  .popup__cross {
    top: 13px;
    left: calc(100% - 35px);
  }
}

@media (max-width: 320px) {
  .popup {
    width: 290px;
    height: 520px;
  }
}
</style>
