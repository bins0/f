<template>
  <div class="page">
    <h3 >{{$route.params.page}}페이지입니다</h3>
    <p>{{data.board[($route.params.page)-1].memo}}</p>
  </div>
</template>

<script>
import data from '@/assets/data.json'
export default {
  name: 'PageComponent',
  data : function () {
    return {
      data :data
    }
  }
}
</script>