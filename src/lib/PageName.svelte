<script>
  export let name;
</script>

<div class="page-name">
  <div class="page-name__line"></div>
  <span class="page-name__text">{name}</span>
</div>

<style lang="scss">
  .page-name {
    display: none;
    position: fixed;
    align-items: center;
    gap: 48px;
    top: 0;
    left: 64px;
    transform: rotate(90deg);
    transform-origin: top left;

    &__line {
      width: 104px;
      height: 1px;
      background: var(--light-grey);
    }

    &__text {
      color: var(--light-grey);
      font-size: 18px;
      font-style: normal;
      font-weight: 500;
      line-height: 24px;
      letter-spacing: 18px;
      text-transform: uppercase;
    }
  }

  @media screen and (min-width: 768px) {
    .page-name {
      display: flex;
    }
  }
</style>
