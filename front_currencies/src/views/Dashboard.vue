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
        await fetch(`${this.API_URL}logout`, {
          method: "get",
          headers: {
            "Content-Type": "application/json", //je précise le type du contenu
          },
          body: JSON.stringify({
            //j'envoie les données sous format json
            email: this.email,
            password: this.password,
          }),
        })).json();

      if (res.status === 'Utilisateur déconnecté') {

        this.$router.push("/login");// Redirection vers la page "/login" après la connexion réussie
        
      } else {
        console.error(res.error);
      }
    },
  },
};
</script>

<template>
    <svg style="display:none;">
  <defs>

    <g id="home">
      <path fill="#90A4AE" d="M42,48H6c-3.3,0-6-2.7-6-6V6c0-3.3,2.7-6,6-6h36c3.3,0,6,2.7,6,6v36C48,45.3,45.3,48,42,48z"/>
      <path fill="#212121" d="M20.8,35.5v-9.6h6.4v9.6h8V22.7H40L24,8.3L8,22.7h4.8v12.8H20.8z"/>
    </g>

    <g id="search">
      <path fill="#90A4AE" d="M22.9,20.1h-1.5l-0.5-0.5c1.8-2.1,2.9-4.8,2.9-7.7C23.8,5.3,18.5,0,11.9,0S0,5.3,0,11.9s5.3,11.9,11.9,11.9
	    c3,0,5.7-1.1,7.7-2.9l0.5,0.5v1.4l9.1,9.1l2.7-2.7L22.9,20.1z M11.9,20.1c-4.5,0-8.2-3.7-8.2-8.2s3.7-8.2,8.2-8.2s8.2,3.7,8.2,8.2
	    S16.4,20.1,11.9,20.1z"/>
    </g>

    <g id="map">
      <path fill="#90A4AE" d="M16,14.2c-1,0-1.8,0.8-1.8,1.8s0.8,1.8,1.8,1.8c1,0,1.8-0.8,1.8-1.8S17,14.2,16,14.2z M16,0
	    C7.2,0,0,7.2,0,16c0,8.8,7.2,16,16,16s16-7.2,16-16C32,7.2,24.8,0,16,0z M19.5,19.5L6.4,25.6l6.1-13.1l13.1-6.1L19.5,19.5z"/>
    </g>

    <g id="planner">
      <path fill="#90A4AE" d="M28.4,3.6h-1.8V0h-3.6v3.6H8.9V0H5.3v3.6H3.6C1.6,3.6,0,5.1,0,7.1L0,32c0,2,1.6,3.6,3.6,3.6h24.9c2,0,3.6-1.6,3.6-3.6V7.1C32,5.1,30.4,3.6,28.4,3.6z M28.4,32H3.6V12.4h24.9V32z M7.1,16H16v8.9H7.1V16z"/>
    </g>

  </defs>
</svg>


