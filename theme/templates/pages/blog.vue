<template>
    <div>
      <div class="content1">
        <div class="blogHeading">
          <p>Our Blog</p>
        </div>
        <div class="searchBar"></div>
      </div>
      <div class="content2">
        <div class="section1">
          <img :src="context.blogs[0].feature_image.secure_url" />
          <div class="section1-text">
            <div class="section1-text-block"><p>Apparel Supplychain</p></div>
            <p>{{ context.blogs[0].title }}</p>
          </div>
        </div>
        <div class="section2">
          <div class="subSection1">
            <img :src="context.blogs[1].feature_image.secure_url" />
            <div class="section2-text"><p>{{ context.blogs[1].title }}</p></div>
          </div>
          <div class="subSection2">
            <img :src="context.blogs[2].feature_image.secure_url" />
            <div class="section2-text2"><p>{{ context.blogs[2].title }}</p></div>
          </div>
        </div>
      </div>
      <div class="content3"> 
        <div class="column" v-for="(items, i) in this.data" :key="i">
          <img :src="data[i].feature_image.secure_url" />
          <div class="sub-col-title"><p>{{ data[i].title}}</p></div>                       
        </div>
      </div>
    </div>
</template>

<style lang="less" scoped>
.content1 {
  display: flex;
  .blogHeading {
    padding-left: 72px;
    width: 126px;
    height: 36px;
    font-family: Marcellus;
    font-weight: 400;
    font-size: 32px;
    line-height: 36px;
    @media screen and (max-width: 768px) {
      padding-left: 32px;
      font-size: 28px;
      line-height: 32px;
      width: 110px;
      height: 32px;
    }
    @media screen and (max-width: 480px) {
      width: 120px;
    }
  }
}
.content2 {
  display: flex;
  padding-top: 60px;
  padding-left: 72px;
  .section1 {
    img {
      width: 689px;
      height: 689px;
      @media screen and (max-width: 768px) {
        width: 378px;
        height: 378px;
      }
      @media screen and (max-width: 480px) {
        width: 288px;
        height: 162px;
      }
    }
    .section1-text {
      width: 689px;
      height: 100px;
      background-color: #e8d7c6;
      font-family: Marcellus;
      font-weight: 400;
      font-size: 24px;
      line-height: 28px;
      p {
        padding-top: 28px;
        padding-bottom: 16px;
        padding-left: 16px;
        padding-right: 16px;
        @media screen and (max-width: 768px) {
          padding-top: 8px;
        }
      }
      .section1-text-block {
        width: 155px;
        height: 35px;
        background-color: #9e856c;
        font-family: Inter;
        font-weight: 400;
        font-size: 14px;
        line-height: 20px;
        p {
          padding-top: 8px;
          padding-bottom: 8px;
          padding-left: 12px;
          padding-right: 12px;
        }
        @media screen and (max-width: 768px) {
          width: 136px;
          p {
            font-size: 12px;
          }
        }
        @media screen and (max-width: 480px) {
          p {
            font-size: 12px;
          }
        }
      }
      @media screen and (max-width: 768px) {
        width: 378px;
        height: 75px;
        p {
          font-size: 20px;
          line-height: 24px;
        }
      }
      @media screen and (max-width: 480px) {
        width: 288px;
        height: 70px;
        p {
          font-size: 20px;
          line-height: 24px;
        }
      }
    }
  }
  .section2 {
    padding-left: 40px;
    .subSection1 {
      img {
        width: 567px; 
        height: 323px;
        @media screen and (max-width: 768px) {
          width: 274px; 
          height: 154px;
        }
        @media screen and (max-width: 480px) {
          width: 288px;
          height: 162px;
        }
      }
      .section2-text {
        width: 567px;
        height: 58px;
        background-color: #e8d7c6;
        font-family: Marcellus;
        font-weight: 400;
        font-size: 24px;
        line-height: 28px;
        p {
          padding-top: 16px;
          padding-bottom: 24px;
          padding-left: 16px;
          padding-right: 16px;
        }
        @media screen and (max-width: 768px)  {
          width: 274px;
          height: 70px;
          p {
            font-size: 20px;
            line-height: 24px;
          }
        }
        @media screen and (max-width: 480px) {
          width: 288px;
          height: 60px;
          p {
            font-size: 20px;
            line-height: 24px;
          }
        }
      }
    }
    .subSection2 {
      padding-top: 25px;
      img {
        width: 567px; 
        height: 323px;
        @media screen and (max-width: 768px) {
          width: 274px; 
          height: 154px;
        }
        @media screen and (max-width: 480px) {
          width: 288px;
          height: 162px;
        }
      }
      .section2-text2 {
        width: 567px;
        height: 58px;
        background-color: #e8d7c6;
        font-family: Marcellus;
        font-weight: 400;
        font-size: 24px;
        line-height: 28px;
        p {
          padding-top: 16px;
          padding-bottom: 24px;
          padding-left: 16px;
          padding-right: 16px;
        }
        @media screen and (max-width: 768px)  {
          width: 274px;
          height: 70px;
          p {
            font-size: 20px;
            line-height: 24px;
          }
        }
        @media screen and (max-width: 480px) {
          width: 288px;
          height: 60px;
          p {
            font-size: 20px;
            line-height: 24px;
          }
        }
      }
    }
    @media screen and (max-width: 768px) {
      padding-left: 28px;
    }
    @media screen and (max-width: 480px) {
      padding-left: 0px;
      padding-top: 32px;
    }
  }
  @media screen and (max-width: 768px) {
    padding-left: 32px;
  }
  @media screen and (max-width: 480px) {
    padding-top: 32px;
    flex-direction: column;
  }
}
.content3 {
  padding-top: 32px;
  padding-left: 72px;
  display: grid;
  grid-template-columns: auto auto auto;
  width: fit-content;
  gap: 30px;
  .column {
    img {
      width: 410px; 
      height: 230px;
      @media screen and (max-width: 768px) {
        width: 212px; 
        height: 119px;
      }
      @media screen and (max-width: 768px) {
        width: 136px; 
        height: 76px;
      }
    }
    .sub-col-title {
      font-family: 'Marcellus';
      font-weight: 400;
      font-size: 24px;
      line-height: 28px;
      width: 410px;
      height: 56px;
      padding-top: 20px;
      @media screen and (max-width: 768px) {
        width: 212px;
        height: 45px;
        font-size: 20px;
        line-height: 24px;
      }
      @media screen and (max-width: 480px) {
        padding-left: 16px;
        width: 139px;
        height: 50px;
        font-size: 20px;
        line-height: 24px;
        margin-top: -23px
      }
    }
    @media screen and (max-width: 480px) {
      display: flex;
      padding-top: 32px;
    }
  }
  @media screen and (max-width: 768px) {
    padding-left: 32px;
    gap: 20px
  }
  @media screen and (max-width: 480px) {
    display: flex;
    flex-direction: column;
    // padding-top: 32px;
  }
}
</style>

<script>
export default  {
    props:["context"],
    data() {
      return {
        data: []
      }
    },
    watch: {
    context: function() {
      for(let i = 3; i < this.context.blogs.length; i++) {
        this.data.push(this.context.blogs[i]);
      }
      console.log("Blogs Data", this.context.blogs);
    }
  } 
}
</script>


