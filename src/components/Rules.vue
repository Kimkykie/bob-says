<template>
<div class="rules">
    <h3>RULES</h3>
    <ul>
        <li v-for="rule in rules">{{ rule }}</li>
    </ul>
</div>
</template>

<script>
export default {
    data() {
        return {
            rules: ['Bob is a lackadaisical teenager. In conversation, his responses are very limited.',
                'Bob answers \'Sure.\' if you ask him a question.',
                'He answers \'Whoa, chill out!\' if you yell at him.',
                'He says \'Fine. Be that way!\' if you address him without actually saying anything.',
                'He answers \'Whatever.\' to anything else.'
            ]
        }
    }
}
</script>

<style>
.rules{
    margin-top: 20px;
}

.rules li {
    font-size: 14px;
    font-family: 'Josefin Sans', sans-serif;
}

.rules h3 {
    font-family: 'Architects Daughter', cursive;
    text-align: center;
    text-decoration: underline;
    font-size: 24px;
    color: goldenrod;
}
</style>
