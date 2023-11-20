<template>
  <header>
    <div id="logo">
      <a href="/">
        <span class="bloc">Portfolio</span>
      </a>
    </div>
  </header>
</template>

<style scoped>
header {
  display: flex;
  margin-bottom: 30px;
}

#logo {
  display: flex;
}

span,
a {
  padding-top: 25px;
  margin: auto;
  width: 100%;
  text-decoration: none;
  color: #000000;
  
}

#logo:hover:before {
  border-top: 2px solid #bda67e;
  border-left: 2px solid #bda67e;
  top: 0;
  content: "";
  width: 15px;
  height: 14px;
  transform: scale(1);
  transition: 0.3s ease-in-out;
}

#logo:hover span:after {
  display: flex;
  border-bottom: 2px solid #bda67e;
  border-right: 2px solid #bda67e;
  right: 0;
  bottom: 0;
  content: "";
  width: 15px;
  height: 14px;
  margin-left: 60px;
  margin-top: 4px;
  transform: scale(1);
  transition: 0.4s ease-in-out;
}

span {
  font-family: "Dancing Script", cursive;
}
</style>
