<template>
  <main>

  <!-- ここからhero -->
  <div class="hero" id="hero" :class="{'hidden': isActive}">
    <div class="main-hero">
      <div class="hero-image">
        <img src="../assets/images/freely.png" alt="">
      </div>
      <div class="hero-second-sentence">
        <p class="be-engineer">Be a backendengineer</p>
      </div>
    </div>
    <!-- スクロールオブジェクト -->

    <div class="scroll">
      <div class="harf-circle">
        <div class="flex-circle">
          <img src="../assets/images/Line 10.png" alt="">
          <p>Scroll to</p>
        </div>
      </div>
    </div>
    <!-- スクロール時に隠すやつ -->
    <div class="hidden-scroll">
      <div class="hidden-harf-circle" :style="rotateStyle">
      </div>
    </div>
    <!-- 下半分隠すやつ -->
    <div class="circle-hidden"></div>
    
  </div>

  <!-- ここからwhy -->
  <div class="why" id="why">
    <div class="why-sentence">
      <h3>そもそもなぜエンジニアなのか</h3>
      <p>お金が稼げそう</p>
      <p>かっこいい</p>
      <p>おもしろい</p>
      <p>知らない世界</p>
    </div>
  </div>

  <!-- ここからlife-plan -->
  <div class="life-plan">
    <h2>人生でやりたいこと</h2>
    <div class="life-plan-flex">
      <div class="life-plan-box">
        <div class="life-plan-number">
          <span class="number-color"><p>1</p></span>
        </div>
        <span class="box-header"><p>自由に働く</p></span>
        <p>エンジニアの場所にとらわれない働き方にあこがれた</p>
      </div>
      <div class="life-plan-box">
        <div class="life-plan-number">
          <span class="number-color"><p>2</p></span>
        </div>
        <span class="box-header"><p>専門性く</p></span>
        <p>手に職を付けられる仕事がしたい</p>
      </div>
      <div class="life-plan-box last-child">
        <div class="life-plan-number">
          <span class="number-color"><p>3</p></span>
        </div>
        <span class="box-header"><p>自慢したい</p></span>
        <p>誰かに使ってもらえるものを作りたい</p>
      </div>
    </div>
  </div>
  <!-- ここに水平スクロール -->
  <div class="carousel">

    <h2>様々な職種</h2>
    <div class="carousel-box">
      <hooper :itemsToShow="1.8" :centerMode="true" :pagination="true" :infiniteScroll="true" :autoPlay="true" :playSpeed="4000">
        <!-- 各スライド -->
        <slide>
            <img src="../assets/images/frontend.png" alt="">
            <h3>フロントエンドエンジニア</h3>
            <p class="carousel-sentence">主にWEBページのユーザーの目に触れる部分を扱う</p>
        </slide>
        <slide>
            <img src="../assets/images/backend.png" alt="">
            <h3>バックエンドエンジニア</h3>
            <p class="carousel-sentence">主にユーザーからは見えない裏側の処理を担当する</p>
        </slide>
        <slide>
            <img src="../assets/images/designer.png" alt="">
            <h3>デザイナー</h3>
            <p class="carousel-sentence">主にWebサイトや広告のデザインを行う</p>
        </slide>
        <slide>
            <img src="../assets/images/infra.png" alt="">
            <h3>インフラエンジニア</h3>
            <p class="carousel-sentence">データベースや環境構築などインフラ領域を扱う</p>
        </slide>
        <navigation slot="hooper-addons"></navigation>
      </hooper>
    </div>
  </div>
  <!-- backend -->
  <div class="backend">
    <h2>バックエンドエンジニアとは</h2>
    <div class="backend-box">
      <span class="box-header"><p>Resion</p></span>
      <div class="box-content">
        
        <div class="box-flex">
          <div>
            <div class="box-sentence">
              <p>ユーザーからは見えない部分を補う</p>
            </div>
            <p>データベース</p>
            <p>インフラ</p>
            <p>システム戦略</p>
            <p>環境構築等</p>
          </div>
          <div>
            <img src="../assets/images/undraw_server_cluster_jwwq 1.png" alt="" class="box-image">
          </div>
        </div>
      </div>
    
    </div>

    <div class="backend-box">
      <span class="box-header"><p>Tech</p></span>
      <div class="box-content">
        
        <div class="box-flex">
          <div>
          <div class="box-sentence">
          <p>ユーザーからは見えない部分を補う</p>
        </div>
            <p>データベース</p>
            <p>インフラ</p>
            <p>システム戦略</p>
            <p>環境構築等</p>
          </div>
          <div>
            <img src="../assets/images/undraw_maintenance_re_59vn 2.png" alt="" class="box-image">
          </div>
        </div>
      </div>
    
    </div>

    <div class="backend-box">
      <span class="box-header"><p>License</p></span>
      <div class="box-content">
        <div class="box-flex">
          <div>
            <div class="box-sentence">
              <p>ユーザーからは見えない部分を補う</p>
            </div>
            <p>データベース</p>
            <p>インフラ</p>
            <p>システム戦略</p>
            <p>環境構築等</p>
          </div>
          <div>
            <img src="../assets/images/undraw_certification_re_ifll 1.png" alt="" class="box-image">
          </div>
        </div>
      </div>
    
    </div>
  </div>
  <div class="chart">
  <h2>年収比較</h2>
    <chart :styles='chartScale' />
  </div>
  <!-- footer -->

