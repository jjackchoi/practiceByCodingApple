/<template>
  <div class="black-bg" v-if="모달창열렸니 == true">
    <div class="white-bg">
      <img :src="원룸들[누른거].image" style="width: 100%;">
      <h4>{{ 원룸들[누른거].title }}</h4>  
      <p>{{ 원룸들[누른거].content }}</p>
      <textarea v-model="month"></textarea>
      <input v-model="month"> 
      <p> {{ month }}개월 선택함 : {{ 원룸들[누른거].price * month }}원</p>
      <button @click="close()">닫기</button>
      
    </div>
  </div>
</template>

<script>
export default {
    name: 'ModalComponent',
    data(){
      return {
        month: 1,
      }
    },
    props: {
      원룸들: Array,
      누른거: Number,
      모달창열렸니: Boolean,
    },
    methods: {
      close(){
        this.$emit('closeModal'); // $emit -> 부모한테 메세지 전송
      },
    }
}
</script>

<style>

</style>