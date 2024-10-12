<template>

  <div class="teacher-card sm:w-[252px] shadow-md hover:shadow-2xl">
    <a href="/s">
      <div class="teacher-card__image h-[192px] w-[192px] m-auto ">
        <img class="rounded-full w-full h-full m-auto" src="https://picsum.photos/200/300" alt="">
      </div>
      <h3 class="teacher-card__name text-2xl text-center mt-[10px]">Nguyễn Văn A</h3>
    </a>
    <p class="teacher-card__description p-[10px] sm:p-[20px]">
      Qualified Teacher with a Bachelor of Education degree as well as international experience teaching English!
    </p>
  </div>

</template>


<script setup>

const props = defineProps({
  cardWidth: {
    type: String,
    default: '252'
  },
  cardImageSize: {
    type: String,
    default: '192'
  },
})

console.log('cardWidth', props.cardWidth)
console.log('cardImageSize', props.cardImageSize)

</script>


<style>

.teacher-card{
  background-color: #fff;
  border-radius: 10px;
  box-shadow: 0px 0px 10px rgba(0, 0, 0, 0.1);
  padding: 20px 0 ;
  transition: all 0.3s ease;
  animation-duration: 0.3s;
  animation-timing-function: ease-in-out;
  animation-name: scaleTeacherCard;
}

@keyframes scaleTeacherCard {
  0% {
    transform: scale(0.4);
  }
  100% {
    transform: scale(1);
  }
}

.teacher-card:hover .teacher-card__name {
  transition: ease-in-out;
  transition-duration: 0.2s;
  color: #40a9ff;
}

@media (max-width: 478px) {
  .teacher-card .teacher-card__image{
    width: 150px;
    height: 150px;
  }
}

</style>