</main>
</template>

<script>
import { Hooper, Slide,Navigation } from 'hooper';
import 'hooper/dist/hooper.css';
import chart from '../components/Chart.vue';

export default {
  name: 'IndexPage',
  layout: 'default',
  components: {
    Hooper,
    Slide,
    Navigation,
    chart,
  },
  data() {
    return {
      height: 100,
      width: 100,
      isActive: false,
      hero: 0,
      why: 0,
      deg: 180
    }
  },
  computed: {
    chartScale() {
      return {
        height: `${this.height}%`,
        width: `${this.width}%`,
      }
    },
    rotateStyle() {
      return {
        transform: `rotate(${this.deg}deg)`
      }
    }
  },
  methods: {
      heroSticky() {
       const hidden = document.querySelectorAll('hidden')
       function clientsRect (target) {
         return target.getBoundingClientRect().top + window.pageYOffset;
       }
         if(this.hero <  window.pageYOffset)
         {
          this.isActive = true
         } else {
           this.isActive = false
         }
     },

     circleRotate() {
      const height = window.innerHeight;
      let rotatePercentage = window.pageYOffset/height
      this.deg = rotatePercentage * 180 + 180
      console.log(this.deg)
     }
  },
  mounted() {
    this.$nextTick(() => {
      window.addEventListener("scroll", this.heroSticky)
      this.hero = document.getElementById('hero').clientHeight;
    }),
    this.$nextTick(() => {
      window.addEventListener("scroll", this.circleRotate)
    })
  }
};
</script>

<style lang="sass" scoped>
@use "@/assets/sass/common" as cmn
html, body 
  margin: 0
  font-family: sans-serif
  overflow-x: hidden

h1 
  font-size:   32px

.hero 
  margin-top: 14vh
  height: 100vh
  width: 100%
  position: sticky
  top: 14vh
  left: 0
  background-color: #fff
  z-index: 30
  opacity: 100
  transition: .5s

/* 要素の切り替えのためのクラス */
.hidden 
  visibility: hidden
  z-index: -99
  opacity: 0
  transition: .5s

.hero-image img
  display: block
  visibility: visible
  margin: 0 auto
  width: 72vh


.hero-second-sentence 
  position: relative
  margin-top: -100px
  padding-top: 70px
  height: 21vh
  z-index: 0
  p
    display: block
    margin: 50px auto 30px auto
    color: cmn.$primary-900
    font-weight: 600
.hero-second-sentence:before 
  display: block
  position: absolute
  top: 0
  left: 0
  background: inherit
  content: ''
  width: 100%
  height: 21vh
  background: linear-gradient(180deg, rgba(127,203,247,0) 0%, rgba(127,203,247,0.2) 100%)
  -webkit-filter: blur(10px)
  -moz-filter: blur(10px)
  -ms-filter: blur(10px)
  filter: blur(10px)
  top: -5px
  left: -5px
  right: -5px
  bottom: -5px
  z-index: -1



.be-engineer 
  display: block
  width: 410px
  font-size: 32px
  color: cmn.$primary-900
  letter-spacing: 0.05em
  font-weight: bold
  margin: 80px auto 0 auto
  position: relative

.scroll 
  margin-top: 50px

.harf-circle 
  margin: 0 auto
  width: 214px
  height: 107px
  border: solid 3px 
  border-color: cmn.$natural-400
  border-radius: 107px 107px 0 0
  border-bottom: 0


.flex-circle 
  display: flex
  height: 69px
  width: 80px
  margin: 35px auto 0 100px
  img 
    animation: wobbling_y 1.2s ease-in-out infinite alternate

.harf-circle p 
  display: flex
  transform: rotate(90deg)
  color: cmn.$natural-400
  font-size: 16px
  margin: 0 0 5px 0
  align-items: end

/* スクロールサークル隠れている方 */
.hidden-scroll
  margin: -107px
