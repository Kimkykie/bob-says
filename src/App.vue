<template>
<div id="app">
    <div id="main">
        <h1>BOB SAYS</h1>
        <BobInput></BobInput>
        <Rules></Rules>
    </div>
</div>
</template>

<script>
import BobInput from './components/BobInput.vue';
import Rules from './components/Rules.vue';
export default {
    name: 'app',
    components: {
        BobInput,
        Rules
    }
}
</script>

<style>
@import url('https://fonts.googleapis.com/css?family=Architects+Daughter|Josefin+Sans|Kalam|VT323');

body {
    margin: 0;
    padding: 0;
    background: url('./assets/bob.jpg') rgb(241, 231, 139);
    background-repeat: no-repeat;
    background-size: cover;
}

#app {
    font-family: 'Avenir', Helvetica, Arial, sans-serif;
    color: #2c3e50;
    max-width: 1000px;
    margin: 0 auto;
    margin-top: 5%;
}

#main{
    padding: 10px 20px 80px 20px;
    background: white;
    border: 8px solid goldenrod;
}

h1,
h2 {
    font-family: 'Architects Daughter', cursive;
    font-size: 40px;
    font-weight: normal;
    color: goldenrod;
    text-align: center;
}
</style>
