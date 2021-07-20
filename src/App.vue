<template>
		<link href="https://fonts.googleapis.com/css2?family=Teko:wght@400;500&display=swap" rel="stylesheet">
    <link href="https://fonts.googleapis.com/css2?family=Russo+One&display=swap" rel="stylesheet">


    <header>
      <router-link to="/">
          <h1>
            <span>
              Stellar
            </span> Movies
          </h1>
      </router-link>
    </header>
  <main>
      <router-view/>
  </main>
</template>

<style lang="scss">
    *{
      margin:0;
      padding:0;
      box-sizing: border-box;
   
    &::selection{
      background: transparentize(#42B883, 0.5);
     }
    }
    .profile{
      padding: 1px 1.6px;
    }

    body{
      background-color: #333333;
    }
    a{
      text-decoration: none;
    }
    header {
      display: flex;
      align-items: center;
      justify-content: center;
      padding: 10px 16px;
      background-color: #0d0f36;
      box-shadow: 0px 0px 6px rgba(0,0,0,0.1);
      font-family: 'Teko', sans-serif;

      h1{
        color: #ffa500;
        font-size: 33px;
         font-family: 'Teko', sans-serif;
      
      span {
        color: #f08080;
      }
    }
  }
</style>