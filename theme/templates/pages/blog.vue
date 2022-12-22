<template>
    <div>Blogs</div>    
</template>

<script>
export default  {
    props:["context"],
    watch: {
    context: function() {
      console.log("brandsss++++++++++++++++++", this.context);
    }
}
}
</script>

