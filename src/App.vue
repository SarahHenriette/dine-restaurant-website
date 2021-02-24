<template>
  <div id="app">
    <div id="nav">
      <!-- <router-link to="/">Home</router-link> |
      <router-link to="/about">About</router-link> -->
        <!-- <router-link to="/" tag="button">Home</router-link> -->
    </div>
    <router-view/>
  </div>
</template>

<style lang="scss">
body {
  margin: 0;
}
#app {
  @import url('https://fonts.googleapis.com/css2?family=Spartan:wght@300;400;600;700&display=swap');
  @import './public/sass/colors.scss';
  
  $fontSpartan: 'Spartan', sans-serif;

  h1, h2, h3, .h3-bis, .text-1, .text-2 {
    font-family: $fontSpartan;
    font-style: normal;
  }
  h2, h3 {
    font-weight: bold;
  }

  h1 {
    font-weight: 300;
    font-size: 64px;
    line-height: 72px;
    letter-spacing: -0.8px;
  }

  h2 {
    font-size: 40px;
    line-height: 56px;
    letter-spacing: -0.5px;
  }

  h3 {
    font-size: 18px;
    line-height: 28px;
    letter-spacing: -0.225px;
  }

  .h3-bis, button {
    font-weight: 600;
    font-size: 14px;
    line-height: 28px;
    text-transform: uppercase;
    text-align: center;
    letter-spacing: 2px;  
  }

  .text-1 {
    font-weight: normal;
    font-size: 18px;
    line-height: 30px;
    letter-spacing: -0.225px;
  }

  .text-2 {
      font-weight: normal;
      font-size: 15px;
      line-height: 28px;
      letter-spacing: -0.1875px;
  }

  button, input[type="submit" i] {
    height: 64px;
    cursor: pointer;
    color: white;
    border: 1px solid $white;
    transition: background-color linear .8s;
    &:focus {
      outline: none;
    }
    &:hover {
      background-color: $white;
      color: $primaryBackground;
      border: solid 1px $primaryBackground;
    }
  }
    label, .input-number-person, .error, select  {
        font-family: $fontSpartan;
    }
    input {
      font-size: 18px;
      &:focus {
        outline: none;
      }
      &::placeholder {
        font-family: $fontSpartan;
      }
    }

  .decoration-text {
    width: 71px;
    height: 7px;
    display: flex;
    justify-content: space-between;
    align-items: center;
    .circle {
    width: 7px;
    height: 7px;
    border-radius: 50%;
    border: solid 1px $primary;
    }
    .line {
      width: 56px;
      height: 1px;
      background-color: $primary;
    }
  }
}

</style>
