<template>
    <div class="nav">
        <NuxtLink class="nav-item" to="/">Strona domowa</NuxtLink>
        <NuxtLink class="nav-item" to="/onas">O nas</NuxtLink>
    </div>
</template>
<script>
export default {
  name: 'NavTop',
}
</script>
<style scoped>
.nav{
    flex-wrap: wrap;
    background-color: rgb(0, 0, 0);
    display: flex;
    border:1px solid rgb(0, 0, 0);
    height: 100%;
    width: 100%;
    max-height:50px;
    min-height:50px;
    max-width:100vw;
    min-width: 200px;

}
.item{
    max-height:100px;
    min-height:100px;
    max-width:100px;
    min-width: 100px;
    border:solid blue;
}
.item2{
    flex-direction: column;
    display: flex;
}
.left-nav{
    font-size: 14px;
    max-height:100px;
    min-height:100px;
    max-width:50px;
    min-width: 100px;
}
.nav-item {
    padding: 15px 5px 10px 5px;
    color: white;
    text-decoration: none;
    margin-left: 5px;

}
.nav-item:hover {
    color: rgb(101, 21, 101)
}

</style>