.hidden-harf-circle 
  transform-origin: 50% 100%
  margin: 0 auto
  width: 214px
  height: 107px
  border: solid 3px 
  border-color: cmn.$secondary-400
  border-radius: 107px 107px 0 0
  border-bottom: 0
  z-index: 20

.circle-hidden
  background-color: #ffffff
  width: 214px
  height: 107px
  margin: 107px auto 0 auto
  z-index: 30
  position: relative

/* why */
.why 
  width: 100%
.why-sentence
  width: 242px
  margin: 0 auto

.why-sentence p
  text-align: center
  margin: 8px 0
  
h3
  font-size: 16px
  display: block
  text-align: center
  color: cmn.$primary-600
  margin-bottom: 30px


/* life-plan */
.life-plan
  width: 100%
  margin-top: 200px

h2 
  text-align: center
  margin-bottom: 54px
  color: cmn.$natural-800

.life-plan-flex
  margin: 0 auto
  width: 72vw
  display: flex
  justify-content: space-between
  
.life-plan-box
  margin-right: 4vw
  width: 300px
  height: 181px
  border: 1px solid cmn.$natural-300
  border-radius: 10px
  padding: 0 50px 30px 50px
  p 
    text-align: center

  .number-color p
    display: block
    margin: -24px auto 16px auto
    padding-top: 12px
    width: 48px
    height: 48px
    border-radius: 48px
    background-color: cmn.$primary-200
    color: primary-800
    text-align: center
  .box-header p
    margin-bottom: 10px
    text-align: center
    color: cmn.$primary-800
.last-child
  margin-right: 0

/* 水平スクロール */
.carousel
  width: 100%
  margin-top: 200px

.carousel-box
  height: 633px

.hooper
  height: 100%

.hooper-slide
  img
    margin: 90px auto 0 auto
    width: 960px
    height: 543px
    opacity: .3
    border-radius: 10px
  h3  
    margin: 20px auto 0 auto
    width: 960px
    text-align: left
  .carousel-sentence
    display: none
    width: 960px
    margin: 15px auto 0 auto

.hooper-track
  ::v-deep .hooper-track
    transition: cubic-bezier(.85,.01,.15,1)

/* 前に戻るボタン */
::v-deep .hooper-prev
  left: 21%
  height: 40px
  width: 40px
  background: url(~assets/images/polygon_prev.png) no-repeat center center
  background-size: 100%
  border: none
  transform: scale(1.3)
  transition-property: all
  transition-duration: 0.4s
  transition-timing-function: cubic-bezier(0.23, 1, 0.58, 1)
  transition-delay: 0s
  &:hover
    transform: scale(0.6)
    transition-property: all
    transition-duration: 0.4s
    transition-timing-function: cubic-bezier(0.23, 1, 0.58, 1)
    transition-delay: 0s
  .icon
    display: none
 


/* 次へ行くボタン */
::v-deep .hooper-next
  right: 21%
  height: 40px
  width: 40px
  background: url(~assets/images/polygon_next.png) no-repeat center center
  background-size: 100%
  border: none
  transform: scale(1.3)
  transition-property: all
  transition-duration: 0.4s
  transition-timing-function: cubic-bezier(0.23, 1, 0.58, 1)
  transition-delay: 0s
  &:hover
    transform: scale(0.6)
    transition-property: all
    transition-duration: 0.4s
    transition-timing-function: cubic-bezier(0.23, 1, 0.58, 1)
    transition-delay: 0s
  .icon
    display: none

/* 中央のスライド */
.is-current
  img
    margin: 0 auto
    opacity: 1.0
  .carousel-sentence
    display: block

.works-card
  margin: 0
  height: auto
  opacity: .3
  transform: scale(.8)
  transition: opacity .5s, transform .5s

.slick-center img 
  opacity: 1 // 中央のスライドは透過しない
  transform: scale(1) // 中央のスライドは小さくしない

/* backend */
.backend
  width: 100%
  margin-top: 200px

.backend-box
  width: 72vw
  margin: 30px auto 40px auto
  .box-header p
    font-size: 64px
    font-weight: bold
    text-shadow: 0 4px 4px rgba(0,0,0,0.25)
  .box-content
    margin-top: -32px
    width: 63vw
    margin-left: 8.7vw
    padding: 34px 5px 10px 58px
    background-color: cmn.$primary-100
  .box-sentence
    margin-bottom: 20px
    p
      color: cmn.$primary-800
  .box-flex
    display: flex
    justify-content: space-between
    .box-image
      height: 200px
      margin-top: -60px

/* chart */
.chart
  margin: 150px auto
  width: 72vw


</style>
