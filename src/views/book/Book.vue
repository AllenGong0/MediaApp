<template>
  <div class="book">
    <swipe class="my-swipe">
      <swipe-item class="item1"></swipe-item>
      <swipe-item class="item2"></swipe-item>
      <swipe-item class="item3"></swipe-item>
    </swipe>
  </div>
</template>
<script>
    import { Swipe, SwipeItem } from 'vue-swipe';
    import Axios from 'axios';
    export default{

        components: {
            'swipe': Swipe,
            'swipe-item': SwipeItem
        },
        created(){
          this.getData();
        },
        methods:{
          getData() {
            Axios.post('https://bird.ioliu.cn/v1?url=https://api.douban.com/v2/book')
                    .then((res) => {
                     console.log(res);
                    });

            // Axios.get('/movie.json')
            // .then((res)=>{
            //     var arr = res.data.subjects.slice(this.movieList.length,this.movieList.length+5);
            //     this.movieList = [...this.movieList,...arr];
            //     console.log(this.movieList);
            //         this.isShow = false;
            //         if(arr.length < 5){
            //             this.isEnd = true;
            //         }
            // });
          }
        }

  }
</script>
<style>
  .book{
    height: 200px;
  }

  .my-swipe {
    height: 200px;
    color: #fff;
    font-size: 30px;
    text-align: center;
  }

  .item1 {
    background: url('/img/1.jpg') no-repeat center;
    background-size:contain;
    color: #fff;
  }

  .item2 {
    background: url('/img/3.jpg') no-repeat center;
    background-size:contain;
    color: #000;
  }

  .item3 {
    background: url('/img/2.jpg') no-repeat center;
    background-size:contain;
    color: #fff;
  }

</style>
