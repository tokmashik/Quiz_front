<template>
  <div class="header open" id="header">
  <div class="navbar">
    <div class="navblackbar">
     
      <button class="header__burgerbtn" id="burger">
        <span></span><span></span><span></span>
      </button>
    <div @click="$router.push('/')" class="mainlogo">Q</div>
    <div class="navbar__btns ">
      <nav-button @click="$router.push('/quizzes')">Quizzes</nav-button>
      <nav-button @click="$router.push('/quizgame')">Quiz Game</nav-button>
      <!--<nav-button style="margin-left: 20px" @click="$router.push('/store')">store</nav-button>-->
      <nav-button @click="$router.push('/consructor')">Constructor</nav-button>
      <button @click="$router.push('/authorization')" class="LogInBtn">Sing in</button>  
    </div>
  </div>
  </div></div>
</template>

<script defer>
document.addEventListener("DOMContentLoaded", function(){
  document.getElementById("burger").addEventListener("click", function(){
    document.getElementById("header").classList.toggle("open")
  })
})
</script>

<style>
.navbar {
  width: 100%;
  display: flex;
  font-weight: 300;
  background-color: #EAEAEA;
}

.navblackbar {
  width: 80%;
  display: flex;
  background-color: #1B1B1B;
  margin-top: 55px;
  margin-left: 10%;
  border-radius: 70px;
  height: 80px;
  justify-content: space-between;
  box-shadow: 0px 8px 20px rgba(0, 0, 0, 0.5);
}

.mainlogo {  
  align-items: center;
  font-family: 'StretchPro';
  cursor: pointer; 
  font-size: 36px;
  color: #ffffff;
  margin-left: 35px;
  margin-top: 14px;
  margin-bottom: 22px;
}

.navbar__btns {
  margin-top: 21px;
  margin-right: 21px;
  margin-bottom: 30px;
  align-items: center;
  display: inline-block;
}

.LogInBtn {
  background: #FFFFFF;
  border-radius: 30px;
  width: 165px;
  height: 38px;
  cursor: pointer; 
  border: 0px;
  font-size: 20px;
  color:#1B1B1B;
  font-family: 'StretchPro';
}

</style>

