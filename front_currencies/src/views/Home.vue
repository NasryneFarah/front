<script>
export default{
  data() {
        return {
            
        }
    },
}
</script>

<template>

<div class="wrapper">
      <header>Currency Converter</header>
      <form action="#">
        <div class="amount">
          <p>Entrer un nombre</p>
          <input type="number">
        </div>
        <div class="drop-list">
          <div class="from">
            <p>De</p>
            <div class="select-box">
              <!-- <img src="https://flagcdn.com/48x36/us.png" alt="flag"> -->
              <select></select>
            </div>
          </div>
          <div class="icon"><i class="fas fa-exchange-alt"></i></div>
          <div class="to">
            <p>A</p>
            <div class="select-box">
              <!-- <img src="https://flagcdn.com/48x36/np.png" alt="flag"> -->
              <select>  </select>
            </div>
          </div>
        </div>
        <div class="exchange-rate">Obtenir un taux de change...</div>
        <button>Conversion</button>
      </form>
    </div>

  
</template>

<style>

*{
    margin: 0;
    padding: 0;
    box-sizing: border-box;
    font-family: "Nunito Sans", sans-serif;
}

body{
  display: flex;
  align-items: center;
  justify-content: center;
  min-height: 100vh;
  padding: 0 10px;
  background: rgba(115, 162, 172, 1);
}

.wrapper{
  width: 370px;
  padding: 30px;
  border-radius: 7px;
  background-color: rgba(251, 170, 130, 1);
  box-shadow: 0px 0px 50px rgba(0, 0, 0, 0.5);
}
.wrapper header{
  color: #189aa7;
  font-size: 28px;
  font-weight: 500;
  text-align: center;
}
.wrapper form{
  margin: 40px 0 20px 0;
}
form :where(input, select, button){
  width: 100%;
  outline: none;
  border-radius: 5px;
  border: none;
}
form p{
    color: whitesmoke;
  font-size: 18px;
  margin-bottom: 5px;
}
form input{
  height: 50px;
  font-size: 17px;
  padding: 0 15px;
  background: #f9ece4;
  color:#189aa7;
  appearance: textfield;
}
form input:focus{
  padding: 0 14px;
  border: 2px solid rgba(115, 162, 172, 1);
}
form .drop-list{
  display: flex;
  margin-top: 20px;
  align-items: center;
  justify-content: space-between;
}
.drop-list .select-box{
  display: flex;
  width: 115px;
  height: 45px;
  align-items: center;
  border-radius: 5px;
  justify-content: center;
  border: 1px solid rgba(115, 162, 172, 1);
}
.select-box img{
  max-width: 21px;
}
.select-box select{
  width: auto;
  font-size: 16px;
  background: none;
  margin: 0 -5px 0 5px;
}
.select-box select::-webkit-scrollbar{
  width: 8px;
}
.select-box select::-webkit-scrollbar-track{
  background: #fff;
}
.select-box select::-webkit-scrollbar-thumb{
  /* background: #888; */
  border-radius: 8px;
  border-right: 2px solid #ffffff;
}
.drop-list .icon{
  cursor: pointer;
  margin-top: 30px;
  font-size: 22px;
}
form .exchange-rate{
  font-size: 17px;
  margin: 20px 0 30px;
  animation-duration: .8s;
   animation-name: clignoter;
   animation-iteration-count: infinite;
   transition: none;
  /* color: ; */
}
@keyframes clignoter {
  0%   { color:#000000; }
  40%   {color:#189aa7; }
  100% { opacity:#000000; }
}
form button{
  height: 52px;
  /* color: #fff; */
  font-size: 22px;
  cursor: pointer;
  background-color: rgba(115, 162, 172, 1);
  color: whitesmoke;
  font-weight: 600;
  transition: 0.3s ease;
}
form button:hover{
    background-color: rgb(62, 91, 97);
}



</style>
