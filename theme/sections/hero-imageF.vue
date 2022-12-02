<template>
  <div>
    <fdk-link :link="settings.props.button_link.value">
      <emerge-img
        v-if="settings.props.image.value"
        :src="settings.props.image.value"
        :sources="[]"
        class="hero__image"
      />
      <fdk-placeholder v-else type="banner-1" />
      <div class="overlay">
        <div class="overlay__content">
          <img
            v-if="settings.props.overlay_image.value"
            class="overlay__image"
            :src="settings.props.overlay_image.value"
          />
        </div>
      </div>
    </fdk-link>
  </div>
</template>
<!-- #region  -->

<settings>
{
    "name": "banner",
    "label": "Banner",
    "props": [
        {
            "id": "image",
            "type": "image_picker",
            "label": "Desktop Image",
            "default": ""
        },
        {
            "type": "image_picker",
            "id": "overlay_image",
            "default": "",
            "label": "Mobile Image",
            "info": "Overlay Image"
        },
        {
            "type": "url",
            "id": "button_link",
            "default": "",
            "label": "Redirect Link"
        }
    ]
}
</settings>
<!-- #endregion -->
<style scoped lang="less">
.hero__image {
  /deep/ .fy__img {
    width: 100%;
    @media @mobile{
      display: none;
    }
  }
}
.overlay {
  position: absolute;
  top: 55%;
  left: 50%;
  width: 100%;
  transform: translate(-50%, -50%);
  // display: flex;
  &__content {
    flex-direction: column;
    padding: 0 @header-padding-desktop;
    width: 30%;
    align-items: center;
    text-align: center;
    @media @mobile {
      width: 100%;
      padding: 0;
    }
  }
  &__left {
    align-items: flex-start;
    justify-content: flex-start;
    @media @mobile {
      align-items: center;
      justify-content: center;
    }
    .overlay__content {
      // display: contents;
      align-items: flex-start;
      text-align: left;
      @media @mobile {
        align-items: center;
        text-align: center;
        // width: 100%;
      }
    }
  }
  &__center {
    align-items: center;
    justify-content: center;
  }
  &__right {
    align-items: flex-end;
    justify-content: flex-end;
    @media @mobile {
      align-items: center;
      justify-content: center;
    }
    .overlay__content {
      
      align-items: flex-end;
      text-align: right;
      @media @mobile {
        align-items: center;
        text-align: center;
      }
    }
  }
  &__image {
    display: none;
    max-width: 100%;
    margin-bottom: 10px;
    @media @mobile {
      display: flex;
    }
  }
  &__text {
    font-size: 40px;
    line-height: 49px;
    font-weight: 700;
    margin-bottom: 48px;
    @media @tablet {
      margin-bottom: 35px;
    }
    @media @mobile {
      font-size: 14px;
      margin-bottom: 30px;
    }
  }
}
</style>

<script>
import btn from "./../components/common/button.vue";
import emergeImage from "../global/components/common/emerge-image.vue";

export default {
  components: {
    "emerge-img": emergeImage
  },
  props: ["settings", "global_config"],
  watch: {
    settings: function(newVal, oldVal) {},
  },
  mounted() {},
  data: function() {
    return {
      // url: ""
    };
  },
};
</script>
