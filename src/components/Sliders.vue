<template>
     <section class="sliders">
        <svg xmlns="http://www.w3.org/2000/svg" class="background-top" width="895" height="320"><path fill="#5C6779" fill-rule="evenodd" d="M795 0H0v320h895V100C895 44.772 850.228 0 795 0z" opacity=".077"/></svg>
        <svg xmlns="http://www.w3.org/2000/svg" class="lines-decoration" width="160" height="76"><g fill="#9E7F66" fill-rule="evenodd"><path d="M0 70h160v6H0zM0 56h160v6H0zM0 42h160v6H0zM0 28h160v6H0zM0 14h160v6H0zM0 0h160v6H0z"/></g></svg>
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
              <li class="h3-bis active">Family gathering</li>
              <li class="h3-bis">Special events</li>
              <li class="h3-bis">social events</li>
            </ul>
          </div>
        </div>
      </section>
</template>


<style lang="scss" scoped>
  @import './public/sass/colors.scss';

  .sliders {
    width: 100%;
    height: 920px;
    display: flex;
    justify-content: center;
    align-items: center;
    position: relative;
    .background-top {
      position: absolute;
      top: 0;
      left: -350px;
    }
    .lines-decoration {
      position: absolute;
      top: 122px;
      left: 125px;
      z-index: 10;
    }
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
          .active::before {
            content: "";
            width: 95px;
            height: 1px;
            background-color: $primary;
          }
        }
      }
    }
  }

  @media screen and (max-width: 1200px) {
    .sliders {
      flex-direction: column;
      .background-top {
          left: -517px;
      }
      .lines-decoration {
          left: 39px;
          top: 82px;
      }
      .slider {
          flex-direction: column;
          width: 689px;
          height: 781px;
          align-items: center;
        .image-slide {
            width: 573px;
            height: 360px;
            background-image: url("/images/homepage/family-gathering-tablet@2x.jpg");
        }
        .text-slide {
            width: 475px;
            height: 288px;
            top: auto;
            bottom: 0;
            left: 0;
            right: 0;
            margin: auto;
            align-items: center;
            p {text-align: center;}
        }
        .nav-slide {
            width: 689px;
            height: 37px;
            bottom: 328px;
            ul {
                width: 689px;
                height: 37px;
                flex-direction: row;
            }
        }
      }
    }
  }
  @media screen and (max-width: 600px) {
      .sliders {
          height: 1044px;
          .background-top, .lines-decoration {
              display: none;
          }
          .slider {
              width: 326px;
              height: 840px;
            .image-slide {
               width: 326px;
               height: 400px; 
               background-image: url("/images/homepage/family-gathering-mobile@2x.jpg");
            }
            .text-slide {
                width: 326px;
                height: 252px;
                h2 {
                    font-size: 32px!important;
                    line-height: 40px!important;
                }
                p {
                    font-size: 15px!important;
                    line-height: 25px!important;
                }
            }
            .nav-slide {
                width: 326px;
                height: 116px;
                bottom: 295px;
                ul {
                    flex-direction: column;
                    align-items: center;
                    height: 116px;
                }
            }
          }
      }
  }
</style>