<script>
  import { link } from "svelte-routing";
  import iconArrowWhite from "../assets/icons/icon-arrow-white.svg";
</script>

<section class="home-small-team">
  <h2>Small team, <br />big ideas</h2>
  <a href="/about" use:link
    >About Us <img src={iconArrowWhite} alt="arrow icon" /></a
  >
</section>

<style lang="scss">
  .home-small-team {
    width: 100%;
    display: flex;
    flex-direction: column;
    gap: 24px;
    padding: 180px 32px;
    background: url("/src/assets/home/mobile/image-small-team.jpg"),
      rgba(0, 0, 0, 0.35);
    background-repeat: no-repeat;
    background-size: 100%;
    background-position: bottom;
    background-blend-mode: multiply;
    transition-property: background-size;
    transition-timing-function: cubic-bezier(0.4, 0, 0.2, 1);
    transition-duration: 1000ms;

    &:hover {
      background-size: 120%;
    }

    h2 {
      color: #fff;
      font-size: 48px;
      font-style: normal;
      font-weight: 700;
      line-height: 52px;
      letter-spacing: -1.714px;
    }

    a {
      width: max-content;
      height: 72px;
      padding: 24px 32px 24px 37px;
      color: #fff;
      font-size: 18px;
      font-style: normal;
      font-weight: 700;
      line-height: 25px; /* 138.889% */
      background: var(--very-dark-blue);
      display: flex;
      align-items: center;
      gap: 24px;

      &:hover {
        background: var(--dark-grey);
      }

      &:active {
        background: var(--light-grey);
      }
    }
  }

  @media screen and (min-width: 768px) {
    .home-small-team {
      padding: 168px 64px;
      background: url("/src/assets/home/tablet/image-small-team.jpg"),
        rgba(0, 0, 0, 0.35);
      background-repeat: no-repeat;
      background-size: 100%;
      background-position: bottom;
      background-blend-mode: multiply;

      h2 {
        font-size: 72px;
        line-height: 64px;
        letter-spacing: -2px;
      }
    }
  }
</style>
