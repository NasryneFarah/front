<script>
export default {
  data() {
    return {
      email: "",
      password: "",
    };
  },

  methods: {
    async submit() {
      const res = await (
        await fetch(`${this.API_URL}login`, {
          method: "post",
          headers: {
            "Content-Type": "application/json", //je précise le type du contenu
          },
          body: JSON.stringify({
            //j'envoie les données sous format json
            email: this.email,
            password: this.password,
          }),
        })).json();

      if (res.status == 'Utilisateur connecté') {

        this.$router.push("/dashboard");// Redirection vers la page "/dashboard" après la connexion réussie
        
      } else {
        console.error(res.error);
      }
    },
  },
};
</script>

<template>
  <!-- Le html de mon formulaire de connexion -->
  <div class="container">
    <!-- mon formulaire de connexion -->
    <div class="login-box">
      <h2>Connexion</h2>
      <form action="#" @submit.prevent="submit()">
        <!-- input de l'email  -->
        <div class="input-box">
          <input v-model="email" type="email" required />
          <label>Email</label>
        </div>

        <!--  input du password -->
        <div class="input-box">
          <input v-model="password" type="password" required />
          <label>Mot de passe</label>
        </div>

        <button class="btn" type="submit">connexion</button>
      </form>
    </div>

    <span style="--i: 0"></span>
    <span style="--i: 1"></span>
    <span style="--i: 2"></span>
    <span style="--i: 3"></span>
    <span style="--i: 4"></span>
    <span style="--i: 5"></span>
    <span style="--i: 6"></span>
    <span style="--i: 7"></span>
    <span style="--i: 8"></span>
    <span style="--i: 9"></span>
    <span style="--i: 10"></span>
    <span style="--i: 11"></span>
    <span style="--i: 12"></span>
    <span style="--i: 13"></span>
    <span style="--i: 14"></span>
    <span style="--i: 15"></span>
    <span style="--i: 16"></span>
    <span style="--i: 17"></span>
    <span style="--i: 18"></span>
    <span style="--i: 19"></span>
    <span style="--i: 20"></span>
    <span style="--i: 21"></span>
    <span style="--i: 22"></span>
    <span style="--i: 23"></span>
    <span style="--i: 24"></span>
    <span style="--i: 25"></span>
    <span style="--i: 26"></span>
    <span style="--i: 27"></span>
    <span style="--i: 28"></span>
    <span style="--i: 29"></span>
    <span style="--i: 30"></span>
    <span style="--i: 31"></span>
    <span style="--i: 32"></span>
    <span style="--i: 33"></span>
    <span style="--i: 34"></span>
    <span style="--i: 35"></span>
    <span style="--i: 36"></span>
    <span style="--i: 37"></span>
    <span style="--i: 38"></span>
    <span style="--i: 39"></span>
    <span style="--i: 40"></span>
    <span style="--i: 41"></span>
    <span style="--i: 42"></span>
    <span style="--i: 43"></span>
    <span style="--i: 44"></span>
    <span style="--i: 45"></span>
    <span style="--i: 46"></span>
    <span style="--i: 47"></span>
    <span style="--i: 48"></span>
    <span style="--i: 49"></span>
  </div>
</template>

<style>
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
  font-family: "Nunito Sans", sans-serif;
}

body {
  display: flex;
  justify-content: center;
  align-items: center;
  min-height: 100vh;
  background: #f9ece4;
  /* background-image: url('img/currency.jpeg');
  background-position: center;        
  background-size: contain;
  background-repeat: no-repeat;
  backdrop-filter: blur(4.5px); */
}

.container {
  position: relative;
  width: 256px;
  height: 256px;
  display: flex;
  justify-content: center;
  align-items: center;
}

.container span {
  position: absolute;
  left: 0;
  width: 32px;
  height: 6px;
  background: #189aa7;
  border-radius: 8px;
  transform-origin: 128px;
  transform: scale(2.2) rotate(calc(var(--i) * (360deg / 50)));
  animation: animateBlink 3s linear infinite !important;
  animation-delay: calc(var(--i) * (3s / 50)) !important;
}

/* il me permettra de créer une animation sur les span */

@keyframes animateBlink {
  0% {
    background: rgb(251, 170, 130);
    background: linear-gradient(
      241deg,
      rgba(251, 170, 130, 1) 0%,
      rgba(115, 162, 172, 1) 100%
    );
  }

  25% {
    background: rgb(251, 170, 130);
    background: linear-gradient(
      241deg,
      rgba(251, 170, 130, 1) 0%,
      rgba(115, 162, 172, 1) 100%
    );
  }
}

/* Styles  pour le formulaire de connexion */
.login-box {
  position: absolute;
  width: 400px;
  /* background: black; */
  color: whitesmoke;
}

.login-box form {
  width: 100%;
  padding: 0 50px;
}

/* Autres styles pour les éléments du formulaire    */
.input-box {
  position: relative;
  margin: 25px 0;
}
/* #e45d0b */
h2 {
  font-size: 2em;
  color: #189aa7;
  font-weight: bold;
  text-align: center;
}

.input-box input {
  width: 100%;
  height: 50px;
  background: transparent;
  border: 2px solid #f8d6c0;
  outline: none;
  font-size: 1em !important;
  padding: 0 20px !important;
  border-radius: 40px;
  transition: 0.5s ease;
}

.input-box input:focus,
.input-box input:valid {
  top: 1px;
  font-size: 0.8em;
  padding: 0 6px;
  background: #f9ece4;
  border: 2px solid #189aa7;
  color: #189aa7;
}

.input-box label {
  position: absolute;
  top: 50%;
  left: 20px;
  transform: translateY(-50%);
  color: #21c4d3;
  font-weight: 900;
  pointer-events: none;
  transition: 0.5s ease;
}

.input-box input:focus ~ label,
.input-box input:valid ~ label {
  top: 1px;
  font-size: 0.8em;
  padding: 0 6px;
  background: #f9ece4;
  color: #189aa7;
}

.btn {
  width: 100%;
  height: 45px;
  background: #189aa7;
  border: none;
  outline: none;
  border-radius: 40px;
  cursor: pointer;
  font-size: 1.2em;
  color: #21c4d3;
  font-weight: bolder;
  transition: 0.8s ease;
}

.btn:hover {
  transition: all 0.5s ease-i;
  background: rgba(115, 162, 172, 1);
}
</style>
