<template>
  <div class="w-full h-full flex flex-col">
    <div class="w-full h-60 flex-none" :class="{'':!jump,'fixed top-0':jump}">
      <iframe
        class="w-full h-full"
        src="https://www.youtube.com/embed/DxcJbrs6rKk"
        title="YouTube video player"
        frameborder="0"
        allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture"
        allowfullscreen
      ></iframe>
    </div>
    <div class="flex-grow overflow-y-scroll">
      <div id="messageList" class="w-full h-full">
        <div
          class="w-full p-2 border-b last:border-0"
          v-for="index in 30"
          :key="index"
        >
          <div class="font-bold text-sm text-gray-500">username</div>
          <div class="ml-3">
            (username content)(username content)(username content)(username
            content)(username content)(username content)(username content)
          </div>
        </div>
        <div class="w-full h-16"></div>
      </div>
    </div>
    <div class="flex-none relative">
      <div class="flex p-3 gap-3 border-t border-gray-200 h-16">
        <input
          class="
            p-2
            flex-1
            border-b-2
            focus:border-blue-500
            outline-none
            transition-all
          "
          placeholder="留言..."
          @focus="changeState('focus')"
          @blur="changeState('blur')"
        />
        <button class="w-16 bg-blue-600 text-white rounded-md">送出</button>
      </div>
      <div
        class="
          absolute
          -top-16
          w-full
          h-16
          bg-gradient-to-t
          from-white
          to-transparent
          pointer-events-none
          z-0
        "
      ></div>
      <div
        class="
          absolute
          -top-3
          w-full
          h-3
          bg-gradient-to-t
          from-gray-200/50
          to-transparent
          pointer-events-none
          z-0
        "
      ></div>
    </div>
  </div>
</template>

<script>
export default {
  data(){
    return {
      jump: false
    }
  },
  methods:{
    changeState( state ){
      console.log(state)
      if(state==='focus'){
        this.jump = true;
      }else{
        this.jump = false;
      }
    }
  }
}
</script>
