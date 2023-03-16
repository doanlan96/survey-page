<template>
  <div class="modal">
      <div class="modal-progress">
        <div class="progress">
            <div id="progresss" class="progress-bar progress-bar-striped progress-bar-animated" role="progressbar" style="width:17%" aria-valuenow="17" aria-valuemin="0" aria-valuemax="100"></div>
        </div>
        <div style="display:flex; justify-content: space-around;">
            <span id="step1">Bước 1</span>
            <span id="step2">Bước 2</span>
            <span id="step3">Bước 3</span>
        </div>
      </div>
      <StepOne v-if="step===1" @next="secondStep"/>
      <StepTwo v-else-if="step===2" @prev="firstStep" @next="thirdStep"/>
      <StepThree v-else-if="step===3" @prev="secondStep" @next="fourthStep"/>
      <SubmitSuccess v-else-if="step===4"/>
  </div>
</template>

<script>
import StepOne from './StepOne.vue';
import StepTwo from './StepTwo.vue';
import StepThree from './StepThree.vue';
import SubmitSuccess from './SubmitSuccess.vue';
export default {
  name: 'MainPage',
  components: {
    StepOne,
    StepTwo,
    StepThree,
    SubmitSuccess,
  },
  data() {
    return {
      step: 1,
    }
  },
  methods: {
    firstStep() {
      let progress_bar = document.getElementById("progresss");
      progress_bar.setAttribute("style", "width:17%");
      progress_bar.setAttribute("aria-valuenow", "17");
      this.step = 1;
    },
    secondStep() {
      let progress_bar = document.getElementById("progresss");
      progress_bar.setAttribute("style", "width:50%");
      progress_bar.setAttribute("aria-valuenow", "50");
      this.step = 2;
    },
    thirdStep() {
      let progress_bar = document.getElementById("progresss");
      progress_bar.setAttribute("style", "width:83%");
      progress_bar.setAttribute("aria-valuenow", "83");
      this.step = 3;
    },
    fourthStep() {
      let progress_bar = document.getElementById("progresss");
      progress_bar.setAttribute("style", "width:100%");
      progress_bar.setAttribute("aria-valuenow", "100");      
      this.step = 4;
    },
  },
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
span {
  color: white;
}
.modal {
  /* text-align: center; */
  display: block;
  position: fixed;
  z-index: 1;
  left: 0;
  top: 0;
  width: 100%;
  height: 100%;
  overflow: auto;
  background-color: rgb(0,0,0);
  background-color: rgba(0,0,0,0.4);
}

.modal-progress {
  margin: 1% auto;
  padding: 30px;
  width: 40%;
}
</style>
