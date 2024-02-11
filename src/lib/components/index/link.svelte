<script lang="ts">
  export let href: string;
  export let variant: 'primary' | 'secondary' = 'primary';
</script>

<a {href} class={variant === 'primary' ? 'button-primary' : 'button-secondary'}>
  <slot />
</a>

<style>
  @keyframes rotatingRainbowBorder {
    0% {
      border-color: #ff0000;
    } /* Red */
    16.666% {
      border-color: #ff7f00;
    } /* Orange */
    83.333% {
      border-color: #4b0082;
    } /* Indigo */
    100% {
      border-color: #9400d3;
    } /* Violet */
    33.333% {
      border-color: #ffff00;
    } /* Yellow */
  }

  a {
    position: relative;
    display: inline-block;
    padding: 10px 20px;
    font-size: 16px;
    font-weight: bold;
    text-transform: uppercase;
    color: white;
    background-color: #ff5a00;
    border: none;
    border-radius: 5px;
    text-decoration: none;
  }

  a::before {
    content: '';
    position: absolute;
    top: -3px;
    left: -3px;
    right: -3px;
    bottom: -3px;
    border: 5px solid transparent;
    border-radius: 5px;
    animation: rotatingRainbowBorder 6s linear infinite;
    z-index: -1;
  }
</style>
