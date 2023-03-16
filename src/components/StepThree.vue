<template>
      <div class="modal-content">
        <p style="font-style: italic; margin: auto;">Lưu ý: Những nội dung có dấu (*) là bắt buộc.</p>
      </div>
       <div class="modal-content">
        <form>
            <h5>6. Nếu chưa sử dụng, bạn có sẵn lòng áp dụng phương thức thanh toán bằng QR Code không?</h5>       
            <input type="radio" id="value1" value="value1" name="question6">
            <label for="value1"> Có</label><br> 
            <input type="radio" id="value2" value="value2" name="question6">
            <label for="value2"> Không</label><br>         
        </form>
       </div>
       <div class="modal-content">
        <form>
            <h5>7. Bạn có muốn sử dụng hình thức thanh toán do ngân hàng trực tiếp cung cấp đi kèm nhiều ưu đãi từ ngân hàng không?</h5>
            <input type="radio" id="value1" value="value1" name="question7" @click="openPage()">
            <label for="value1"> Có</label><br> 
            <input type="radio" id="value2" value="value2" name="question7">
            <label for="value2"> Không</label><br>
        </form>     
      </div>
      <div class="modal-content">
        <form>
            <h5>8. Bạn mong muốn có thể hoàn tất toàn bộ quy trình qua đăng kí online không?</h5>
            <input type="radio" id="value1" value="value1" name="question8" @click="openPage()">
            <label for="value1"> Hoàn tất Online</label><br> 
            <input type="radio" id="value2" value="value2" name="question8">
            <label for="value2"> Hoàn tất với hỗ trợ</label><br>
        </form>     
      </div>
      <div class="modal-content">
        <form>
            <h5>9. Với hình thức thanh toán mới, bạn có mong muốn áp dụng phương thức đối soát và xác minh giao dịch tự động không?</h5>
            <input type="radio" id="value1" value="value1" name="question9">
            <label for="value1"> Rất mong muốn</label><br> 
            <input type="radio" id="value2" value="value2" name="question9">
            <label for="value2"> Có cũng được</label><br>
            <input type="radio" id="value3" value="value3" name="question9">
            <label for="value3"> Chưa có nhu cầu</label><br>        
        </form>     
      </div>
      <div class="modal-content">
        <form>
            <h5>10. Bạn có muốn sử dụng miễn phí phần mềm Myshop và máy thanh toán Paybox không?</h5>
            <input type="radio" id="value1" value="value1" name="question10" @click="if(!checked){openPage();} changeCheckStatus();">
            <label for="value1"> Có</label><br> 
            <input type="radio" id="value2" value="value2" name="question10" @click="if(!checked){openPage();} changeCheckStatus();">
            <label for="value2"> Không</label><br>
            <input type="radio" id="value3" value="value3" name="question10" @click="if(!checked){openPage();} changeCheckStatus();" >
            <label for="value3"> Xem xét sử dụng</label><br>        
        </form>     
      </div>
      <div class="modal-content">
        <form>
            <h5>11. Nếu có, bạn mong muốn hoàn thành lắp đặt sau bao nhiêu ngày?</h5>
            <input type="radio" id="value1" value="value1" name="question11">
            <label for="value1"> 1 ngày</label><br> 
            <input type="radio" id="value2" value="value2" name="question11">
            <label for="value2"> 2 ngày</label><br>
            <input type="radio" id="value3" value="value3" name="question11">
            <label for="value3"> 3 ngày</label><br>        
        </form>     
      </div>
      <div style="width: 40%; margin: 2% auto;" class="button row m-t-30" >
                <div class="col-6">
                  <button class="btn btn-primary" @click="prevStep()">Back</button>
                </div>
                <div class="col-6">
                  <button class="btn btn-primary" @click="nextStep()">Submit</button>
                </div>
      </div>    
  </template>
  
  <script>
  export default {
    name: 'StepThree',
    components: {
    },
    created() {
        window.scrollTo({top: 0, behavior: "smooth"});
    },
    data() {
      return {
        checked: false,
      }
    },
    methods: {
        changeCheckStatus() {
          this.checked = true;
        },
        openPage() {
          window.open('https://vcci.com.vn/');
        },
        prevStep() {
            this.$emit("prev");
        },
        nextStep() {
          this.$emit("next");
        },
    }
  }
  </script>
  
  <!-- Add "scoped" attribute to limit CSS to this component only -->
  <style scoped>
  p {
    font-size: 13px;
  }
  button {
    width: 60%;
  }
  label{
    width: 90%;
    display: inline-block;
    vertical-align: middle;
  }  
  input[type='radio'] {
    margin-right: 5px;
  }
  .modal-content {
  
    text-align: left;
    background-color: #fefefe;
    margin: 1% auto;
    padding: 30px;
    padding-top: 10px;
    border: 1px solid #888;
    width: 40%;
  }
  .bo4 {
    display: flex;
    border: 0.5px solid #aaaaaa;
    border-radius: 5px;
    margin-bottom: 5px;
  }
  .sizefull {
    border: none;
    width: 100%;
    margin: 10px;
  }
  </style>
  