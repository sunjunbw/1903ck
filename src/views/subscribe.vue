 <template>
<div>
  
    <mt-switch v-model="value"></mt-switch>
   
    <mt-navbar class="page-part" v-model="selected">
  <mt-tab-item id="1">选项一</mt-tab-item>
  <mt-tab-item id="2">选项二</mt-tab-item>
  <mt-tab-item id="3">选项三</mt-tab-item>
</mt-navbar>

<!-- tab-container -->
<mt-tab-container v-model="selected">
  <mt-tab-container-item id="1">
    <mt-cell v-for="n in 10" :title="'内容 ' + n"></mt-cell>
  </mt-tab-container-item>
  <mt-tab-container-item id="2">
    <mt-cell v-for="n in 4" :title="'测试 ' + n"></mt-cell>
  </mt-tab-container-item>
  <mt-tab-container-item id="3">
    <mt-cell v-for="n in 6" :title="'选项 ' + n"></mt-cell>
  </mt-tab-container-item>
</mt-tab-container>
 
  </div>


 </template>

 <script>
 import { Navbar, TabItem } from 'mint-ui';
 export default {
 	data(){
 		return {
 			active:'tab-container1',
 			value:true,
 			selected:"1"
 		}
 	}
 }
 </script>
 
