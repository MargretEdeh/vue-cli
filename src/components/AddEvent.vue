<template>
    <div>
        <form @submit="onSubmit" class="form">
            <div class="the-form">
                <label>Event</label>
            <input  class="input" v-model="social" type="text" name="social" placeholder="Add an Event"/>
            </div>
            <div class="the-form">
              <label>Date</label>
            <input class="input" v-model="date" type="text" name="date" placeholder="Date of Event"/>
            </div>
            <div class="the-form">
              <label>Color</label>
            <input class="input" v-model="color" type="text" name="color" placeholder="Color code"/>
            </div>
            <div class="the-form">
            <input class="btn-add" type="submit" name="color" value="Add Event"/>
            </div>
        </form>
    </div>
</template>

<script>
export default {
    name: "FormPart",
    data(){
        return{
            social: '',
            date:  '',
            Color: '',
        }
    },
    methods:{
        onSubmit(e) {
            e.preventDefault()
            if(!this.social){
                alert("Please add an event")
            }
            const newTask ={
                id: Math.floor(Math.random()*100000),
                social: this.social,
                date: this.date,
                color: this.color
            }
            this.$emit('add-event', newTask)
                console.log(newTask)
            this.social=" ",
            this.date= " "
            this.color=" "
        }
    }
}
</script>
<style scoped>
.form{
    border: 1px solid white;
    width: 400px;
    margin: 4em 0 0 5em;
    padding: 1em;
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
}
.the-form{
    display: flex;
    flex-direction: column;
    margin: 7px;
}
.input{
    padding: 17px;
    width: 350px;
    border-radius: 8px;
    border: none;
}
.btn-add{
    width: 380px;
    padding: 15px;
    background-color: cyan;
    border: none;
    border-radius: 8px;
    font-weight: 600;
    font-size: 15px;
}
.btn-add:hover{
    background-color: rgb(12, 160, 160);
}
</style>