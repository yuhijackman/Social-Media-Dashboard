<template>
  <div class="active-status-card">
    <h3 class="active-status-card__item--title">
      {{ status.type }} <img :src="iconUrl" alt="">
    </h3>
    <p class="active-status-card__item--content">
      {{ status.currentNumber }}
      <span
        :class="'percentage--' + status.percentage.type"
      >
        <img :src="'/images/icon-' + status.percentage.type + '.svg'" alt="">{{ status.percentage.number }} %
      </span>
    </p>
  </div>
</template>

<script>
export default {
  props: {
    status: {
      type: Object,
      required: true
    }
  },
  computed: {
    iconUrl: function() {
      return `/images/icon-${this.status.media}.svg`;
    },
  }
}
</script>

<style lang="scss" scoped>
@import "@/styles/scss/_variable.scss";
%item {
  display: flex;
  justify-content: space-between;
}
%percentage {
  font-size: $fs-500;
  display: flex;
  align-items: center;
  img {
    margin-right: 5px;
  }
}
.active-status-card {
  width: 100%;
  background-color: $bg-card;
  padding: 20px;
  border-radius: 5px;
  display: flex;
  flex-direction: column;
  &__item {
    &--title {
      @extend %item;
      align-items: center;
      font-size: $fs-600;
      font-weight: 700;
      color: $text-grey;
      margin-bottom: 20px;
    }
    &--content {
      @extend %item;
      align-items: flex-end;
      font-size: $fs-900;
      font-weight: 700;
      span {
        font-size: 1rem;
      }
      .percentage {
        &--up {
          @extend %percentage;
          color: $lime-green;
        }
        &--down {
          @extend %percentage;
          color: $bright-red;
        }
      }
    }
  }
}
</style>