<template>
  <div class="mainSection">
    <div class="content1">
      <div class="blogHeading">
        <p>Our Blog</p>
      </div>
      <div class="blogDesc">
        <p>He rejects pleasures to secure other greater pleasures, or else he endures pains to avoid worse pains.</p>
      </div>
    </div>
    <div class="content2">
      <fdk-link :link= "`/blog/${context.blogs[0].slug}`" :title="context.blogs[0].title">
        <div class="section1">  
          <div class="photo">
            <img :src="context.blogs[0].feature_image.secure_url" />
          </div>
          <div class="section1-text">
            <div class="section1-text-block"><p>Apparel Supplychain</p></div>
            <p>{{ context.blogs[0].title }}</p>
          </div>
        </div>
      </fdk-link>
      <div class="section2">
        <fdk-link :link= "`/blog/${context.blogs[1].slug}`" :title="context.blogs[1].title">
          <div class="subSection1">
            <div class="photo">
              <img :src="context.blogs[1].feature_image.secure_url" />
            </div>
            <div class="section2-text"><p>{{ context.blogs[1].title }}</p></div>
          </div>
        </fdk-link>
        <fdk-link :link= "`/blog/${context.blogs[2].slug}`" :title="context.blogs[2].title">
          <div class="subSection2">
            <div class="photo">
              <img :src="context.blogs[2].feature_image.secure_url" />
            </div>
            <div class="section2-text2"><p>{{ context.blogs[2].title }}</p></div>
          </div>
        </fdk-link>
      </div>
    </div>
    <div class="content3">
      <div v-for="(items, i) in context.blogs.slice(3)" :key="i">
        <fdk-link :link= "`/blog/${data[i].slug}`" :title="data[i].title">
          <div class="column">
            <div class="photo">
              <img :src="data[i].feature_image.secure_url" />
            </div>
            <div class="sub-col-title"><p>{{ data[i].title}}</p></div>
          </div> 
        </fdk-link>
      </div>
    </div>
    <div class="whites100"></div>
  </div>
</template>

<settings>
{
  "props": [
    {
      "type": "text",
      "id": "textH",
      "default": "",
      "label": "Heading"
    },
    {
      "type": "textarea",
      "id": "textD",
      "default": "",
      "label": "Subheading"
    }
  ]
}
</settings>

<style lang="less" scoped>
.content1 {
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
  .blogDesc { 
    padding-left: 72px;
    padding-top: 8px;
    font-family: Inter;
    font-weight: 400;
    font-size: 16px;
    line-height: 20px;
    width: 1296px;
    height: 22px;
    @media screen and (max-width: 768px){
      padding-left: 32px;
      font-size: 14px;
      line-height: 22px;
      width: 680px;
      height: 20px;
    }
    @media screen and (max-width: 480px) {
      font-size: 14px;
      line-height: 20px;
      width: 288px;
      height: 40px;
    }
  }
}
.content2 {
  display: flex;
  padding-top: 60px;
  padding-left: 72px;
  .section1 {
   .photo {
    width: 689px;
    height: 689px;
    overflow: hidden;
    img {
      width: 689px;
      height: 689px;
      transition: transform 0.35s;
      @media screen and (max-width: 768px) {
        width: 378px;
        height: 378px;
      }
      @media screen and (max-width: 480px) {
        width: 288px;
        height: 162px;
      }
    }
    @media screen and (max-width: 768px) {
      width: 378px;
      height: 378px;
    }
    @media screen and (max-width: 480px) {
      width: 288px;
      height: 162px;
    }
   }
   .photo:hover img {
    transform: scale(1.1);
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
        height: 99px;
        p {
          font-size: 20px;
          line-height: 24px;
        }
      }
      @media screen and (max-width: 480px) {
        width: 288px;
        height: 95px;
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
      .photo {
        overflow: hidden;
        width: 567px; 
        height: 323px;
         img {
          transition: transform 0.35s;
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
        @media screen and (max-width: 768px) {
          width: 274px; 
          height: 154px;
        }
        @media screen and (max-width: 480px) {
          width: 288px;
          height: 162px;
        }
      }
      .photo:hover img {
        transform: scale(1.1);
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
      .photo {
        overflow: hidden;
        width: 567px; 
        height: 323px;
        img {
          transition: transform 0.35s;
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
        @media screen and (max-width: 768px) {
          width: 274px; 
          height: 154px;
        }
        @media screen and (max-width: 480px) {
          width: 288px;
          height: 162px;
        }
      }
      .photo:hover img {
        transform: scale(1.1);
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
    .photo {
      overflow: hidden;
      width: 410px; 
      height: 230px;
      img {
        transition: transform 0.35s;
        width: 410px; 
        height: 230px;
        @media screen and (max-width: 768px) {
          width: 212px; 
          height: 119px;
        }
        @media screen and (max-width: 480px) {
          width: 136px; 
          height: 76px;
        }
      }
      @media screen and (max-width: 768px) {
        width: 212px; 
        height: 119px;
      }
      @media screen and (max-width: 480px) {
        width: 136px; 
        height: 76px;
      }
    }
    .photo:hover img {
      transform: scale(1.1);
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
    // gap: 0px;
    padding-top: 0px;
  }
}
.mainSection {
    position: relative;
}
.whites100{
  position: absolute;
  top:0px;
  left:0px;
  width: 100%;
  height: 100%;
  background-color: white;
  animation-name: example100;
  animation-duration: 1.5s;
  animation-direction:reverse;
  animation-fill-mode: forwards;
}
@keyframes example100 {
  0%   {height:0%;}
  100% {height:100%;}
}
</style>

<script>
export default  {
    props:["context", "settings","page_config"],
    data() {
      return {
        data: [],
        items: []
      }
    },
    methods: {
    fetchData() {
        this.$apiSDK.content.getBlogs({pageNo : 1 ,pageSize : 10}).then((data) => {
          console.log("dataaaaaaaaaaaa", data);
        this.items = data.items;
        console.log("Items+++++++++++", this.items);
      });
    }
  },
    watch: {
    context: function() {
      for(let i = 3; i < this.context.blogs.length; i++) {
        this.data.push(this.context.blogs[i]);
      }
      console.log("Blogs Data", this.context);
    }
    // page_config: function() {
    //   console.log("Setting Data from watch", this.page_config);
    // }
  },
  mounted() {
    this.fetchData();
    console.log("Setting Data from mounted", this.page_config);
  }
}
</script>


