<template>
    <div class="modal-content">
      <h4 style="margin-bottom: 5%;"> Thông tin doanh nghiệp </h4>
      <p>Mã số thuế: 0110010000</p>
      <p>Tên công ty: <b>Moonshine</b></p>
      <p>Địa chỉ: 116 Trần Duy Hưng</p>
      <p>Người đại diện: Trang</p>
      <Form :validation-schema="schema">
              <label>Tên người liên hệ để phối hợp (*)</label>
              <div class="bo4">
                <Field
                    name="name"
                    type="text"
                    placeholder="Vui lòng nhập tên người liên hệ"
                    class="sizefull"
                />
              </div>
              <ErrorMessage name="name" class="fs-18 text-danger d-block" />

              <label></label>
              <div class="bo4">
                <Field name="position" class="sizefull" as="select">
                  <option selected="true" disabled="true" value="">Vui lòng chọn chức vụ (*)</option>
                  <option value="0">Chủ tịch/Phó chủ tịch</option>
                  <option value="1">Giám đốc/Tổng giám đốc</option>
                  <option value="2">Phó Giám đốc/Phó Tổng giám đốc</option>
                  <option value="3">Chủ doanh nghiệp</option>
                  <option value="4">Ban lãnh đạo (Chức vụ khác)</option>
                  <option value="5">Kế toán trưởng</option>
                  <option value="6">Trưởng phòng/Trưởng ban</option>
                  <option value="7">Kế toán viên</option>
                  <option value="8">Nhân viên (Khác)</option>
                  <option value="9">Kế toán thuê ngoài</option>
                </Field>
              </div>
              <ErrorMessage name="position" class="fs-18 text-danger d-block" />

              <label>Email (*)</label>
              <div class="bo4">
                <Field
                    name="email"
                    type="email"
                    placeholder="Vui lòng nhập email"
                    class="sizefull"
                />
              </div>
              <ErrorMessage name="email" class="fs-18 text-danger d-block" />
              
              <label>Số điện thoại di động để liên hệ (*)</label>
              <div class="bo4">
                <Field
                    name="phone"
                    type="number"
                    placeholder="Vui lòng nhập số điện thoại di động"
                    class="sizefull"
                />
              </div>
              <ErrorMessage name="phone" class="fs-18 text-danger d-block" />

              <label></label>
              <div class="bo4">
                <Field name="age" class="sizefull" as="select">
                  <option selected="true" disabled="true" value="">Vui lòng chọn độ tuổi (*)</option>
                  <option value="0">Dưới 26 tuổi</option>
                  <option value="1">Từ 26 đến 30 tuổi</option>
                  <option value="2">Từ 31 đến 40 tuổi</option>
                  <option value="3">Từ 41 đến 50 tuổi</option>
                  <option value="4">Trên 50 tuổi</option>
                </Field>
              </div>
              <ErrorMessage name="age" class="fs-18 text-danger d-block" />

              <label>Số CMT/CCCD người liên hệ</label>
              <div class="bo4">
                <Field
                    name="identify"
                    type="number"
                    placeholder="Vui lòng nhập số CMT/CCCD người liên hệ"
                    class="sizefull"
                />
              </div>
              <ErrorMessage name="identify" class="fs-18 text-danger d-block" />

              <label>Số điện thoại cơ quan (nếu có)</label>
              <div class="bo4">
                <Field
                    name="phone1"
                    type="number"
                    placeholder="Vui lòng nhập số điện thoại cơ quan"
                    class="sizefull"
                />
              </div>
              <ErrorMessage name="phone1" class="fs-18 text-danger d-block" />

              <p style="font-style: italic; margin-top: 5%;">Ghi chú: Những nội dung có dấu (*) là bắt buộc.</p>

              <div style="margin-top: 20px" class="button row m-t-30" >
                <div style="text-align: center;">
                  <button class="btn btn-primary" style="width: 30%;" @click.prevent="nextStep();">Next</button>
                </div>
              </div>
      </Form>
    </div>
</template>

<script>
import { Form, Field, ErrorMessage } from "vee-validate";
import * as yup from "yup";
export default {
  name: 'StepOne',
  components: {
    Form,
    Field,
    ErrorMessage,
  },
  created() {
    window.scrollTo({top: 0, behavior: "smooth"});
  },
  data() {
    const schema = yup.object().shape({
      name: yup
          .string()
          .required("Tên người liên hệ bị trống"),
      position: yup
          .string()
          .required("Chức vụ bị trống"),
      email: yup
          .string()
          .required("Email bị trống")
          .email("Email sai định dạng"),
      phone: yup
          .number()
          .positive()
          .required("Số điện thoại bị trống"),
      age: yup
          .number()
          .required("Độ tuổi bị trống"),
    })
    return {
      schema,
    }
  },
  methods: {
    nextStep() {
        this.$emit("next");
    }    
  }
}
</script>

<style scoped>
p {
  font-size: 13px;
}
label {
  font-size: 15px;
  margin-top: 3%;
}

input::-webkit-outer-spin-button,
input::-webkit-inner-spin-button {
    /* display: none; <- Crashes Chrome on hover */
    -webkit-appearance: none;
    margin: 0; /* <-- Apparently some margin are still there even though it's hidden */
}

input[type=number] {
    -moz-appearance:textfield; /* Firefox */
}

.modal-content {

  text-align: left;
  background-color: #fefefe;
  margin: 1% auto;
  padding: 30px;
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