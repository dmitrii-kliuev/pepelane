<template>
  <div class="error" :class="theme.block2">
    <div class="error__msgOne" :class="theme.title">An error has occurred</div>
    <div class="error__msgTwo" :class="theme.text">Please refresh the page</div>
    <button class="error__button">Reload page</button>
  </div>
</template>

<script>
import { mapState } from 'vuex'

export default {
  name: 'Error',
  computed: {
    ...mapState('vehicle', {
      theme: (state) => state.theme,
    }),
  },
}
</script>

<style scoped>
.error {
  margin-top: 40px;
  display: flex;
  flex-direction: column;
  align-items: center;
  border-radius: 48px;
  justify-content: center;
  flex: 1;

  &__msgOne {
    font-family: var(--f-bold);
    font-size: 40px;
  }

  &__msgTwo {
    margin-top: 24px;
    font-family: var(--f-reg);
    font-size: 14px;
  }

  &__button {
    margin-top: 40px;
    font-family: var(--f-bold);
    color: var(--c-alabaster);
    background-color: var(--c-dodger-blue);
    border: none;
    border-radius: 12px;
    width: 161px;
    height: 48px;
    font-size: 16px;
    user-select: none;
    cursor: pointer;

    &:hover {
      background-color: var(--c-blue);
    }
  }
}

@media (max-width: 700px) {
  .error {
    margin-top: 8px;
    border-radius: 24px;
    margin-bottom: 20px;

    &__msgOne {
      font-size: 24px;
    }

    &__msgTwo {
      margin-top: 16px;
    }

    &__button {
      font-size: 14px;
    }
  }
}
</style>
