<template>
    <section class="enjoyable-locally">
        <svg xmlns="http://www.w3.org/2000/svg" class="background-top" width="895" height="320"><path fill="#5C6779" fill-rule="evenodd" d="M795 0H0v320h895V100C895 44.772 850.228 0 795 0z" opacity=".077"/></svg>
        <div class="contain-background-bottom"><svg xmlns="http://www.w3.org/2000/svg" class="background-bottom" width="895" height="320"><path fill="#5C6779" fill-rule="evenodd" d="M100 0h795v320H0V100C0 44.772 44.772 0 100 0z" opacity=".077"/></svg></div>
        <div class="enjoyable">
            <div class="image-enjoyable"></div>
            <div class="text-enjoyable">
              <div class="decoration-text">
                <div class="circle"></div>
                <div class="line"></div>
              </div>
              <h2>Enjoyable place for all the family</h2>
              <p class="text-1">Our relaxed surroundings make dining with us a great experience for everyone. We can even arrange a tour of the farm before your meal.</p>
            </div>
        </div>
        <div class="locally">
            <div class="image-locally">
              <svg xmlns="http://www.w3.org/2000/svg" width="160" height="76"><g fill="#9E7F66" fill-rule="evenodd"><path d="M0 70h160v6H0zM0 56h160v6H0zM0 42h160v6H0zM0 28h160v6H0zM0 14h160v6H0zM0 0h160v6H0z"/></g></svg>
            </div>
            <div class="text-locally">
              <div class="decoration-text">
                <div class="circle"></div>
                <div class="line"></div>
              </div>
              <h2>The most locally sourced food</h2>
              <p class="text-1">All our ingredients come directly from our farm or local fishery. So you can be sure that you’re eating the freshest, most sustainable food.</p>
            </div>
        </div>
      </section>
</template>


<style lang="scss" scoped>
  @import './public/sass/colors.scss';

  main {
    .enjoyable-locally {
      width: 100%;
      height: 1411px;
      position: relative;
      .background-top {
        position: absolute;
        top: 250px;
        left: 0;
      }
      .contain-background-bottom {
        position: absolute;
        bottom: 0;
        right: 0;
      }
      .enjoyable {
        padding-top: 46px;
         .image-enjoyable {
          background-image: url("/images/homepage/enjoyable-place-desktop@2x.jpg");
          margin-bottom: 60px;   
        }
      }
      .locally {
        flex-direction: row-reverse;
        padding-top: 257px;
        .image-locally {
          background-image: url("/images/homepage/locally-sourced-desktop@2x.jpg");
          position: relative;
          svg {
            position: absolute;
            top: 293px;
            right: -114px;
          }
        }
      }
      .enjoyable, .locally {
        width: 1118px;
        height: 540px;
        display: flex;
        justify-content: space-between;
        align-items: center;
        margin: auto;
        .image-enjoyable, .image-locally {
          width: 540px;
          height: 720px;
          background-size: contain;
          background-repeat: no-repeat;
          z-index: 10;
          box-shadow: 5px 28px 44px rgba($color: $ombres, $alpha: 0.5);
        }
        .text-enjoyable, .text-locally {
          width: 445px;
          height: 273px;
          h2 {
            width: 399px;
            height: 112px;
            margin-top: 48px;
            margin-bottom: 16px;
          }
          p {
            height: 90px;
            margin: 0;
          }
        }
      }
    }
    .highlights {
      width: 100%;
      height: 761px;
      background-color: $primaryBackground;
    }
  }

  @media screen and (max-width: 1350px) {
    main {
      .enjoyable-locally {
        height: 1490px;
        display: flex;
        flex-direction: column;
        .background-top {
          left: -517px;
          top: 200px;
        }
        .contain-background-bottom {
          width: 384px;
          height: 320px;
          overflow: hidden;
        }
        .contain-background-bottom .background-bottom {
          right: -511px;
        }
        .enjoyable, .locally {
          width: 573px;
          height: 673px;
          flex-direction: column;
          position: absolute;
          padding-top: 0;
          left: 0;
          right: 0;
          .image-enjoyable, .image-locally {
            width: 573px;
            height: 360px;
          }
          .text-enjoyable , .text-locally {
            width: 457px;
            height: 257px;
            flex-direction: column;
            align-items: center;
            .decoration-text {
              margin: auto;
            }
            h2 {
              width: 410px;
              height: 112px;
              margin: 32px auto 16px auto;
            }
            h2, p {
              text-align: center;
            }
          }
        }
        .enjoyable {
          margin: auto;
          top: -44px;
          .image-enjoyable {
            background-image: url("/images/homepage/enjoyable-place-tablet@2x.jpg");
            margin-bottom: 0;
          }
        }
        .locally {
          bottom: 113px;
          .image-locally {
            background-image: url("/images/homepage/locally-sourced-tablet@2x.jpg");
            svg {
               top: 228px;
               right: -58px;      
            }
          }
        }
      }
    }
  }

@media screen and (max-width: 768px) {
  main {
    .enjoyable-locally {
      .background-top {
          top: 100px;
        }
      .enjoyable {
        top: -97px;
      }
      .locally {
        bottom: 120px;
      }
    }
  }
}

 @media screen and (max-width: 600px) {
  main {
    .enjoyable-locally {
      .background-top, .contain-background-bottom {
        display: none;
      }

      .enjoyable, .locally {
        width: 327px;
        height: 683px;
        .image-enjoyable,.image-locally {
          width: 327px;
          height: 400px;
        }
        .text-enjoyable, .text-locally {
          width: 327px;
          height: 235px;
          h2 {
            width: 327px;
            height: 80px;
            font-size: 32px!important;
            line-height: 40px!important;
          }
          p {
            width: 327px;
            height: 100px;
            font-size: 15px!important;
          }
        }
      }

      .enjoyable {
        top: -60px;
        .image-enjoyable {
          background-image: url("/images/homepage/enjoyable-place-mobile@2x.jpg");
        }
      }

      .locally {
        .image-locally {
          background-image: url("/images/homepage/locally-sourced-mobile@2x.jpg");
          svg {
            display: none;
          }
        }
      }
    }
  }
 }

</style>