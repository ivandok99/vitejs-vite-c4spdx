<script>
//import { store } from './store.js'
export default {
  data() {
    return {
      visible: false,
      likes: 10,
      messages: [
        'asdkjh sdhkj dkjn kjn aksc kjnnads',
        'ksjdf  jnv or voapdv  knvdasak  ',
        'lksd v pldvnnllknvkmnkszmdnf apkmvdslv  kn lassmnv ',
        'kjsdv lkm pojf pa p  k pasd lvck ladkfv a',
      ],
      user: 'Ivandok99',
      date: '05/01/2023 15:34',

      //store,
    };
  },
  computed: {
    messages: async function () {
      //this.visible = false;
      const rawsponse = await fetch('/api/social/messages', {
        method: 'GET',
      });
    },
  },
};
</script>

<template>
  <div class="w3-panel w3-border w3-round-xlarge">
    <div class="w3-border-bottom w3-padding">
      <i id="useri" class="fa fa-user"></i>
      <span id="topbar" class="w3-margin-right">{{ user }}</span>
      <i id="heart" class="fa fa-heart"></i>
      <span id="topbar">{{ likes }}</span>
      <span class="w3-right">{{ date }}</span>
    </div>
    <p>{{ messages[0] }}</p>
  </div>
</template>

<style>
/*.h_container {
  background-color: #cac7c7;
  border-radius: 20px;
  box-shadow: 0 2px 8px rgba(0, 0, 0, 0.1);
  display: inline-block;
  width: 35px;
  height: 35px;
  text-align: center;
  line-height: 45px;
}*/

#topbar {
  font-size: 16px;
  margin-left: 3px;
}
#useri {
  color: grey;
  font-size: 20px;
}
#heart {
  color: grey;
  font-size: 20px;
}
#heart:hover {
  color: red;
}
</style>
