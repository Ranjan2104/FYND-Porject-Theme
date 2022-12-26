<template>
  <section :class='["media-with-text" ,"full-width-section", "mirror-" + settings.props.mirror.value, "style-" + settings.props.styleV.value]' >
    <div :class='["image-section"]'>
      <img :src="settings.props.image.value" />
    </div>
    <div  :class='["media-with-text__content"] '>
      <div class="media-with-text__content--main">
        {{ settings.props.text.value }}
      </div>
      <div class="media-with-text__content--sub">
        {{ settings.props.heading.value }}
      </div>
    </div>
    <div class="whites100"></div>
  </section>
</template>

<!-- #region  -->

<settings>
{
  "name": "brand-story-section",
  "label": "Brand Story Section",
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
              "value": "style1",
              "text": "Style 1"
          },
          {
              "value": "style2",
              "text": "Style 2"
          }
      ],
      "default": "style1",
      "label": "Layout"
    },
    {
      "type": "select",
      "id": "mirror",
      "options": [
          {
              "value": "on",
              "text": "ON"
          },
          {
              "value": "off",
              "text": "OFF"
          }
      ],
      "default": "off",
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
  @media screen and (max-width: 768px) {
    flex-direction: row;
  }
  @media screen and (max-width: 480px) {
    flex-direction: column;
  }
  
  .image-section {
    flex: 0 0 50%;
    box-sizing: border-box;
    width: 100%;
    max-width: 100%;
    height: auto;
    img {
        width: 752px;
        height: 1002px;

      @media screen and (max-width: 768px) {
        width: 326px;
        height: 434px;
      }
      @media @mobile {
        width: 320px;
        height: 426px;
      }
    }
    @media screen and (max-width: 768px) {
        flex: 0 0 50%;
        width: 50%;
        padding-left: 32px;
        padding-top: 18px;
    }
    @media screen and (max-width: 480px) {
      width: auto;
      margin-right: auto;
    }
  }

  &__content {
    align-self: flex-start;
    text-align: left;
    padding-left: 50px;
    padding-right: 50px;
    display: flex;
    flex-direction: column;
    line-height: 35px;
    box-sizing: border-box;
    
    @media screen and (max-width: 480px) {
      padding-left: 25px;
    }
    
    &--main {
      padding: 10px;
      font-size: 32px;
      font-family: 'Franklin Gothic Medium', 'Arial Narrow', Arial, sans-serif;
      font-weight: 400;
      line-height: 36px;

      @media screen and (max-width: 768px) {
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

      @media screen and (max-width: 768px) {
        font-size: 12px;    
        line-height: 20px;
      }
    }
  }
}

.mirror-on {
  flex-direction: row-reverse;
  @media screen and (max-width: 480px) {
    flex-direction: column-reverse;
  }
}

.style-style2 {
    .image-section {
      img {
        height: 564px;
        @media screen and (max-width: 768px) {
          height: 244px;
          padding-bottom: 210px
        }
        @media @mobile {
          height: 240px;
          padding-bottom: 0px
        }
      }
  }
}
.media-with-text {
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
