<template>
  <div class="skills">
    <h1 v-once>{{name}}</h1>
    {{ btnState ? 'The button is disabled' : 'The button is active'}}
    <button v-on:click="changeName" v-bind:disable="btnState">Change Name</button>
    <ul>
      <li v-for="(data, index) in skills" :key="index">{{index}} {{data.skill}}</li>
    </ul>
      <p v-if="skills.length >= 1">You have more than 1 skill</p>
      <p v-else>You have less than or equal to 1 skill</p>
      <!-- <div v-bind:class="{ 'alert': showAlert, 'anotherClass': showClass}"></div> -->
      <div v-bind:class="alertObj"></div>
      <!-- <div v-bind:style="{ backgroundColor: bgColor, width: bgWidth, height: bgHeight, border: bdColor }"></div> -->
      <div v-bind:style="alertObjTwo"></div>
  </div>
</template>

<script>
export default {
  name: 'Skills',
  props () {
  },
  data () {
    return {
      name: 'Skills Course',
      btnState: true,
      showAlert: true,
      showClass: true,
      skills: [
        {'skill': 'vuejs'},
        {'skill': 'front end developer'}
      ],
      alertObj: {
        alert: true,
        anotherClass: true
      },
      bgColor: 'orange',
      bgWidth: '100%',
      bgHeight: '30px',
      bdColor: '1px solid red',
      alertObjTwo: {
        backgroundColor: 'green',
        width: '100%',
        height: '30px',
        border: '1px solid red'
      }
    }
  }
}
</script>

<style scoped> /* external file <style src="./Skills.css">  */
  .alert{
    background-color: yellow;
    width:100%;
    height: 30px;
  }
  .anotherClass{
    border: 1px solid red;
  }
</style>
