<template lang="html">
  <!-- <div class="one-color"> -->
    <div class="one-colorpanel one-hsv">
      <div class="one-colors" @mousedown="choose" ref="vcolors">
        <div class="one-color-pointer" :style="pointerPosition"></div>
        <div class="one-color-base" :style="{background: hueString}"></div>
        <div class="one-brightness-light"></div>
        <div class="one-brightness-dark"></div>
      </div>
      <div class="one-color-control">
        <div class="one-color-present">
          <div :style="{backgroundColor: rgbString}"></div>
        </div>
        <div class="one-color-slider">
          <div class="one-hue">
            <slider :vertical="false" :value="hueSlideValue" @change="hueSlide"></slider>
          </div>
          <div class="one-opacity">
            <slider :style="opacityStyle" :value="opacitySlideValue" @change="opacitySlide"></slider>
          </div>
        </div>
      </div>
      <div class="one-color-value">
        <a href="javascript:;" class="one-color-toggle" @click="toggleMode"></a>
      </div>
      <div class="one-color-stash">
        <div class="one-color-stash-wrap">
          <ul>
            <li @click="setColor(item)" v-for="item in stash" :style="{backgroundColor: item}" :class="{'transparent': item === 'rgba(255,255,255,0)'}"></li>
          </ul>
        </div>
        <a href="javascript:;" class="one-color-toggle" @click="toggleStash"></a>
      </div>
    </div>
  <!-- </div> -->
</template>

<script src="./main.js"></script>
<style src="./style.less" lang="less"></style>
