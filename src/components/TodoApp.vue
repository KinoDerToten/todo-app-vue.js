<template>
    <main>
        <div class="container m-auto">
            <div class="row">
                <div class="col-12">
                    <div class="row justify-content-between">
                        <div class="col-2"><h1 class="text-white">Todo</h1></div>
                        <div class="col-1"><button type="submit"><i class="far fa-sun fa-2x sun"></i></button></div>
                    </div>
                </div>
                <div class="col-12 mt-3">
                    <div class="row">
                        <div class="col-11 enter-list">
                            <input v-model="newTask" type="text" placeholder="Create a new todo...">
                        </div>
                        <div class="col-1 enter-button">
                            <button v-on:click="addTask" type="submit"><i class="fas fa-arrow-right fa-2x arrow"></i></button>
                        </div>
                    </div>
                </div>
                <div class="col-11 list-comments">
                    <div class="list-group">
                        <div class="list-group-item" v-for="(taskList, index) in tasks" :key="index">
                            {{taskList.title}}
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </main>
</template>
<script>

export default {
    data() {
        return {
           newTask: '',
           tasks: []
        }
    },
    methods: {
        addTask: function() {
            this.tasks.push({
                title: this.newTask
            })
            this.newTask = ''
        }
    }
}
</script>

<style scoped>
main{
    height: 100vh;
    padding-top: 70px;
}

    .container{
        width: 550px;
        height: 680px;
    }

    button{
        background: none;
        border: none;
    }

    .sun{
        color: #FFF;
    }

    input{
        width: 100%;
    }

    .arrow{
        color: #FFF;
    }

    .enter-list{
        background: #25273c;
        margin: 0;
        padding: 0;
        border-radius: 5px;
    }

    .enter-list input{
        height: 100%;
        background: transparent;
        border: none;
        padding: 10px;
        color: white;
    }

    .enter-list input:focus{
        box-shadow: 0 0 0 0 ;
        outline: none;
    }

    .list-comments{
        margin: 0;
        margin-top: 20px;
        padding: 0;
        background: #25273c;
        border-radius: 5px;
    }

    .list-group-item{
        background: transparent;
        color: #818398;
        border: none;
    }

    .list-group-item input{
        width: 50px;
    }

    .round {
  position: relative;
}

    .round label {
    background-color: transparent;
    border: 1px solid #FFF;
    border-radius: 50%;
    cursor: pointer;
    height: 28px;
    left: 0;
    position: absolute;
    top: 0;
    width: 28px;
    }

    .round label:after {
    border: 2px solid #fff;
    border-top: none;
    border-right: none;
    content: "";
    height: 6px;
    left: 7px;
    opacity: 0;
    position: absolute;
    top: 8px;
    transform: rotate(-45deg);
    width: 12px;
    }

    .round input[type="checkbox"] {
    visibility: hidden;
    }

    .round input[type="checkbox"]:checked + label {
    background: linear-gradient(to bottom, #57ddff 0%, #c058f3 100%);
    background-image: linear-gradient(to bottom, #57ddff 0%, #c058f3 100%);
    }

    .round input[type="checkbox"]:checked + label:after {
    opacity: 1;
    }
</style>