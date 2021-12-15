<template>
    <div class="container">
      <div class="jumboton">
        <span v-decorar:grande.italico.negrilla="{familia: 'helvetica', color: 'red'}">Aprende Vue.js 2 Facil</span>
        <hr>
         <span v-decorar-local:pequeno.italico.negrilla="{familia: 'serif', color: 'blue'}">Aprende Angular 2 Facil</span>
      </div>
    </div>
</template>

<script>
export default {
  directives: {
    'decorar-local' : {
      bind(el, binding, vnode){

      el.style.fontFamily = binding.value.familia;
      el.style.color = binding.value.color;

      if(binding.arg == 'grande'){
        el.style.fontSize = '50px';
      }
      if(binding.arg == 'pequeno'){
        el.style.fontSize = '10px';
      }
      if(binding.modifiers['negrilla']){
        el.style.fontWeight = 'bold';
      } if(binding.modifiers['italico']){
        el.style.fontStyle = 'italic'
      }
    }
    }
  }

}
</script>

<style>

</style>
