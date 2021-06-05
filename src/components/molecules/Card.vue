<template>
  <div :class="'card card--' + media.type">
    <h3 class="card__item--account-name">
      <img :src="iconUrl" alt="">@nathanf
    </h3>
    <p class="card__item--follower">
      {{ media.follower }}<span>FOLLOWERS</span>
    </p>
    <span
      :class="[
        statusClass
      ]"
    >
      <img :src="upDownIconUrl" alt="">{{ increaseDecrease }} today
    </span>
  </div>
</template>

<script>
export default {
  props: {
    media: {
      type: Object,
      required: true
    }
  },
  computed: {
    iconUrl: function() {
      return `/images/icon-${this.media.type}.svg`;
    },
    increaseDecrease: function() {
      return this.media.increase ?? this.media.decrease;
    },
    statusClass: function() {
      return ('increase' in this.media) ? 'card__item--status--increase' : 'card__item--status--decrease';
    },
    upDownIconUrl: function() {
      return ('increase' in this.media) ? '/images/icon-up.svg' : '/images/icon-down.svg';
    }
  }
}
</script>

<style lang="scss" scoped>
@import "@/styles/scss/_variable.scss";
%card {
  width: 100%;
  background-color: $bg-card;
  padding: 20px 0;
  border-radius: 5px;
  display: flex;
  flex-direction: column;
  align-items: center;
}
%status {
  display: flex;
  align-items: center;
  img {
    margin-right: 5px;
  }
}
.card {
  &--facebook {
    @extend %card;
    border-top: 2px solid $facebook-theme;
  }
  &--twitter {
    @extend %card;
    border-top: 2px solid $twitter-theme;
  }
  &--instagram {
    @extend %card;
    border-top: 2px solid transparent;
    border-image: $instagram-theme;
    border-image-slice: 1;
  }
  &--youtube {
    @extend %card;
    border-top: 2px solid $youtube-theme;
  }
  &__item {
    &--follower {
      &:not(:last-child) {
        margin-bottom: 20px;
      }
      font-size: $fs-900;
      font-weight: 700;
      display: flex;
      flex-direction: column;
      justify-content: center;
      align-items: center;
      span {
        font-size: $fs-500;
        color: $text-grey;
        letter-spacing: .4rem;
      }
    }
    &--account-name {
      &:not(:last-child) {
        margin-bottom: 20px;
      }
      display: flex;
      align-items: center;
      img {
        margin-right: 10px;
      }
    }
    &--status {
      &--increase {
        @extend %status;
        color: $lime-green;
      }
      &--decrease {
        @extend %status;
        color: $bright-red;
      }
    }
  }
}
</style>