<template>
  <div class="about">
    <div class="about__container">
      <div>Why choose Easybank?</div>
      <p>
        We leverage Open Banking to turn your bank account into your financial hub. Control your
        finances like never before.
      </p>
    </div>
  </div>
</template>

<script setup></script>

<style lang="scss" scoped>
.about {
  background-color: $light-grayish-blue;
  width: 100%;
  height: 700px;
  display: flex;
  align-items: center;
  justify-content: center;

  &__container {
    width: $width-desktop;
  }
}
</style>