<nav class="nav__cont">
  <ul class="nav">
    <li class="nav__items ">
        <svg xmlns="http://www.w3.org/2000/svg" height="1em" viewBox="0 0 576 512"><path d="M575.8 255.5c0 18-15 32.1-32 32.1h-32l.7 160.2c0 2.7-.2 5.4-.5 8.1V472c0 22.1-17.9 40-40 40H456c-1.1 0-2.2 0-3.3-.1c-1.4 .1-2.8 .1-4.2 .1H416 392c-22.1 0-40-17.9-40-40V448 384c0-17.7-14.3-32-32-32H256c-17.7 0-32 14.3-32 32v64 24c0 22.1-17.9 40-40 40H160 128.1c-1.5 0-3-.1-4.5-.2c-1.2 .1-2.4 .2-3.6 .2H104c-22.1 0-40-17.9-40-40V360c0-.9 0-1.9 .1-2.8V287.6H32c-18 0-32-14-32-32.1c0-9 3-17 10-24L266.4 8c7-7 15-8 22-8s15 2 21 7L564.8 231.5c8 7 12 15 11 24z"/>
            <use xlink:href="#home"></use>
        </svg>
      <a href="">Home</a>
    </li>
    
    <li class="nav__items ">
        <svg xmlns="http://www.w3.org/2000/svg" height="1em" viewBox="0 0 512 512">><path d="M64 32C28.7 32 0 60.7 0 96V416c0 35.3 28.7 64 64 64H448c35.3 0 64-28.7 64-64V192c0-35.3-28.7-64-64-64H80c-8.8 0-16-7.2-16-16s7.2-16 16-16H448c17.7 0 32-14.3 32-32s-14.3-32-32-32H64zM416 272a32 32 0 1 1 0 64 32 32 0 1 1 0-64z"/>
            <use xlink:href="#currency"></use>
        </svg>
      <a href="">Listes des monnaies</a>
    </li>
      
    <li class="nav__items ">
        <svg xmlns="http://www.w3.org/2000/svg" height="1em" viewBox="0 0 512 512">><path d="M512 80c0 18-14.3 34.6-38.4 48c-29.1 16.1-72.5 27.5-122.3 30.9c-3.7-1.8-7.4-3.5-11.3-5C300.6 137.4 248.2 128 192 128c-8.3 0-16.4 .2-24.5 .6l-1.1-.6C142.3 114.6 128 98 128 80c0-44.2 86-80 192-80S512 35.8 512 80zM160.7 161.1c10.2-.7 20.7-1.1 31.3-1.1c62.2 0 117.4 12.3 152.5 31.4C369.3 204.9 384 221.7 384 240c0 4-.7 7.9-2.1 11.7c-4.6 13.2-17 25.3-35 35.5c0 0 0 0 0 0c-.1 .1-.3 .1-.4 .2l0 0 0 0c-.3 .2-.6 .3-.9 .5c-35 19.4-90.8 32-153.6 32c-59.6 0-112.9-11.3-148.2-29.1c-1.9-.9-3.7-1.9-5.5-2.9C14.3 274.6 0 258 0 240c0-34.8 53.4-64.5 128-75.4c10.5-1.5 21.4-2.7 32.7-3.5zM416 240c0-21.9-10.6-39.9-24.1-53.4c28.3-4.4 54.2-11.4 76.2-20.5c16.3-6.8 31.5-15.2 43.9-25.5V176c0 19.3-16.5 37.1-43.8 50.9c-14.6 7.4-32.4 13.7-52.4 18.5c.1-1.8 .2-3.5 .2-5.3zm-32 96c0 18-14.3 34.6-38.4 48c-1.8 1-3.6 1.9-5.5 2.9C304.9 404.7 251.6 416 192 416c-62.8 0-118.6-12.6-153.6-32C14.3 370.6 0 354 0 336V300.6c12.5 10.3 27.6 18.7 43.9 25.5C83.4 342.6 135.8 352 192 352s108.6-9.4 148.1-25.9c7.8-3.2 15.3-6.9 22.4-10.9c6.1-3.4 11.8-7.2 17.2-11.2c1.5-1.1 2.9-2.3 4.3-3.4V304v5.7V336zm32 0V304 278.1c19-4.2 36.5-9.5 52.1-16c16.3-6.8 31.5-15.2 43.9-25.5V272c0 10.5-5 21-14.9 30.9c-16.3 16.3-45 29.7-81.3 38.4c.1-1.7 .2-3.5 .2-5.3zM192 448c56.2 0 108.6-9.4 148.1-25.9c16.3-6.8 31.5-15.2 43.9-25.5V432c0 44.2-86 80-192 80S0 476.2 0 432V396.6c12.5 10.3 27.6 18.7 43.9 25.5C83.4 438.6 135.8 448 192 448z"/>
            <use xlink:href="#paire"></use>
        </svg>
     <a href="">Listes des paires</a>
    </li>
      
    <li class="nav__items ">
        <svg xmlns="http://www.w3.org/2000/svg" height="1em" viewBox="0 0 512 512"><path d="M377.9 105.9L500.7 228.7c7.2 7.2 11.3 17.1 11.3 27.3s-4.1 20.1-11.3 27.3L377.9 406.1c-6.4 6.4-15 9.9-24 9.9c-18.7 0-33.9-15.2-33.9-33.9l0-62.1-128 0c-17.7 0-32-14.3-32-32l0-64c0-17.7 14.3-32 32-32l128 0 0-62.1c0-18.7 15.2-33.9 33.9-33.9c9 0 17.6 3.6 24 9.9zM160 96L96 96c-17.7 0-32 14.3-32 32l0 256c0 17.7 14.3 32 32 32l64 0c17.7 0 32 14.3 32 32s-14.3 32-32 32l-64 0c-53 0-96-43-96-96L0 128C0 75 43 32 96 32l64 0c17.7 0 32 14.3 32 32s-14.3 32-32 32z"/>
            <use xlink:href="#logout"></use>
        </svg>
      <a href="#/login" @click="submit()">logout</a>
    </li>
        
  </ul>
