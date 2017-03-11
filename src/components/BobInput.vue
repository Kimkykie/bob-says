<template>
<div id="bob-div">
    <div id="input-div">
        <input type="text" id="bob-input" placeholder="Have a conversation with Bob" v-on:keyup.enter="hey()">
    </div>

    <div class="answer-div">
        <p>Bob Answer: <span id="bob-answer">{{ answer }}</span></p>
    </div>
</div>
</template>

<script>
export default {
    name: 'input-div',
    data() {
        return {
            statement: '',
            answer: ''
        }
    },
    methods: {

        isQuestion: function(statement) {
            this.statement = document.getElementById('bob-input').value;
            return this.statement.slice(-1) === '?';
        },

        isYelling: function(statement) {
            this.statement = document.getElementById('bob-input').value;
            return this.statement.toUpperCase() === this.statement && this.statement.match(/[A-Z]/);

        },

        isSilent: function(statement) {
            this.statement = document.getElementById('bob-input').value;
            return /^\s*$/.test(this.statement);
        },

        hey: function(statement) {
            this.answer = document.getElementById('bob-answer').textContent;
            if (this.isSilent(statement)) {
                this.answer = '\"Fine. Be that way!\"';
            } else if (this.isYelling(statement)) {
                this.answer = '\"Whoa, chill out!\"';
            } else if (this.isQuestion(statement)) {
                this.answer = '\"Sure.\"';
            } else {
                this.answer = '\"Whatever.\"';
            }
            document.getElementById('bob-input').addEventListener('blur', function() {
                this.value = '';
            });
        }
    }
}
</script>

<style>
#input-div{
    text-align: center;
}
#bob-input,
input[type="text"]:focus {
    width: 80%;
    line-height: 38px;
    border-top: 1px solid white;
    border-left: 1px solid white;
    border-right: 1px solid white;
    border-bottom: 2px solid goldenrod;
    outline: 0;
    font-size: 16px;
    font-family: 'Josefin Sans', sans-serif;
}

.answer-div p{
  font-size: 20px;
  font-family: 'Kalam', cursive;
}

#bob-answer{
  margin-left: 2%;
  font-size: 20px;
  font-family: 'Kalam', cursive;
  color: goldenrod;
}
</style>
