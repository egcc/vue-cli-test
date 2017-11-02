<template>
	<div>
    <h2>this is page1.</h2>
    <p>{{name}}</p>
    <hr/>
    <child1 prop-text="parent prop value wakaka..." v-bind:prop-two="propValue" v-bind:num-prop="1"></child1>
  </div>
</template>

<script>
import child1 from './p1child'
export default {
  data () {
    return {
      name: 'page1 name!!',
      propValue: 'propTwo value wakaka... this is a dynamic props value'
    }
  },
  components: { child1 }
}
</script>