<template>
    <div class="article">
        <div class="image-article"></div>
        <div class="text-article">
            <div class="decoration-text">
            <div class="circle"></div>
            <div class="line"></div>
            </div>
            <h2>{{ title }}</h2>
            <p class="text-1">{{ text }}</p>
        </div>
    </div>
</template>

<style lang="scss" scoped>
  @import './public/sass/colors.scss';

    .article {
        width: 1118px;
        height: 540px;
        display: flex;
        justify-content: space-between;
        align-items: center;
        margin: auto;
        .image-article {
            width: 540px;
            height: 720px;
            background-size: contain;
            background-repeat: no-repeat;
        }
        .text-article {
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

    @media screen and (max-width: 1200px) {
        .article {
          width: 573px;
          height: 673px;
          flex-direction: column;
          position: absolute;
          padding-top: 0;
          left: 0;
          right: 0;
          .image-article {
            width: 573px;
            height: 360px;
          }
          .text-article {
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
    }

</style>