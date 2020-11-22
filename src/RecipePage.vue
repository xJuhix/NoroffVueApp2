<template>
    <div>
        <h1>Recipes Puppy</h1>
    <div class="[ row ]">
        <div v-for="recipe in recipes" v-bind:key="recipe" class="[ col-sm-12 ]">
            <RecipeComponent    v-bind:recipeImg="recipe.thumbnail"
                                v-bind:title="recipe.title"
                                v-bind:ingredients="recipe.ingredients"
                                v-bind:href="recipe.href">
            </RecipeComponent>
        </div>
    </div>
    </div>
</template>

<script>
import RecipeComponent from './components/RecipeComponent.vue'
export default {
    name: 'RecipesPage',
    components: {
        RecipeComponent
    },
    data(){
        return{
            recipes: []
        }
    },
    beforeMount: function(){
    const app = this;
    const conversionUrl = 'https://cors-anywhere.herokuapp.com/';
    const url = 'http://www.recipepuppy.com/api/';
        fetch(conversionUrl + url)
        .then(function(response) {
            return response.json();
        })
        .then(function(result) {
            app.recipies = result.results;
        })
    }
}
</script>