<template>
    <div class="[ card ]">
        <div class="[ row ]">
            <div class="[ col-sm-12 ]">
                <div class="[ card--information ]"><br />
        
                <b>Title: </b>{{title}}<br />
                <img :src="recipeImg" /><br />
                <b>Ingredients: </b>{{ingredients}}<br />
                <b>Recipe: </b><a href="href" target="_blank">Click Here</a><br />
                </div>

            </div>
        </div>
    </div>
</template>

<script>
export default {
    name: 'RecipeComponents',
    props: ['recipeImg','title','ingredients','href'],
}
</script>

<style scoped>
html {
    background-color: darkgrey;
}
.card{
    border: dotted 3px blue;
    border-radius: 4px;
    padding: 0px 20px 30px;
    margin: 30px 700px 0 700px;
    background-color: darkgrey;
    
}
.card img{
    width: 50%;
    padding-top: 25px;
}
</style>