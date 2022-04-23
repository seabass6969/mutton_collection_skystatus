<style>
@keyframes spinner {
        0% {
          transform: translate3d(-50%, -50%, 0) rotate(0deg);
        }
        100% {
          transform: translate3d(-50%, -50%, 0) rotate(360deg);
        }
      }
.spin {
    position: absolute;
    top: 50%;
    left: 50%;
    display: block;
    width: 50vw;
    margin: auto auto auto auto;
    animation: 1.5s linear infinite spinner;
}
</style>
<img src="/Villager.webp" alt="villager thinking" class="spin">

