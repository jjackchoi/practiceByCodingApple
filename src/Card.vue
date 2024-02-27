/<template>
  <div>
    <img :src="원룸.image" class="room-img">
    <h4 @click="$emit('openModal', 원룸.id)">{{ 원룸.title }}</h4>
    <p>{{ 원룸.price }}원</p>
  </div>
</template>

<script>
export default {
    name: 'CardComponent',
    props: { // props로 보낸 데이터는 수정금지(read only)
        원룸들: Array,
        원룸: Object,
    },
    methods: {
        send(){
            this.$emit('openModal', this.원룸.id);
        },
    }
}
</script>

<style>

</style>