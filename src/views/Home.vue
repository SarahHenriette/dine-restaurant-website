<template>
  <div class="home">
    <HeaderHome/>
    <main>
      <EnjoyableLocally/>
      <Highlights/>
      <section class="sliders">
        <div class="slider">
          <div class="image-slide"></div>
          <div class="text-slide">
            <h2>Family Gathering</h2>
            <p class="text-1">We love catering for entire families. So please bring everyone along for a special meal with your loved ones. We’ll provide a memorable experience for all.</p>
            <router-link to="/reservation" tag="button">Book a table</router-link>
          </div>
          <div class="nav-slide">
            <!-- <div class="line-slide"></div> -->
            <ul>
              <li class="h3-bis">Family gathering</li>
              <li class="h3-bis">Special events</li>
              <li class="h3-bis">social events</li>
            </ul>
          </div>
        </div>
      </section>
    </main>
  </div>
</template>

<script>
import HeaderHome from '@/components/HeaderHome'
import EnjoyableLocally from '@/components/EnjoyableLocally'
import Highlights from '@/components/Highlights'

export default {
  name: 'Home',
  components: {
    HeaderHome,
    EnjoyableLocally,
    Highlights
  }
}
</script>

<style lang="scss" scoped>
  @import './public/sass/colors.scss';

  .sliders {
    width: 100%;
    height: 920px;
    display: flex;
    justify-content: center;
    align-items: center;
    .slider {
      width: 1110px;
      height: 600px;
      display: flex;
      position: relative;
      .image-slide {
        width: 540px;
        height: 600px;
        background-image: url("/images/homepage/family-gathering-desktop@2x.jpg");
        background-size: contain;
        background-repeat: no-repeat;
      }
      .text-slide {
        width: 445px;
        height: 288px;
        display: flex;
        flex-direction: column;
        position: absolute;
        right: 0;
        top: 63px;
        h2 {
          margin: 0;
        }
        p {
          margin-top: 16px;
          margin-bottom: 32px;
        }
        button {
          width: 245px;
          background-color: $primaryBackground;
        }
      }
      .nav-slide {
        width: 445px;
        height: 108px;
        display: flex;
        justify-content: space-between;
        position: absolute;
        bottom: 63px;
        right: 0px;
        // .line-slide {
        //   width: 95px;
        //   height: 1px;
        //   background-color: $primary;
        // }
        ul {
          padding-left: 0;
          margin: 0;
          height: 108px;
          width: 188px;
          display: flex;
          flex-direction: column;
          justify-content: space-between;
          li {
            list-style-type: none;
            text-align: left!important;
          }
        }
      }
    }
  }
</style>