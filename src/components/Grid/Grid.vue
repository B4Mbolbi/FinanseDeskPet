<script setup>

</script>

<template>
<div class="Wrapper flex flex-row justify-center items-center">
    <div class="Settings">
      <div class="Profile">
        <slot name="profile"></slot>
      </div>
      <div class="AddDesk">
        <slot name="Adddesk"></slot>
      </div>
    </div>
  <div class="DeskAnalys flex flex-col justify-center items-center">
    <div class="Desk">
      <slot name="desk"></slot>
    </div>
    <div class="Analys">

    </div>
  </div>

<!--    <div class="Content gap-3.5 flex flex-row w-[100%]">-->
<!--      <div class="Settings">-->
<!--        <div class="Profile gap-3.5">-->
<!--          <slot name="profile"></slot>-->
<!--        </div>-->
<!--        <div class="AddDesk gap-3.5">-->
<!--          <slot name="Adddesk"></slot>-->
<!--        </div>-->
<!--      </div>-->
<!--      <div class="Desk w-[100%]">-->
<!--        <div class="Desk gap-3.5">-->
<!--          <slot name="desk"></slot>-->
<!--        </div>-->
<!--      </div>-->
<!--      <div class="Setting gap-3.5">-->
<!--      </div>-->
<!--    </div>-->


</div>
</template>

<style scoped>
*{
  margin: 0;
  padding: 0;
  font-family: "Arial Black", Gadget, sans-serif;
  color: black;
  //border: 2px solid black;

}
.Wrapper{
  width: 100%;
  height: 100vh;
  background:linear-gradient(20deg,black,peru);
  display: flex;
  justify-content: start;
  align-items: center;
}
.Settings{
  width: 30%;
  height: 100%;
  min-width: 30%;
  gap: 5px;
  display: flex;
  flex-direction: column;
  justify-content: start;
  align-items: center;
  padding: 2px;
}
.Settings .Profile{
  width: 100%;
  height: 15%;
  min-height: 15%;
}
.Settings .AddDesk {
  width: 100%;
  height: 90%;
  background: peru;
  border-radius: 20px;
}
.Desk{
  width: 100%;
  height: 70%;
  max-height: 70%;
  min-height: 70%;
  gap: 5px;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  padding: 2px;
  //background: peru;
  border-radius: 20px;
}
.Analys{
  width: 100%;
  height: 70%;
  gap: 5px;
  display: flex;
  flex-direction: column;
  //background: peru;
  border-radius: 20px;
}
.DeskAnalys{
  width: 100%;
  height: 100%;
  gap: 3px;
  padding: 2px;
}


</style>