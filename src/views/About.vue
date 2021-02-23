<template>
  <div class="about">
    <HeaderReservation/>
    <section class="background">
        <svg xmlns="http://www.w3.org/2000/svg" class="background-curve" width="993" height="320"><path fill="#5C6779" fill-rule="evenodd" d="M893 320H0V0h993v220c0 55.228-44.772 100-100 100z" opacity=".077"/></svg>
        <svg xmlns="http://www.w3.org/2000/svg" class="background-decoration-lines" width="160" height="76"><g fill="#9E7F66" fill-rule="evenodd"><path d="M0 70h160v6H0zM0 56h160v6H0zM0 42h160v6H0zM0 28h160v6H0zM0 14h160v6H0zM0 0h160v6H0z"/></g></svg>
    </section>
    <form action=""  @submit.prevent="submit">
      <input type="text" placeholder="Name" name="name" id="name" v-model="name.value" :class="name.error">
      <div :class="name.error" v-if="name.messageError.length > 0" class="containError"><span v-for="message in name.messageError" :key="message">{{ message }}</span></div>

      <input type="email" placeholder="Email" v-model="email.value" :class="email.error">
      <div :class="email.error" v-if="email.messageError.length > 0" class="containError"><span v-for="message in email.messageError" :key="message">{{ message }}</span></div>

      <div class="input-date"><label for="date" :class="date.error">Pick a date</label><div class="contains-date"><input type="number" class="contain-date" min="01" max="12" placeholder="MM" v-model="date.valueMonth" :class="date.error"><input type="number" class="contain-date" min="01" max="31" placeholder="DD" v-model="date.valueDay" :class="date.error"><input type="number" class="contain-date" min="2021" max="2022" placeholder="YYYY"  v-model="date.valueYear" :class="date.error"></div></div>
      <div :class="date.error" v-if="date.messageError.length > 0" class="containError contain-date"><span v-for="message in date.messageError" :key="message">{{ message }}</span></div>

      <div class="input-time"><label for="time" :class="time.error">Pick a time</label><div class="contains-time"><input type="number" class="contain-time" min="08" max="23" placeholder="09" v-model="time.valueHours" :class="time.error"><input type="number" class="contain-time" min="00" max="59" placeholder="00" v-model="time.valueMinutes" :class="time.error"><input type="text" class="contain-time"  placeholder="AM" v-model="time.valueMoment" :class="time.error"></div></div>
      <div :class="time.error" v-if="time.messageError.length > 0" class="containError contain-time"><span v-for="message in time.messageError" :key="message">{{ message }}</span></div>
      
      <div class="input-number-person">
        <span @click="decrementPeople" class="moins">-</span>
        <p><span>{{ nbrPeople }}</span> people</p>
        <span @click="incrementPeople" class="plus">+</span>
      </div>
      <input type="submit"  value="make reservation" id="btn-submit">
      <!-- <router-link to="/reservation" tag="button">make reservation</router-link> -->
    </form>
    <Footer/>
  </div>
</template>

<script>
import Footer from '@/components/Footer'
import HeaderReservation from '@/components/HeaderReservation'

export default {
  data () {
    return {
      name: {
        value: "",
        error: "",
        messageError: []
      },
      email: {
        value: "",
        error: "",
        messageError: []
      },
      time: {
        valueHours: "",
        valueMinutes: "",
        valueMoment: "",
        error: "",
        messageError: []
      },
      date: {
        valueMonth: "",
        valueDay: "",
        valueYear: "",
        error: "",
        messageError: []
      },
      nbrPeople: 4
    }
  },
  components: {
    Footer,
    HeaderReservation
  },
  methods: {
    decrementPeople() {
      this.nbrPeople = this.nbrPeople - 1
    },
    incrementPeople() {
      this.nbrPeople = this.nbrPeople + 1
    },
    submit() {
      console.log('okkk')
 
          this.verifyInputEmpty(this.name)
          this.verifyInputEmpty(this.email)
          this.verifyInputEmptyDate(this.date)
          this.verifyInputEmptyTime(this.time)
          this.verifyValidEmail()

    if(this.name.value !== "" && this.email.value !== "" && this.time.valueHours !== "" && this.time.valueMinutes !== ""  && this.time.valueMoment !== ""
    && this.date.valueMonth !== "" && this.date.valueDay !== "" && this.date.valueYear !== ""
    ) {
          alert('Votre message à bien été envoyé')
          this.name.value = ""
          this.email.value= ""
          this.time.valueHours = ""
          this.time.valueMinutes = ""
          this.time.valueMoment = ""
          this.date.valueMonth = ""
          this.date.valueDay = ""
          this.date.valueYear = ""
        }
    },

    verifyInputEmpty(variable) {
       variable.messageError = []
        if(!variable.value){
          console.log("tu fais chier ta race")
          variable.error = "error"
          variable.messageError.push("This field is required")
        } 
    },
    verifyInputEmptyDate(variable) {
       variable.messageError = []
        if (!variable.valueMonth || !variable.valueDay || !variable.valueYear) {
           variable.error = "error"
          variable.messageError.push("This field is incomplete")
        }
    },
      verifyInputEmptyTime(variable) {
       variable.messageError = []
        if (!variable.valueHours || !variable.valueMinutes || !variable.valueMoment) {
           variable.error = "error"
          variable.messageError.push("This field is incomplete")
        }
    },
      verifyValidEmail() {
        let emailValid = /^[a-zA-Z0-9.!#$%&'*+/=?^_`{|}~-]+@[a-zA-Z0-9-]+(?:\.[a-zA-Z0-9-]+)*$/
        if(emailValid.test(this.email.value) ) {
          return true
        }
        this.email.messageError.push("This address is not valid")
        this.email.error = "error"
      }
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
    justify-content:space-evenly;
    align-items: center;
    // padding: 48px;
    .error {
      color: red;
      font-size: 10px;
    }
    .containError {
      width: 444px;
      position: relative;
      top: -9px;
    }
    .contain-date, .contain-time {
      top: -23px;

    }
    input{
      border: none;
      border-bottom: 1px solid $primaryBackground;
      opacity: 0.5;
      width: 444px;
      height: 45px;
    }
    input.error {
      border-bottom: 1px solid red;
      color: red;
      font-size: 15px;
      &::placeholder {
        color: red;
      }
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
      .error {
        color: red;
        font-size: 15px;
      }
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
      .plus, .moins {
        width: 20px;
        height: 20px;
        margin-bottom: 0;
      }
    }
    input[type="submit" i] {
      width: 444px;
      background-color: $primaryBackground;
      opacity: 1;
      text-transform: uppercase;
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