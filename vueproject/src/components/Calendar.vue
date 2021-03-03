<template>
    <div id="calendar">
        <div class="day" :class="{weekend: isWeekend(idx),selected:selected.has(idx)}" v-for="(item,idx) in days" :key="idx" @click="toggle(idx)">
            <div v-if="idx < 7">{{dayName(idx)}}</div>
            <div>{{item}}</div>
        </div>
    </div>
</template>

<script>
export default {
    data: function(){
        return {
            selected:new Set()
        }
    },
    methods:{
        toggle: function(idx){
            this.selected.has(idx) ? this.selected.delete(idx) : this.selected.add(idx)
        },
        isWeekend: idx => idx % 7 === 6 || idx % 7 === 5,
        dayName: idx => ['Po','Út','St','Čt','Pá','So','Ne'][idx]
    },
    computed: {
        days(){
            return [1,2,3,4,5,6,7,8,9,10,11,12,13,14,15,16,17,18,19,20,21,22,23,24,25,26,27,28,29,30,31];
        }

    }
}
</script>

<style scoped>
    .day{
        border-bottom:  1px solid #DADCE0;
        border-right: 1px solid #DADCE0;
        text-align: center;
        padding-top: 5px;
        font-size: 20px;
        cursor: pointer;
        transition: background-color 200ms, color 200ms;
    }
    #calendar {
        border-left:  1px solid #DADCE0;
        border-top: 1px solid #DADCE0;
        display:grid;
        grid-template-columns: repeat(7,1fr );
        grid-template-rows: repeat(5,1fr);
        height:100%;
        width:100%;
    }
    .weekend{
        color: #1B9CE2;
    }
    .selected{
        background-color:#1B9CE2;
        color:white;
    }
</style>
