<template>
<div>
<h1>{{name}}</h1>
<p>{{hello()}}</p>
<span>{{msg}}</span>
<hr>
<input type="text" v-on:input="change">
<a :href="link">Gmail</a>
<table border="1" v-if="isvisible">
<tr>
<th>Name</th>
<th>Age</th>
<th>Rollno</th>
</tr>
<tr v-for="items in a">
<td>{{items.Name}}</td>
<td>{{items.age}}</td>
<td>{{items.Rollno}}</td>
</tr>
</table>
<button v-on:click="abc">click</button>
</div>
</template>
<script>
export default{
	data(){
	return{
name:"this is vuejs",
title:"instance",
msg:"hello world",
link:"http://www.gmail.com",
a:[{Name:"kamal",age:20,Rollno:24},
	{Name:"Sai",age:21,Rollno:21},
    {Name:"Raghu",age:22,Rollno:27}],
    isvisible:true  
 }
 },
 created(){
 this.hello()
 },
 methods:{
 change: function(event){
 this.msg=event.target.value
 },
 abc:function(){
 this.isvisible=!this.isvisible
 },
hello:function(){
	alert("welcome to vue js")
	},

}
}
</script>