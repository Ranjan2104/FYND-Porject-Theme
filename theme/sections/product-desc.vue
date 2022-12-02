<template>
  <section :class='["media-with-text" ,"full-width-section", "align-" + settings.props.align.value, "style-" + settings.props.styleV.value]' >
    <div :class='["image-section"]'>
      <img :src="settings.props.image.value" />
    </div>
    <div  :class='["media-with-text__content"]'>
      <div class="media-with-text__content--main">
        {{ settings.props.text.value }}
      </div>
      <div class="media-with-text__content--sub">
        {{ settings.props.heading.value }}
      </div>
    </div>
  </section>
</template>
<!-- #region  -->

<settings>
{
  "name": "product-description",
  "label": "Product Description",
  "props": [
    {
      "type": "image_picker",
      "id": "image",
      "default": "",
      "label": "Image"
    },
    {
      "type": "select",
      "id": "styleV",
      "options": [
          {
              "value": "left",
              "text": "Style 1"
          },
          {
              "value": "right",
              "text": "Style 2"
          }
      ],
      "default": "left",
      "label": "Layout"
    },
    {
      "type": "select",
      "id": "align",
      "options": [
          {
              "value": "left",
              "text": "ON"
          },
          {
              "value": "right",
              "text": "OFF"
          }
      ],
      "default": "right",
      "label": "Mirror layout"
    },
    {
      "type": "text",
      "id": "text",
      "default": "",
      "label": "Heading"
    },
    {
      "type": "textarea",
      "id": "heading",
      "default": "",
      "label": "Description"
    }
  ]
}
</settings>
<!-- #endregion -->
<style lang="less" scoped>

.media-with-text {
  display: flex;
  align-items: center;
  justify-content: space-around;
  font-size: 16px;
  font-weight: 300;
  padding-left: 40px;
  padding-right: 40px;
  box-sizing: border-box;
  @media @large-1280 {
    padding-left: 0px;
    padding-right: 0px;
    flex-direction: column;
  }
  
  .image-section {
    flex: 0 0 50%;
    box-sizing: border-box;
    img {
        width: 752px;
        height: 1002px;
        @media @mobile {
        width: 320px;
        height: 426px;
      }
      @media @tablet {
        width: 326px;
        height: 434px;
      }
    }
    &.al-left {
      text-align: left;
      @media @tablet {
        text-align: center;
      }
    }
    &.al-right {
      text-align: right;
      @media @tablet {
        text-align: center;
      }
    }
    &.al-center {
      text-align: center;
    }
    @media @large-1280 {
      flex: 0 0 100%;
    }
  }
  /deep/ .video-js {
    width: 720px;
    height: 100%;
    // height: 394px;
    min-height: 400px;
    // flex: 0 0 50%;
    background-color: transparent;
    box-sizing: border-box;
    @media @mobile {
      width: 100vw;
      min-height: 200px;
    }
  }
  &__content {
    margin-bottom: 755px;
    text-align: left;
    padding: 50px;
    display: flex;
    flex-direction: column;
    line-height: 35px;
    box-sizing: border-box;

    @media screen and (max-width: 768px) {
      width: 438px;
      margin-top: -929px;
      margin-left: 316px;
    }
    @media screen and (max-width: 480px) {
      margin-top: -460px;
      margin-left: 0px;;
    }
    
    &.al-left {
      text-align: left;
      @media @large-1280 {
        text-align: center;
      }
    }
    &.al-center {
      text-align: center;
    }
    &.al-right {
      text-align: right;
      @media @large-1280 {
        text-align: center;
      }
    }
    
    &--main {
      padding: 10px;
      font-size: 32px;
      font-family: 'Franklin Gothic Medium', 'Arial Narrow', Arial, sans-serif;
      font-weight: 400;
      line-height: 36px;
      
      @media @mobile {
        font-size: 28px;
        line-height: 32px;
      }
    }
    &--sub {
      margin-top: 5px;
      padding: 10px;
      font-size: 14px;
      font-family: 'Lucida Sans', 'Lucida Sans Regular', 'Lucida Grande', 'Lucida Sans Unicode', Geneva, Verdana, sans-serif;
      font-weight: 400;
      line-height: 20px;
      @media @mobile {
        font-size: 12px;
        line-height: 20px;
      }
    }
  }
}
.align-left {
  flex-direction: row-reverse;
  @media screen and (max-width: 768px) {
    .image-section {
      img {
        width: 326px;
        height: 434px;
        margin-left: -39px;
        margin-bottom: 1336px;
        
      }
    }
    .media-with-text {
      &__content {
        width: 550px;
        margin-top: -624px;
        margin-left: 412px;
        margin-bottom: -756px;
      }
      &--main {
        font-size: 32px;
        font-family: 'Franklin Gothic Medium', 'Arial Narrow', Arial, sans-serif;
        font-weight: 400;
        line-height: 36px;
      }
      &--sub{
        @media tablet {
          margin-top: 97px;
        }
      }
    }
  }

  @media screen and (max-width: 480px) {
    flex-direction: column-reverse;
  }
}
.style-right {
  .image-section {
      img {
        width: 752px;
        height: 564px;
        margin-bottom: 430px;

      @media screen and (max-width: 768px) {
        width: 326px;
        height: 434px;
        //margin-left: -350px; 
      }
      @media screen and (max-width: 480px) {
        width: 320px;
        height: 240px;
        margin-left: 0px;
      }
    }
  }
}
@media screen and (max-width: 1160px) {

  .my-video-dimensions {
    width: 100%;
  }
  .video__content {
    margin-top: 20px;
    width: 100%;
  }
}

/deep/.video-js .vjs-big-play-button {
  top: 50% !important;
  left: 50% !important;
  transform: translate(-50%, -50%) !important;
}
/deep/.vjs-poster {
  background-size: cover;
}
</style>

<script>
import NoSSR from "vue-no-ssr";
import { isBrowser, isNode } from "browser-or-node";
import "video.js/dist/video-js.min.css";

export default {
  data() {
    return {
     
    };
  },
  props: ["settings"],
  computed: {
   
  },
  components: {
    "no-ssr": NoSSR,
    videoPlayer: () => {
      return isBrowser
        ? Promise.resolve(require("vue-video-player/src/player"))
        : Promise.resolve({})
    },
  },
  directives: {},
  mounted() {},
  beforeDestroy() {
    
  },
};
</script>
