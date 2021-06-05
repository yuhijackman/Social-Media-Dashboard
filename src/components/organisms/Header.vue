<template>
  <header class="header">
    <div class="header__content">
      <h1 class="title">
        Social Media Dashboard
        <span>Total Followers: 23,004</span>
      </h1>
      <div class="switcher-container">
        <div class="switcher">
          <span>Dark Mode</span>
          <label class="switch">
            <input type="checkbox">
            <span class="switch__slider"></span>
          </label>
        </div>
      </div>
    </div>
  </header>
</template>

<style lang="scss" scoped>
@import "@/styles/scss/_variable.scss";
.header {
  &__content {
    display: flex;
    justify-content: space-between;
    .title {
      font-size: $fs-700;
      font-weight: 700;
      display: flex;
      flex-direction: column;
      span {
        line-height: 1.8rem;
        font-size: $fs-500;
        font-weight: 700;
        color: $text-grey;
      }
    }
  }
  .switcher {
    display: flex;
    align-items: center;
    span {
      line-height: 1.8rem;
      font-size: $fs-500;
      font-weight: 700;
      color: $text-grey;
      margin-right: 10px;
    }
  }
  .switch {
    position: relative;
    display: inline-block;
    width: 60px;
    height: 20px;
    input {
      opacity: 0;
      width: 0;
      height: 0;
      &:checked + .switch__slider {
        background-color: #ccc;
        background-image: unset;
      }
      &:checked + .switch__slider:before {
        transform: translateX(24px);
      }
    }
    &__slider {
      position: absolute;
      cursor: pointer;
      top: 0;
      left: 0;
      right: 0;
      bottom: 0;
      background-image: linear-gradient(to bottom, hsl(210, 78%, 56%), hsl(146, 68%, 55%));
      transition: .4s;
      border-radius: 20px;
      &:before {
        position: absolute;
        content: "";
        height: 18px;
        width: 18px;
        left: 4px;
        bottom: 1px;
        background-color: hsl(230, 41%, 20%);
        -webkit-transition: .4s;
        transition: .4s;
        border-radius: 50%;
      }
    }
  }
}
@media only screen and (max-width: 500px) {
  .header {
    &__content {
      flex-direction: column;
      .title {
        padding-bottom: 15px;
        border-bottom: 1px solid $text-grey;
      }
      .switcher-container {
        padding-top: 15px;
      }
    }
  }
}
</style>