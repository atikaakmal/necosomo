<template>
      <li>
         {{item.name}}
         <button @click="delMethod(index)"   title="Delete">delete</button>
       </li>
</template>

<script>
export default {
  name: 'ListOfItems',
  props: {
    delMethod: {type: Function},
    item: {type: Object},
    index: {type: Number},
  }
}
</script>