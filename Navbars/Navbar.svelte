<script>
    import import1 from '../lib/hh.svelte'
    import import2 from '../lib/hh.svelte'
    import import3 from '../lib/hh.svelte'
    import import4 from '../lib/hh.svelte'
    
let click = 'notActive';
function clickChanger() {
//    changes click ('active') to 'notActive'

  if (click === 'active') {
      click = 'notActive';
  } else{
      click = 'active';
  }
}


let visible = 1;


function toggle2(){
    visible = 2;
}
function toggle3(){
    visible = 3;
}
function toggle4(){
    visible = 4;
}

</script>


<!-- Navbar Starts -->

<!-- svelte-ignore a11y-click-events-have-key-events -->
<div class="menu-toggle" class:active="{click === 'active'}" on:click={clickChanger}>
  <span></span>
  <span></span>
  <span></span>
</div>
<!-- svelte-ignore a11y-click-events-have-key-events -->
<nav class="nav"  class:active="{click === 'active'}" on:click={clickChanger}>
  <div class="nav-left"  class:active="{click === 'active'}" on:click={clickChanger}>
      <ul>
          <li class="nav-link" class:active="{click === 'active'}" on:click={clickChanger} on:click={toggle4}><a href="#" class="large">Link</a></li>
          <li class="nav-link" class:active="{click === 'active'}" on:click={clickChanger} on:click={toggle3}><a href="#" class="large">Link</a></li>
          <li class="nav-link" class:active="{click === 'active'}" on:click={clickChanger} on:click={toggle2}><a href="#" class="large">Link</a></li>
      </ul>
      <div class="contact"  class:active="{click === 'active'}" on:click={clickChanger}>
          <p class="large">Get In Touch</p>
          <p class="small">Discord</p>
      </div>
  </div>
  <div class="nav-right"  class:active="{click === 'active'}" on:click={clickChanger}></div>
</nav>
<!-- svelte-ignore a11y-click-events-have-key-events -->
<div class="logo"  class:active="{click === 'active'}" on:click={clickChanger}>Title</div>



<!-- Navbar ends -->

{#if visible === 1}
<import1 />
{:else if visible === 2}
<import2 />
{:else if visible === 3}
<import3 />
{:else}
<import4 />
{/if}

<!-- <Projects /> -->





<style>
  a {
      text-decoration: none;
      color: #000000;
  }

  a:hover {
      opacity: 0.5;
  }

  .large {
      font-size: 1.2rem;
      text-transform: uppercase;
  }

  .small {
      font-size: 0.8rem;
      color: #161616a9;
  }

  /*menu time*/

  .menu-toggle {
      position: fixed;
      z-index: 9999;
      right: 5%;
      top: 4rem;
      width: 2rem;
      height: 2rem;
      cursor: pointer;
      display: flex;
      flex-direction: column;
      justify-content: space-around;
      transition: 0.5s;
  }

  .menu-toggle.active {
      transform: rotate(-180deg);
  }

  .menu-toggle span {
      background: #fff;
      width: 100%;
      height: 3px;
  }

  .menu-toggle.active span:nth-child(1) {
      position: absolute;
      background: #ffffff;
      top: 50%;
      left: 50%;
      transform: translate(-50%, -50%) rotate(45deg);
  }

  .menu-toggle.active span:nth-child(2) {
      opacity: 0;
  }

  .menu-toggle.active span:nth-child(3) {
      position: absolute;
      background: #fff;
      top: 50%;
      left: 50%;
      transform: translate(-50%, -50%) rotate(-45deg);
  }

  /*here comes nav*/
  nav {
      position: fixed;
      height: 100vh;
      width: 100%;
      z-index: 100;
      pointer-events: none;
  }

  .nav.active {
      pointer-events: auto;
  }

  .nav-left {
      position: relative;
      z-index: 10;
      left: -50%;
      top: 0;
      width: 50%;
      height: 100vh;
      /*Prev NAVLEFTLL bg color*/
      background-color: var(--bg-color-light);
      transition: 0.8s;
  }

  .nav-left.active {
      transition: 0.5s;
      left: 0;
      /*NavLeftLL bg color*/
      background-color: var(--bg-color-light);
  }

  .nav-left ul {
      position: relative;
      top: 35%;
      left: 10%;
      height: 30%;
      display: flex;
      flex-direction: column;
      justify-content: space-around;
      list-style: none;
  }

  .nav-right {
      position: absolute;
      z-index: 9;
      left: -50%;
      top: 0;
      width: 50%;
      height: 100vh;
      /* navrightLL bg color*/
      /* background-color: #9D3C72; */
      background-color: var(--bg-color-dark);
      transition: 0.8s;
  }

  .nav-right.active {
      left: 50%;
      transition: 0.5s;
  }

  .nav-link {
      opacity: 0;
      position: relative;
      left: -10%;

  }

  .nav-link.active {
      opacity: 1;
      position: relative;
      transition: 0.5s;
      left: 0;
      z-index: 50;

  }

  .contact {
      position: absolute;
      opacity: 0;
      bottom: 10%;
      left: 0;
      pointer-events: none;
  }

  .contact.active {
      opacity: 1;
      left: 10%;
      transition: 0.5s;
  }

  .logo {
      position: fixed;
      top: 4rem;
      left: 5%;
      z-index: 100;
      color: #ffffff;
      font-size: 1.5rem;
      text-transform: uppercase;
      pointer-events: none;
      transition: 1s;
  }

  .logo.active {
      color: #000000;
  }


</style>
