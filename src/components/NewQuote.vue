<template>
    <div class="row">
        <!-- <form> -->
            <div class="col-md-6 offset-md-3 col-sm-8 offset-sm-2 form-group">
                <label for="quote" class="font-weight-bold display-6">Quote</label>
                <textarea name="quote" 
                rows="3" cols="30" 
                placeholder="Add a nice quote.."
                v-model="quote" 
                class="form-control"></textarea>
            </div>
            <div class="col-md-6 offset-md-3 col-sm-8 offset-sm-2 form-group">
                <div v-if="alert" class="mb-2 alert alert-danger">{{ alert }}</div>
                <button 
                class="btn btn-primary form-control" 
                type="submit"
                @click="createQuote"
                >Add Quote</button>
            </div>
        <!-- </form> -->
            
    </div>
</template>

<script>

export default {
    data: function(){
        return{
            quote: '',
            alert: ''
        };
    },
    methods: {
        createQuote(){
            if(this.quote.trim()){
                this.$emit('quoteAdded',this.quote);
                this.quote = '';
                this.alert='';
            }
            else{
                this.alert="Please type something";
                // return alert('Please type something');
            }
        }
    }
}
</script>

<style scoped>

</style>
