<template>
  <div class="search">
      <h3>Choose a genre: </h3>
      <select name="search" id="">
          <option value="Rock">Rock</option>
      </select>
  </div>
</template>

<script>
export default {
    name: 'Search',
    data (){
        return {
            optionValue: '',
        };
    },
    methods: {
        sendOption(){
            console.log(this.optionValue);
            this.$emit('emitSearch', this.optionValue);
        }
    }
}
</script>

<style lang="scss">
    .search{
        text-align: center;
        padding: 1em 0;
        h3{
        display: inline-block;
        color: lightgray;
        font-size: 1em;
        }
    }
</style>