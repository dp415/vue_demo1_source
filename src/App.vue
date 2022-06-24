<!-- Parent Page -->
<!-- Demo Template -->

<script setup>
/**/
import { reactive, ref} from 'vue'
//import satements for children
import demo1 from './demo1-declarativeRendering.vue'
import demo2 from './demo2-attributeBindings.vue'
import demo3 from './demo3-eventListeners.vue'
import demo4 from './demo4-FormBindings.vue'
import demo5 from './demo5-conditionalRendering.vue'
import demo6 from './demo6-list_rendering.vue'
import demo7 from './demo7-computed_property.vue'
import demo8 from './demo8-lifecycle_and_template_refs.vue'
import demo9 from './demo9-watchers.vue'
import demo10 from './demo10-Components.vue'
import demo11 from './demo11-props.vue'
import demo12 from './demo12-emits.vue'
import demo13 from './demo13-slots.vue'

demo3.name="demo3"
demo4.name="demo4"
demo5.name="demo5"
demo6.name="demo6"
demo7.name="demo7"
demo9.name="demo9"

//let demoHold=reactive({page:demo1});

//const display=reactive([demo1,demo2])

const currentTab=ref('demo1')

const tabs = {
	demo1,demo2,demo3,demo4,demo5,demo6,demo7,demo8,demo9,demo10,demo11,demo12,demo13
}
/**
let demo_id=0;
const demos=ref([
	{id:demo_id++,text:'Index',url:'demo'+demo_id},
	{id:demo_id++,text:'Demo 1',url:'demo'+demo_id},
	{id:demo_id++,text:'Demo 2',url:'demo'+demo_id},
	{id:demo_id++,text:'Demo 3',url:'demo'+demo_id},
	{id:demo_id++,text:'Demo 4',url:'demo'+demo_id},
	{id:demo_id++,text:'Demo 5',url:'demo'+demo_id},
	{id:demo_id++,text:'Demo 6',url:'demo'+demo_id},
	{id:demo_id++,text:'Demo 7',url:'demo'+demo_id},
	{id:demo_id++,text:'Demo 8',url:'demo'+demo_id},
	{id:demo_id++,text:'Demo 9',url:'demo'+demo_id},
	{id:demo_id++,text:'Demo 10',url:'demo'+demo_id},
	{id:demo_id++,text:'Demo 11',url:'demo'+demo_id},
	{id:demo_id++,text:'Demo 12',url:'demo'+demo_id},
	{id:demo_id++,text:'Demo 13',url:'demo'+demo_id}
])
/**/
//const counter = reactive({count: 0})
/**/

function changePage(){
	if(demoHold.page!=demo2)
		demoHold.page=demo2
	else if(demoHold.page!=demo1)
		demoHold.page=demo1
	alert(demoHold.page==demo1);
}
</script>

<script>
// finished options example //

</script>

<template>
	<h1>Vue Demo Projects</h1>
	<div id="topMenu">
		<ul id="navBar">
			<li v-for="(_,tab) in tabs" :key="tab" :class="['tab-button', {active: currentTab===tab}]" @click="currentTab=tab">{{tab}}</li>
			<!-- <li v-for="demo in demos" :key="demo.id" @mouseover="changePage();"><a href=demo.url>{{demo.text}}</a></li> -->
		</ul>
	</div>
		<Transition>
			<KeepAlive :include="/demo[345679]/">
				<component :is="tabs[currentTab]" class="tab" />
			</KeepAlive>
		</Transition>
</template>
<!-- options outline -->
  <style>
	  body{
		  background-color: #262626;
		  color: white;
	  }
	  #navBar{
		  list-style-type: none;
		  overflow: hidden;
		  background-color: #333333;
		  padding: 0;
		  margin: 0;
		  width: 100%;
	  }
	  #navBar li {
		  float: left;
		  display: block;
		  padding: 16px;
		  cursor: pointer;
		  font-weight: bold;
	  }
	  #navBar li:hover{
		  background-color: darkgrey;
		  color:black;
	  }
	  
	  .tab-button.active {
	    background: #e0e0e0;
		color:black;
	  }
  </style>