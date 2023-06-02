<template>
  <div class="box" :class="{ direction: backgroundDirection === 'right' }">
    <section class="title">
      {{ title }}
    </section>

    <section class="content">
      <slot />
    </section>
  </div>
</template>

<script>
export default {
  name: 'Box',

  props: {
    title: {
      type: String,
      default: ''
    },
    backgroundDirection: {
      type: String,
      default: 'left'
    }
  }
}
</script>

<style lang="scss" scoped>
.box {
  width: 100%;
  height: 100%;
  display: flex;
  flex-direction: column;
  background: linear-gradient(
    -90deg,
    rgba(23, 80, 149, 0.2) 0%,
    rgba(1, 16, 42, 0.2) 100%
  );
  border-radius: 10px;
  overflow: hidden;

  .title {
    width: 430px;
    height: 36px;
    background: url('~@/assets/images/title.png');
    background-size: 100% 100%;
    display: flex;
    align-items: center;
    padding: 0 60px 3px;
    font-size: 22px;
    font-family: YouSheBiaoTiHei;
    font-weight: 400;
    color: #ffffff;
    margin-left: -35px;
  }

  .content {
    width: 100%;
    flex: 1 0;
    overflow: hidden;
    padding: 20px 15px;
  }
}

.direction {
  background: linear-gradient(
    90deg,
    rgba(23, 80, 149, 0.2) 0%,
    rgba(1, 16, 42, 0.2) 100%
  );
}
</style>