</nav>

  <div class="wrapper">
    <main>
      <h1>dashboard admin </h1>
    </main>
  </div>


</template>

<style>
*{
    font-family: 'Nunito Sans', sans-serif;
}
.nav__cont {
	 position: fixed;
	 width: 60px;
     left: 0;
	 top: 0;
	 height: 100vh;
	 z-index: 100;
	 background-color: #f9ece4;
	 overflow: hidden;
	 transition: width 0.3s ease;
	 cursor: pointer;
	 box-shadow: 4px 7px 10px rgba(0, 0, 0, .4);
}
 .nav__cont:hover {
	 width: 200px;
}
 @media screen and (min-width: 600px) {
	 .nav__cont {
		 width: 80px;
	}
}
 .nav {
	 list-style-type: none;
	 color: #21c4d3;
}
 .nav:first-child {
	 padding-top: 1.5rem;
}
 .nav__items {
	 padding-bottom: 4rem;
}
 .nav__items a {
	 position: relative;
	 display: block;
	 top: -35px;
	 padding-left: 25px;
	 padding-right: 15px;
	 transition: all 0.3s ease;
	 margin-left: 25px;
	 margin-right: 10px;
	 text-decoration: none;
	 color: #21c4d3;
	 font-family: 'roboto';
	 font-weight: 100;
	 font-size: 1.35em;
}
 .nav__items a:after {
	 content: '';
	 width: 100%;
	 height: 100%;
	 position: absolute;
	 top: 0;
	 left: 0;
	 border-radius: 2px;
	 background: linear-gradient(
      241deg,
      rgba(251, 170, 130, 1) 0%,
      rgba(115, 162, 172, 1) 100%
    );
	 opacity: 0;
	 transition: all 0.5s ease;
	 z-index: -10;
}
 .nav__items:hover a:after {
	 opacity: 1;
}
 .nav__items svg {
	 width: 26px;
	 height: 26px;
	 position: relative;
	 left: -25px;
	 cursor: pointer;
}
 @media screen and (min-width: 600px) {
	 .nav__items svg {
		 width: 32px;
		 height: 32px;
		 left: -15px;
	}
}
 body {
	 height: 100vh;
     background: #f9ece4;
	 /* background: radial-gradient(circle at 94.02% 88.03%, #54a4ff, transparent 100%), radial-gradient(circle at 25.99% 27.79%, #ff94fb, transparent 100%), radial-gradient(circle at 50% 50%, #000, #000 100%); */
}
 h1 {
	 margin-top: 2.2rem;
	 margin-left: 80px;
	 text-align: center;
	 font-family: 'Roboto';
	 font-weight: 100;
	 font-size: 4rem;
	 text-transform: uppercase;
	 color:  rgba(115, 162, 172, 1);
	 letter-spacing: 6px;
	 text-shadow: 10px 10px 10px rgba(0, 0, 0, .3);
}
 
</style>