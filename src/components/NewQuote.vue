<template>
    <div class="row form-area">
        <div class="form-group col-md-6 col-sm-10 col-xs-10">
            <label for="add-quote">Your quote:</label>
            <textarea v-model="quoteText" class="form-control" rows="5" id="add-quote"></textarea>
        </div>
        <button class="btn btn-primary" @click="increaseQuoteAmount()" :class="{ disabled: quoteText.length == 0 }">Add quote</button>    
    </div>
</template>

<script>
export default {
  data() {
      return {
          quoteText: '',
      }
  },
  methods: {
    increaseQuoteAmount() {
        if(this.quoteText.length) {
            this.$emit('increaseQuoteAmount' , this.quoteText)
        }
    }
  }
}
</script>

<style scoped>

</style>
