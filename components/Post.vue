<template>

        <div class="post">
        <p>{{id}}. {{name}}</p>
        </div>


</template>

<script>
export default {
  name:'Post',
  props:['id','name']
}
</script>

<style>
  .post{
    padding: 1rem;
    border: 1px solid whitesmoke;
    margin: 1rem 0;
  }

  .post:hover{
    background: #2d3436;
    border: 1px solid #6c5ce7;
    cursor:pointer
  }

  a{

  }
</style>
