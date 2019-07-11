<template>
<div>
<button v-on:click="counter++">increase</button>
<button v-on:click="counter--">decrease</button>
<p>counter:{{ counter }}</p>
<p>result:{{ result() }}</p>
<h2 v-html="finshedlink"></h2>
<button v-on:mousemove="timer">timer</button>
<p>{{hours}}:{{minutes}}:{{seconds}}</p>
<p v-on:mousemove="updates">{{x}}/{{y}}-<span v-on:mousemove.stop="">stop</span></p>
<input type="text" v-on:keyup.enter="alertbox">
</div>
</template>
<script>
export default{
	data(){
	return{
	counter:0,
	hours:0,
	minutes:0,
	seconds:0,
	x:0,
	y:0,
	finshedlink: '<a href="http://www.google.com">google</a>'
    }
	},
	watch:{
	updates:function(newValue,oldValue){
	console.log(newValue,oldValue)
	}
	},

	methods:{
    result:function(){
    return this.counter >5 ? 'greater 5':'smaller 5'
    },
	timer: function(){
	this.hours++;
	this.minutes+=60;
	this.seconds+=360;
	},
	updates:function(event){
	this.x=event.clientX;
	this.y=event.clientY;
	},
	alertbox: function(){
    alert("required strong text")
	},
	
}
}
</script>
