<template>
 <p>{{ game.home_team }} vs {{game.away_team}}</p>   
</template>

<script>
export default {
    name: "GamesItem",
    props: ["game"]
}
</script>

<style>

</style>