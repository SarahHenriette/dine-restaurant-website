<template>
  <div class="about">
    <HeaderReservation/>
    <section class="background">
        <svg xmlns="http://www.w3.org/2000/svg" class="background-curve" width="993" height="320"><path fill="#5C6779" fill-rule="evenodd" d="M893 320H0V0h993v220c0 55.228-44.772 100-100 100z" opacity=".077"/></svg>
        <svg xmlns="http://www.w3.org/2000/svg" class="background-decoration-lines" width="160" height="76"><g fill="#9E7F66" fill-rule="evenodd"><path d="M0 70h160v6H0zM0 56h160v6H0zM0 42h160v6H0zM0 28h160v6H0zM0 14h160v6H0zM0 0h160v6H0z"/></g></svg>
    </section>
    <form action="">
      <input type="text" placeholder="Name" name="name" id="name">
      <input type="email" placeholder="Email">
      <div class="input-date"><label for="date">Pick a date</label><div class="contains-date"><input type="number" class="contain-date" min="01" max="12" placeholder="MM"><input type="number" class="contain-date" min="01" max="31" placeholder="DD"><input type="number" class="contain-date" min="2021" max="2022" placeholder="YYYY"></div></div>
      <div class="input-time"><label for="time">Pick a time</label><div class="contains-time"><input type="number" class="contain-time" min="08" max="23" placeholder="09"><input type="number" class="contain-time" min="00" max="59" placeholder="00"><input type="text" class="contain-time"  placeholder="AM"></div></div>
      <div class="input-number-person">
        <span>-</span>
        <p><span>4</span> people</p>
        <span>+</span>
      </div>
      <router-link to="/reservation" tag="button">make reservation</router-link>
    </form>
    <Footer/>
  </div>
</template>

<script>
import Footer from '@/components/Footer'
import HeaderReservation from '@/components/HeaderReservation'

export default {
  components: {
    Footer,
    HeaderReservation
  }
}
</script>

<style lang="scss" scoped>
  @import './public/sass/colors.scss';
  .about {
    position: relative;
    .background {
    width: 100%;
    height: 320px;
    position: relative;
    .background-curve {
      position: absolute;
      left: 0;
      top: 0;
    }
    .background-decoration-lines {
      position: absolute;
      top: 165px;
      left: 655px;
    }
  }
  form {
    width: 540px;
    height: 545px;
    background-color: $white;
    position: absolute;
    top: 258px;
    right: 165px;
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    // padding: 48px;
    input{
      border: none;
      border-bottom: 1px solid $primaryBackground;
      opacity: 0.5;
      width: 444px;
      height: 45px;
    }
    label {
      width: 102px;
    }
    // input[type="date" i],  input[type="time" i]{
    //   width: 289px;
    // }
    // input[type="number" i]{
    //   width: 444px;
    //   height: 45px;
    // }
    .input-date, .input-time {
      width: 444px;
      display: flex;
      justify-content: space-between;
      align-items: center;
    }
    .input-date, .input-time {
      .contains-date, .contains-time {
        width: 289px;
        display: flex;
        justify-content: space-between;
      }
      .contain-date, .contain-time {
        width: 80px;
        margin: 0;
      }
    }
    .input-number-person {
      display: flex;
      justify-content: space-between;
      align-items: center;
      width: 444px;
      font-weight: bold;
      border-bottom: 1px solid $primaryBackground;
    }
    .input-date, .input-time, #name, input[type="email" i], .input-number-person{
      margin-bottom: 32px;
    }
    button {
      width: 444px;
      background-color: $primaryBackground;
    }
  
  }
  }
  
  @media screen and (max-width: 1200px) {
    .background {
      height: 435px!important;
      .background-curve, .background-decoration-lines {
        display: none;
      }
    }
       form {
      top: 370px!important;
      left: 0!important;
      right: 0!important;
      margin: auto!important;
    }
  }

@media screen and (max-width: 600px)  {
  form {
    width: 327px!important;
    height: 585px;
    .input-date, .input-time, #name, input[type="email" i], button {
      width: 263px!important;
    }
    .input-date, .input-time {
      width: 263px;
      flex-direction: column;
      align-items: flex-start!important;
    }
    .input-number-person {
       width: 263px!important;
    }
      .input-date, .input-time {
        .contains-date, .contains-time {
          width: 263px!important;
        }
      }
  }
}

</style>