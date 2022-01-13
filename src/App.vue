<script>
  import Card from './components/Card.vue'
  import Content from './components/Content.vue'
  import Edit from './components/Edit.vue'
  import {ref} from "vue";

  export default{
    name: 'App',
    components: {Card, Content, Edit},
    setup(){
      const shouldDisplay = ref(false);
      const newUser = ref('')
      const loadEdition = (res) => {
        shouldDisplay.value = res
      }
      const completeEditing = ({userName, isDisplayed}) => {
        shouldDisplay.value = userName
        newUser.value = isDisplayed
      }
      return{
        shouldDisplay, newUser, loadEdition, completeEditing
      }
    }
  }
</script>

<template>
  <div class="w-full h-full flex justify-center py-40">
    <Card v-if="!shouldDisplay">
      <template #customComponent>
        <Content @goToEdit="loadEdition" :user="newUser"/>
      </template>
    </Card>

    <Card v-else>
      <template #customComponent>
        <Edit @goToHome="completeEditing" @goToHomeWithoutModifies="shouldDisplay=false"/>
      </template>
    </Card>
  </div>
</template>
