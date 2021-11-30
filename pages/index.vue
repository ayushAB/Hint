<template>
  <div class="flex justify-center items-center h-full max-w-5xl mx-auto">
    <div
      class="flex flex-col justify-center flex-1 max-w-2xl shadow-2xl px-6 py-10 bg-indigo-600 gap-3 rounded"
    >
      <div
        class="shadow-2xl p-3 bg-white rounded text-gray-700 font-bol text-center text-xl mb-10"
      >
        Hint Demo
      </div>
      <div>
        <div class="flex items-center w-full">
          <Hint v-if="hintNumber ==0 " :ripple-config="rippleConfig1" :hint-dailog-config="hintDailogConfig1" @hint-button-click="onHintDissmiss" />
          <label for="price" class="block text-sm font-medium text-white ml-1"
            >Price</label
          >
        </div>
        <div class="mt-1 relative rounded-md shadow-sm">
          <div
            class="absolute inset-y-0 left-0 pl-3 flex items-center pointer-events-none"
          >
            <span class="text-gray-500 sm:text-sm"> $ </span>
          </div>
          <input
            id="price"
            type="text"
            name="price"
            class="focus:ring-indigo-500 focus:border-indigo-500 block w-full pl-7 pr-12 sm:text-sm border-gray-300 rounded-md h-10"
            placeholder="0.00"
          />
          <div class="absolute inset-y-0 right-0 flex items-center">
            <label for="currency" class="sr-only">Currency</label>
            <select
              id="currency"
              name="currency"
              class="focus:ring-indigo-500 focus:border-indigo-500 h-full py-0 pl-2 pr-7 border-transparent bg-transparent text-gray-500 sm:text-sm rounded-md"
            >
              <option>USD</option>
              <option>CAD</option>
              <option>EUR</option>
            </select>
          </div>
        </div>
      </div>
      <div>
        <div class="flex items-center w-full">
          <Hint v-if="hintNumber == 1" :hint-dailog-config="hintDailogConfig2" @hint-button-click="onHintDissmiss" />
          <label for="price" class="block text-sm font-medium text-white ml-1"
            >Price</label
          >
        </div>
        <div class="mt-1 relative rounded-md shadow-sm">
          <div
            class="absolute inset-y-0 left-0 pl-3 flex items-center pointer-events-none"
          >
            <span class="text-gray-500 sm:text-sm"> $ </span>
          </div>
          <input
            id="price"
            type="text"
            name="price"
            class="focus:ring-indigo-500 focus:border-indigo-500 block w-full pl-7 pr-12 sm:text-sm border-gray-300 rounded-md h-10"
            placeholder="0.00"
          />
          <div class="absolute inset-y-0 right-0 flex items-center">
            <label for="currency" class="sr-only">Currency</label>
            <select
              id="currency"
              name="currency"
              class="focus:ring-indigo-500 focus:border-indigo-500 h-full py-0 pl-2 pr-7 border-transparent bg-transparent text-gray-500 sm:text-sm rounded-md"
            >
              <option>USD</option>
              <option>CAD</option>
              <option>EUR</option>
            </select>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {

  data (){
    return {
      hintNumber: 0,
      rippleConfig1:{
        height: 'h-3',
        width: 'w-3',
        color:'bg-gray-600'
      },
      hintDailogConfig1: {
          hintText:'This is the Hint 2',
          buttonPostion:  'end',
          backgroundColor:  'bg-gray-800',
          btnColor: 'bg-white',
          btnTextColor:'text-gray-800',
          hintTextColor:'text-white'
        },
        hintDailogConfig2: {
          hintText:'This is the Hint 2',
          buttonPostion:  'end',
          backgroundColor:  'bg-indigo-800',
          btnColor: 'bg-white',
          btnTextColor:'text-gray-800',
          hintTextColor:'text-white'
        }
    }
  },

  methods:{
    onHintDissmiss() {
      this.hintNumber++;
    },
  }
}
</script>
<style>
html,
body {
  height: 100%;
}
#__nuxt,
#__layout {
  height: 100%;
  background-color: rgb(26, 24, 24);
}
</style>
