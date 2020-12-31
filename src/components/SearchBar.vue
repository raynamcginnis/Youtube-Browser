<template>
    <div>
        <input @input = "onInput" placeholder="What would you like to search for?" />
    </div>
</template>

<script>
export default {
    name: 'SearchBar',
    methods: {
        onInput: function(event) {
            this.$emit('termChange', event.target.value);
        }
    }
}
</script>

<!-- scoped means that the css will only effect THIS component -->
<style scoped>
    input {
        width: 100%;
        text-align: center;
        font-style: italic;
        border: 1px solid #ddd;
        box-shadow: 0px 0px 2px darkgray;
        padding: 3px;
         }
    div {
        text-align: center;
        margin: 20px;
    }
</style>