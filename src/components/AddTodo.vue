<template>
    <form @submit="onSubmit" class="add-form">
        <div class="form-control">
            <input type="text" v-model="title" name="text" placeholder="Add Todo">
        </div>

        <div class="form-control">
            <input type="text" v-model="day" name="day" placeholder="Add Day">
        </div>

        <div class="form-control form-control-check">
            <label>Set Reminder</label>
            <input type="checkbox" v-model="reminder" name="reminder">
        </div>

        <input type="submit" value="Save Todo" class="btn btn-block">
    </form>
</template>

<script lang="ts">
export default{
    name: 'AddTodo',
    data(){
        return{
            title:'',
            day:'',
            reminder:false
        }
    },
    methods:{
        onSubmit(e){
            e.preventDefault();
            if(!this.title){
                alert('Please Add a Todo')
                return
            }

            const newTodo = {
                id: Math.floor(Math.random()*1000),
                title: this.title,
                day: this.day,
                reminder: this.reminder
            }

            this.$emit('add-todo', newTodo)

            this.title = ''
            this.day = ''
            this.reminder = false
        }
    }
}
</script>

<style scoped>
.add-form{
    margin-bottom: 60px;
}
.form-control{
    margin: 20px 0;
}
.form-control input{
    width: 100%;
    height: 40px;
    margin: 5px;
    padding: 3px 7px;
    font-size: 17px;
}
.form-control-check{
    display: flex;
    align-items: center;
    justify-content: space-between;
}
.form-control-check label{
    flex: 1;
}
.form-control-check input{
    height: 20px;
    flex: 2;
}
</style>