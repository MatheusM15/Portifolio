<template>
  <div class="pt-5">
    <div class="d-flex">
        <div class="col-md-4">
            <div class="right-detalhe">
                <img id="img-detalhe" src="../assets/post_chat.png">
                <div id="title-project">
                    MENRI CHAT
                </div>
            </div>
        </div>
    </div>
  </div>
</template>

<script>
export default {
    name: 'ProjectInfo'
}
</script>

<style>
.right-detalhe{
    height: 75vh;
    background: white;
    border-radius: 10px;
    border: 10px solid blue;
}
#img-detalhe{
    width: 100%;
    height: 250px;
    object-fit: contain;
}
#title-project{
    height: 35px;
    display: flex;
    justify-content: center;
    align-items: center;
    color: white;
    font-weight: bold;
    background: blue;
}
</style>