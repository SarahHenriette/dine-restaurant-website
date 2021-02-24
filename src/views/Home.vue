<template>
  <div class="home">
    <HeaderHome/>
    <main>
      <EnjoyableLocally/>
      <Highlights/>
      <Sliders/>
      <section class="reservation">
          <h2>Ready to make a reservation ?</h2>
          <router-link to="/reservation" tag="button">Book a table</router-link>
      </section>
      <Footer/>
    </main>
  </div>
</template>

<script>
import HeaderHome from '@/components/HeaderHome'
import EnjoyableLocally from '@/components/EnjoyableLocally'
import Highlights from '@/components/Highlights'
import Sliders from '@/components/Sliders'
import Footer from '@/components/Footer'

export default {
  name: 'Home',
  components: {
    HeaderHome,
    EnjoyableLocally,
    Highlights,
    Sliders,
    Footer
  }
}
</script>

<style lang="scss" scoped>
  @import './public/sass/colors.scss';

  .reservation {
    width: 100%;
    height: 240px;
    background-image: url("/images/homepage/ready-bg-desktop@2x.jpg");
    background-size: cover;
    background-repeat: no-repeat;
    position: relative;
    h2 {
      color: $white;
      top: 92px;
      left: 165px;
      margin: 0;
    }
    button {
      width: 245px;
      background-color: transparent;
      top: 88px;
      right: 165px;
    }

    h2, button {
      position: absolute;
    }
  }

   @media screen and (max-width: 1200px) {
      .reservation {
        height: 272px;
        background-size: cover;
            h2 {
          top: 65px;
          left: 0;
          right: 0;
          margin: auto;
          text-align: center;
        }
        button {
          top: 144px;
          left: 0;
          right: 0;
          margin: auto;
        }
      }
   }

    @media screen and (max-width: 769px) {
      .reservation {
        background-image: url("/images/homepage/ready-bg-tablet@2x.jpg");
        background-size: contain;
      }
    }

    @media screen and (max-width: 600px) {
      .reservation {
        height: 328px;
        background-image: url("/images/homepage/ready-bg-mobile@2x.jpg");
        background-size: cover;
        h2 {
          font-size: 32px!important;
          line-height: 40px!important;
          top: 80px;
        }
        button {
          top: 184px;
        }
      }
    }


</style>