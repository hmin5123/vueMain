<template>
  <div class="about">
    <h1>This is an ataBinding page</h1>
    <h1>Hello {{ titile }}</h1>
    <br>

    <div>{{ htmlString }}</div>
    <div v-html="htmlString"></div>
    <br>

    <input type="text" v-model="valueModel">
    <br><br>

    <input type="number" v-model.number="numberModel">
    <br><br>

    <textarea v-model="message"></textarea>
    <br><br>

    <div>
      <select v-model="city">
        <option value="02">서울</option>
        <option value="21">부산</option>
        <option value="064">제주</option>
      </select>
    </div>
    <br><br>

    <div>
        <label for="">
          <input type="checkbox" v-model="checked">
          {{ checked }}
        </label>
      </div>
      <br><br>

      <div>
        <label for="">
          <input type="checkbox" v-model="checked2" true-value="yes" false-value="no">
          {{ checked2 }}
        </label>
      </div>
      <br><br>

      <div>
        <label for="">
          <input type="checkbox" v-model="checked3" value="서울">
          서울
        </label>
        <label for="">
          <input type="checkbox" v-model="checked3" value="부산">
          부산
        </label>
        <label for="">
          <input type="checkbox" v-model="checked3" value="제주">
          제주
        </label>
        <br>
        <span>체크한 지역 : {{ checked3 }}</span>
      </div>
      <br><br>

      <div>
        <label for="">
          <input type="radio" v-bind:value="radioValue1" v-model="picked">
          서울
        </label>
        <label for="">
          <input type="radio" v-bind:value="radioValue2" v-model="picked">
          부산
        </label>
        <label for="">
          <input type="radio" v-bind:value="radioValue3" v-model="picked">
          제주
        </label>
        <br>
        <span>선택한 지역 : {{ picked }}</span>
      </div>
      <br>

      <div>
        <img v-bind:src="imgSrc">
      </div>
      <br>

      <div>
        <input type="text" v-model="textValue">
        <button type="button" v-bind:disabled="textValue === ' '">Click</button>
      </div>
      <br><br>

      <div class="container" v-bind:class="{
        'active': isActive, 'text-red': hasError
        }">
        Class Binding
      </div>
      <br><br>

      <div class="container2" v-bind:class="[activeClass, errorClass]">
        Array Class Binding
      </div>
      <br><br>

      <div v-bind:style="styleObject">인라인 스타일 바인딩</div>
      <br><br>

      <div v-bind:style="[baseStyle, addStyle]">배열 인라인 스타일 바인딩</div>
      <br><br><br><br><br><br>
  </div>
</template>

<script>
export default {
  data () {
    return {
      htmlString: '<p style="color:red;">This is a red String</p>',
      valueModel: 'South Korea',
      numberModel: 3,
      message: '여러 줄을 입력할 수 있는 textarea 입니다.',
      city: '064',
      checked: true,
      checked2: 'yes',
      checked3: [],
      picked: ' ',
      radioValue1: '서울',
      radioValue2: '부산',
      radioValue3: '제주',
      imgSrc: 'https://kr.vuejs.org/images/logo.png',
      textValue: '',
      isActive: true,
      hasError: false,
      activeClass: 'active',
      errorClass: 'text-red',
      styleObject: {
        color: 'red',
        fontSize: '23px'
      },
      baseStyle: 'background-color: yellow; width: 100%; height: 100px',
      addStyle: 'color: red; font-weight: bold;'
    }
  }
}
</script>

<style scoped>
  .container, .container2 {
    width: 100%;
    height: 100px;
  }
  .active {
    background-color: yellow;
    font-weight: bold;
  }

  .text-red {
    color: red;
  }
</style>
