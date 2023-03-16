<template>
    <div class="card">
      <div style="border-radius:200px; height:200px; width:200px; background: #efedff; margin:0 auto;">
        <i class="checkmark">✓</i>
      </div>
        <h1>Thành công!</h1> 
        <p>Chúng tôi đã nhận được bộ câu trả lời khảo sát của doanh nghiệp bạn<br/> Cảm ơn đã tham gia khảo sát!</p>
    </div>
</template>

<script>
export default {
    name: "SubmitSuccess",
    
}
</script>

<style scoped>
      template {
        text-align: center;
        padding: 40px 0;
        background: #EBF0F5;
      }
        h1 {
          color: #0D6EFD;
          font-weight: 900;
          font-size: 40px;
          margin-bottom: 10px;
        }
        p {
          color: #404F5E;
          font-size:20px;
          margin: 0;
        }
      i {
        color: #0D6EFD;
        font-size: 100px;
        line-height: 200px;
        margin-left:-15px;
      }
      .card {
        background: white;
        padding: 60px;
        border-radius: 4px;
        box-shadow: 0 2px 3px #C8D0D8;
        display: inline-block;
        margin: 0 auto;
      }
</style>