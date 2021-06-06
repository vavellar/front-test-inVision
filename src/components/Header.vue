<template>
<div class="body">
    <div class="header">
        <div class="menu">
            <p class="title">sacola</p>
            <p class="title">pagamento</p>
            <p class="title">confirmação</p>
        </div>
    </div>
 </div>
    
</template>

<script>
export default {

}
</script>

<style>

.header {
    display: flex;
    background-color: white;
	box-shadow: 2px 2px 2px #D7D7DA
        
}

.menu {
    display: flex;
    justify-content: space-between;
    width: 100%;
    margin-left: 10px;
    margin-right: 10px;
    
    
}

.title {
    text-transform: uppercase;
    color: #CCCCCC;
    font-weight: 700;
    font-size: 16px
}

</style>