<template>
  <div class="col-md-8">
    <h3 class="reply">评论回复：</h3>
    <h2 style='display: none'>暂无评论，点击左侧添加评论！！！</h2>
    <ul class="list-group">
        <Item v-for="(comment,index) in comments" :key="index" :comment="comment" :deleteComment="deleteComment" :index="index"/>
      <li class="list-group-item">
        <div class="handle">
          <a href="javascript:;">删除</a>
        </div>
        <p class="user"><span >yyy</span><span>说:</span></p>
        <p class="centence">Vue有点难!</p>
      </li>
    </ul>
  </div>
</template>

<script>
  import Item from './Item.vue'
  export default {
    //声明接收属性
    props:['comments','deleteComment'],//只是指定了属性名
    components:{
      Item
    }
  }
</script>

<style>
  .reply {
    margin-top: 0px;
  }


</style>
