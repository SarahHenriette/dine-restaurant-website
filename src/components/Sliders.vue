<template>
     <section class="sliders">
        <svg xmlns="http://www.w3.org/2000/svg" class="background-top" width="895" height="320"><path fill="#5C6779" fill-rule="evenodd" d="M795 0H0v320h895V100C895 44.772 850.228 0 795 0z" opacity=".077"/></svg>
        <svg xmlns="http://www.w3.org/2000/svg" class="lines-decoration" width="160" height="76"><g fill="#9E7F66" fill-rule="evenodd"><path d="M0 70h160v6H0zM0 56h160v6H0zM0 42h160v6H0zM0 28h160v6H0zM0 14h160v6H0zM0 0h160v6H0z"/></g></svg>
        <div class="slider">
          <div class="image-slide family active"></div>
          <div class="text-slide active">
            <h2>Family Gathering</h2>
            <p class="text-1">We love catering for entire families. So please bring everyone along for a special meal with your loved ones. We’ll provide a memorable experience for all.</p>
            <router-link to="/reservation" tag="button">Book a table</router-link>
          </div>
          <div class="image-slide special"></div>
          <div class="text-slide">
            <h2>Special Events</h2>
            <p class="text-1">Whether it’s a romantic dinner or special date you’re celebrating with others we’ll look after you. We’ll be sure to mark your special date with an unforgettable meal.</p>
            <router-link to="/reservation" tag="button">Book a table</router-link>
          </div>
          <div class="image-slide social"></div>
          <div class="text-slide">
            <h2>Social Events</h2>
            <p class="text-1">Are you looking to have a larger social event? No problem! We’re more than happy to cater for big parties. We’ll work with you to make your event a hit with everyone.</p>
            <router-link to="/reservation" tag="button">Book a table</router-link>
          </div>
          <div class="nav-slide">
            <!-- <div class="line-slide"></div> -->
            <ul>
              <li class="h3-bis active"><div class="line-slide"></div>Family gathering</li>
              <li class="h3-bis"><div class="line-slide"></div>Special events</li>
              <li class="h3-bis"><div class="line-slide"></div>social events</li>
            </ul>
          </div>
        </div>
      </section>
</template>

<script>
export default {
  
  methods: {
   
  },
   mounted () {
      let images = document.querySelectorAll('.image-slide')
      let textSlide = document.querySelectorAll('.text-slide')
      let lineSlide = document.querySelectorAll('ul .h3-bis')


      console.log(images)
      console.log(textSlide)
      console.log(lineSlide)


  let i = 0

      setInterval(() => {
        console.log(i)
        if(images[i].classList.contains('active')) {
            images[i].classList.remove('active')
            textSlide[i].classList.remove('active')
            lineSlide[i].classList.remove('active')

            images[i + 1].classList.add('active')
            textSlide[i + 1].classList.add('active')
            lineSlide[i + 1].classList.add('active')

            i = i + 1
        }
        if(i == images.length-1) {
          setTimeout(() => {
            images[i].classList.remove('active')
            textSlide[i].classList.remove('active')
            lineSlide[i].classList.remove('active')

            i= 0
            images[i].classList.add('active')
            textSlide[i].classList.add('active')
            lineSlide[i].classList.add('active')


          }, 5000);
        }
      }, 5000);

    
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
        background-size: contain;
        background-repeat: no-repeat;
        display: none;
        animation: imageSlide .5s linear;
        z-index: 6;
      }

      @keyframes imageSlide {
        0% { margin-left: 40px}
        100% {margin-left: 0px;}
      }
      .family{
        background-image: url("/images/homepage/family-gathering-desktop@2x.jpg");
      }
      .special {
        background-image: url("/images/homepage/special-events-desktop@2x.jpg");
      }
      .social {
        background-image: url("/images/homepage/social-events-desktop@2x.jpg");
      }
      
      .text-slide {
        width: 445px;
        height: 288px;
        display: flex;
        flex-direction: column;
        position: absolute;
        right: 0;
        top: 63px;
        display: none;
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
      .active {
        display: flex;
      }
      .nav-slide {
        width: 570px;
        height: 108px;
        display: flex;
        justify-content: space-between;
        position: absolute;
        bottom: 63px;
        right: 0px;
        .line-slide {
          width: 95px;
          height: 1px;
          background-color: transparent;
          margin-right: 30px;

        }
        ul {
          padding-left: 0;
          margin: 0;
          height: 108px;
          width: 332px;
          display: flex;
          flex-direction: column;
          justify-content: space-between;
          li {
            list-style-type: none;
            text-align: left!important;
            display: flex;
            align-items: center;

          }
          .active {
             .line-slide {
                background-color: $primary;
              }
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