<template>
    <div class="slide3">
    </div>
</template>

<script>
export default{
    props: ['visibleSlide', 'index'],
    data() {
        return {
            
        }
    }
}

</script>

<style>
.slide3 {
  display: flex;  
  flex-flow: row wrap;
  font-weight: bold;
  text-align: left; 
  border-radius: 10px;
  width: 620px;
  height: 370px;
}

.slide3 > * {
  padding: 1px;
  flex: 1 100%;
  
}
.cabecalho {
  background: black;
  color: white;
  font-size: 2.1em;
}
.subt1 {
    background: black;
  color: white;
  font-size: 1.8em;
}
.texto {
    background: black;
  color: white;
  padding: 5px;
  font-size: 1.5em;
}
   
@media all and (min-width: 600px) {
  .aside { flex: 1 0 0; }
}

@media all and (min-width: 800px) {
  .texto    { flex: 3 0px; }
  .subt1 { order: 1; } 
  .texto    { order: 2; }
}

body {
  padding: 2em; 
}

</style>