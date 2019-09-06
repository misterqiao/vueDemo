<template>
    <div class="home">
        <div class="container">
            <h1 class="title">趣试衣</h1>
            <p class="lead"> 专注于线上教育, 用心做课程, 用心做服务! </p>
        </div>
        <div id="wrap">
			<ul id="main">
			</ul>

			<ul id="styleBtn">
				<li>Table</li>
				<li>Sphere</li>
				<li>Helix</li>
				<li>Grid</li>
			</ul>

			<div id="show">
				<div class="s-title">{{ demoArr.title }}</div>
				<div class="s-img">{{ demoArr.src }}</div>
				<div class="s-author">{{ demoArr.author }}</div>
				<div class="s-dec"></div>
			</div>
		</div>

		<div id="frame">
			<iframe src="" frameborder='0' width="100%" height="100%"></iframe>
			<div id="back">Back</div>
		</div>
    </div>
</template>

<script>
import $ from 'jquery'
import {a,b} from "../assets/js/index" 
import {e,f} from "../assets/js/jquery.mousewheel"
export default {
  name: 'home',
  data(){
    return {
      demoArr:[
        {title:'Js',author:'阿飞',date:'2016.03.03',kt:'阿飞老师我爱你',src:'demo/3D drag'},
				{title:'Js',author:'阿飞',date:'2016.03.03'},
				{title:'Js',author:'阿飞',date:'2016.03.03'},
				{title:'Js',author:'阿飞',date:'2016.03.03'},
				{title:'Js',author:'阿飞',date:'2016.03.03'},
				{title:'Js',author:'阿飞',date:'2016.03.03'},
				{title:'Js',author:'阿飞',date:'2016.03.03'},
				{title:'Js',author:'阿飞',date:'2016.03.03'},
				{title:'Js',author:'阿飞',date:'2016.03.03'},
				{title:'Js',author:'阿飞',date:'2016.03.03'},
				{title:'Js',author:'阿飞',date:'2016.03.03'},
      ]
    }
  },
  mounted:function(){
      a(),
      b(),
      e(),
      f()
  }
}
</script>


<style scoped>
.home {
  width: 100%;
  height: 100%;
  background: url(../assets/showcase.png) no-repeat;
  background-size: 100% 100%; 
}
 .container {
  width: 100%;
  height: 100%;
  box-sizing: border-box;
  padding-top: 100px;
  background-color: rgba(0, 0, 0, 0.7);
}
.title{
  font-size: 30px;
}
.lead {
  margin-top: 50px;
  font-size: 22px;
}
@import url("../assets/index.css");
</style> 