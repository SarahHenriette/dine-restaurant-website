<template>
    <section class="highlights">
        <div class="text-highlights">
            <div class="decoration-text">
            <div class="circle"></div>
            <div class="line"></div>
            </div>
            <h2>A few highlights from our menu</h2>
            <p class="text-1">We cater for all dietary requirements, but here’s a glimpse at some of our diner’s favourites. Our menu is revamped every season.</p>
        </div>
        <div class="articles-highlights">
            <div class="article">
            <div class="image-article salmon"><div class="line"></div></div>
            <div class="text-article">
                <h3>Seared Salmon Fillet</h3>
                <p class="text-2">Our locally sourced salmon served with a refreshing buckwheat summer salad.</p>
            </div>
            </div>
            <div class="line-articles-highlights"></div>
            <div class="article">
            <div class="image-article beef"><div class="line"></div></div>
            <div class="text-article">
                <h3>Seared Salmon Fillet</h3>
                <p class="text-2">Our locally sourced salmon served with a refreshing buckwheat summer salad.</p>
            </div>
            </div>
            <div class="line-articles-highlights"></div>
            <div class="article">
            <div class="image-article chocolate"><div class="line"></div></div>
            <div class="text-article">
                <h3>Seared Salmon Fillet</h3>
                <p class="text-2">Our locally sourced salmon served with a refreshing buckwheat summer salad.</p>
            </div>
            </div>
        </div>
    </section>
</template>

<style lang="scss" scoped>
  @import './public/sass/colors.scss';

.highlights {
  width: 100%;
  height: 761px;
  background-color: $primaryBackground;
  display: flex;
  position: relative;
  .text-highlights, .articles-highlights {
    position: absolute;
    top: 200px;
  }
  .text-highlights {
    width: 445px;
    height: 273px;
    left: 165px;
    h2, p {
      color: $white;
    }
    h2 {
      width: 100%;
      height: 112px;
      margin-top: 48px;
      margin-bottom: 16px;
    }
    p {
      width: 100%;
      height: 90px;
    }
  }
  .articles-highlights {
    width: 540px;
    height: 393px;
    display: flex;
    flex-direction: column;
    right: 165px;
    top: 255px;
    .line-articles-highlights {
      width: 540px;
      height: 1px;
      background-color: $primary;
      margin: 24px 0;
    }
    .article {
      width: 540px;
      height: 96px;
      display: flex;
      justify-content: space-between;
      .image-article {
        width: 160px;
        height: 96px;
        position: relative;
        background-size: contain;
        background-repeat: no-repeat;
        .line {
          width: 32px;
          height: 1px;
          background-color: $primary;
          position: absolute;
          top: 20px;
          right: 0;
        }
      }
      .salmon {
        background-image: url("/images/homepage/salmon-desktop-tablet@2x.jpg");
      }
      .beef {
        background-image: url("/images/homepage/beef-desktop-tablet@2x.jpg");
      }
      .chocolate {
        background-image: url("/images/homepage/chocolate-desktop-tablet@2x.jpg");
      }
      .text-article {
        width: 350px;
        height: 88px;
        h3, p {
          margin: 0;
          color: $white;
        }
      }
    }
  }
}

@media screen and (max-width: 1350px) {
  .highlights {
    height: 891px;
    .text-highlights, .articles-highlights {
      left: 0;
      right: 0;
      margin: auto;
    }
    .text-highlights {
      height: 257px;
      top: 96px;
      h2, p {
        text-align: center;
      }
      h2 {
        margin-top: 32px;
      }
      .decoration-text {
        margin: auto;
      }
    }
    .articles-highlights {
      width: 573px;
      height: 386px;
      bottom: 96px;
      top: auto;
    }
  }
}

@media screen and (max-width: 600px) {
  .highlights {
    height: 1720px;
    .text-highlights {
      width: 327px;
      height: 235px;
      top: 72px;
      h2 {
        font-size: 32px!important;
      }
    }
    .articles-highlights {
      flex-direction: column;
      width: 327px;
      height: 1211px;
      bottom: 72px;
      .line-articles-highlights {
        width: 327px;
        margin-top: 0;
        margin-bottom: 24px;
      }
      .article {
        width: 327px;
        height: 393px;
        flex-direction: column;
        .image-article {
          width: 327px;
          height: 245px;
        }
        .salmon {
          background-image: url("/images/homepage/salmon-mobile@2x.jpg");
        }
        .beef {
          background-image: url("/images/homepage/beef-mobile@2x.jpg");
        }
        .chocolate {
          background-image: url("/images/homepage/chocolate-mobile@2x.jpg");
        }
        .text-article {
          width: 327px;
          height: 116px;
          h3, p {
            text-align: center;
          }
        }
      }
    }
  }
}
</style>