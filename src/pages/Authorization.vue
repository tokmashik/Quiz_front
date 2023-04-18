<template>
<div class="autoriz_wr">
    <div class="autoriz_block">
        <div @click="$router.push('/')" class="mainlogo">Q</div>
        <div class="Sing__in">
            <h3>Sing in</h3> 
            <h4>Continue with 
                <a href="Google"></a> Google or VK</h4>
            <div class="inputs_auth_reg">
                <h4>Email</h4>
                <my-input class=""
                placeholder="">
                </my-input>
                <h4>Password</h4>
                <button class="hide_password"></button>
                <my-input class=""
                placeholder="">
                </my-input>
                <my-button style="align-self: flex-end; margin-top: 15px">
                   Sing in
                </my-button>
            </div>
        </div>
    </div>

</div>
  </template>
  
  <script >

  </script>
  
  <style>
.autoriz_wr {
    width: 76%;
    margin: 0 auto;
    justify-content: center;
}

.autoriz_block {
    justify-content: center;
    margin-top: 3%;
    box-sizing: border-box;

    z-index: 2;
    width: 1082px;
    height: 984px;

    background: rgba(0, 0, 0, 0.14);
    box-shadow: 10px 10px 30px rgba(0, 0, 0, 0.25);
    backdrop-filter: blur(25px);
    /* Note: backdrop-filter has minimal browser support */

    border-radius: 20px;
}

.Sing__in {
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    padding: 0px;
    gap: 16px;

    color: #fff;
}

.inputs_auth_reg {
    display: flex;
    flex-direction: column;
    align-items: flex-start;
    padding: 0px;
    gap: 4px;
}

.hide_password {

}
  </style>