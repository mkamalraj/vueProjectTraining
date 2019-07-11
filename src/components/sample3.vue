<template>
<div>
<div>
<hr>
<h1 :style="example">{{names}}</h1>
<p>hello</p>
<p v-if="isvisible">{{age}}</p>
<p v-else-if="isdisable">{{age2}}</p>
<h1 v-else>{{content}}</h1>
<p v-show ="abc">{{content2}}</p>
<h1>kamal</h1>
</div>
<div>
<ul v-if="disable">
<li v-for="value in  fruits">{{value.fruit}}</li>
</ul>
<button v-on:click="submit">button</button>
</div>
<div :style="box">
</div>
</div>
</template>
<script>
export default{
	data(){
	return{
	names:"hello world123!",
     age:21,
     age2:22,
     content:"This is a header",
     content2:"hii",
     isvisible:false,
     isdisable:false,
     abc:true,
     disable:true,
     fruits:[{fruit:"apple",price:"$7",place:"US"},
              {fruit:"orange",price:"$7",place:"US"}],
     example:{
     color:'red',
     background:'grey',
     margin:'25px'
     },
     ul_style:{
     color:'navy',
     background:'purple'
     },
     li_style:{
     padding:'10px',
     color:'red'
     },
     box:{
     height:'100px',
     width:'100px',
     border:'2px solid green',
     background:'red',
     margin:'20px'
     }
}
},
methods:{
     submit: function(){
     this.disable=!this.disable;
     },
}
}
</script>