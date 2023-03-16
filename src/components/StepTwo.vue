<template>
      <div class="modal-content">
        <p style="font-style: italic; margin: auto;">Lưu ý: Những nội dung có dấu (*) là bắt buộc.</p>
      </div>
      <div class="modal-content">
        <h5>1. Anh/ Chị vui lòng mô tả sản phẩm/dịch vụ/ngành nghề kinh doanh chính của Doanh nghiệp</h5>
        <div class="bo4">
          <input type="text" class="sizefull" name="name" placeholder="Vui lòng nhập câu trả lời">
        </div>
      </div>
      <div class="modal-content">
        <form>
            <h5>2. Hiện tại khách hàng của bạn thanh toán bằng hình thức nào?</h5>       
                <input type="checkbox" id="cash" value="Cash">
                <label for="cash"> Tiền mặt</label><br> 
                <input type="checkbox" id="qr" value="QR">
                <label for="qr"> Quét mã QR</label><br>
                <input type="checkbox" id="card" value="Card">
                <label for="card"> Quẹt thẻ</label><br>
                <input type="checkbox" id="banking" value="Banking">
                <label for="banking"> Chuyển khoản</label><br>    
        </form>
       </div>
       <div class="modal-content">
        <form>
            <h5>3. Cách thức bạn đối soát doanh thu hiện tại?</h5>       
            <input type="radio" id="value1" value="value1" name="question3">
            <label for="value1"> Đối soát thủ công bằng cách kiểm tra các giao dịch</label><br> 
            <input type="radio" id="value2" value="value2" name="question3">
            <label for="value2"> Đối soát tự động</label><br>
        </form>
       </div>
       <div class="modal-content">
        <form>
            <h5>4. Với hình thức thanh toán hiện tại cần xác minh giao dịch như thế nào?</h5>       
            <input type="checkbox" id="value1" value="value1">
            <label for="value1"> Chụp ảnh màn hình thanh toán của khách</label><br> 
            <input type="checkbox" id="value2" value="value2">
            <label for="value2"> Xác minh tự động trên app thanh toán</label><br>
            <input type="checkbox" id="value3" value="value3">
            <label for="value3"> Xác minh qua thông báo số dư ngay lập tức tới tài khoản ngân hàng</label><br>
            <input type="checkbox" id="value4" value="value4">
            <label for="value4"> Chưa có hình thức xác minh nào</label><br>                               
        </form>
       </div>
       <div class="modal-content">
        <form>
            <h5>5. Bạn đã từng bị thất thoát doanh thu do quá trình thanh toán của khách hàng hoặc do nhầm lẫn từ nhân viên không?</h5>       
            <input type="radio" id="value1" value="value1" name="question5">
            <label for="value1"> Rất nhiều lần</label><br> 
            <input type="radio" id="value2" value="value2" name="question5">
            <label for="value2"> Đã từng</label><br>
            <input type="radio" id="value3" value="value3" name="question5">
            <label for="value3"> Chưa từng</label><br>
            <input type="radio" id="value4" value="value4" name="question5">
            <label for="value4"> Khoản thất thoát trong giới hạn chấp nhận</label><br>                               
        </form>
       </div>
      <div style="width: 40%; margin: 2% auto;" class="button row m-t-30" >
                <div class="col-6">
                  <button class="btn btn-primary" @click="prevStep()">Back</button>
                </div>
                <div class="col-6">
                  <button class="btn btn-primary" @click="nextStep()">Next</button>
                </div>
      </div>         
  </template>
  
  <script>
  export default {
    name: 'StepTwo',
    components: {
    },
    created() {
        window.scrollTo({top: 0, behavior: "smooth"});
    },
    methods: {
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
  h5 {
    margin-bottom: 5%;
    margin-top: 3%;
  }
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
  input[type='checkbox'] {
    /* Double-sized Checkboxes */
    -ms-transform: scale(1.5); /* IE */
    -moz-transform: scale(1.5); /* FF */
    -webkit-transform: scale(1.5); /* Safari and Chrome */
    -o-transform: scale(1.5); /* Opera */
    transform: scale(1.5);
    padding: 10px;
    margin-right: 10px;
  }
  input[type='radio'] {
    /* Double-sized Checkboxes */
    -ms-transform: scale(1.5); /* IE */
    -moz-transform: scale(1.5); /* FF */
    -webkit-transform: scale(1.5); /* Safari and Chrome */
    -o-transform: scale(1.5); /* Opera */
    transform: scale(1.5);
    padding: 10px;
    margin-right: 10px;
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
  