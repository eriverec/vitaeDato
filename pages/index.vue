<template>
  <div>
    <div class="center">
      <section>
        <div class="hola">Hola</div>
      </section>
      <p>Yo soy <strong>Eri Vera</strong></p>
      <section>
        <div class="cargo">Developer Web</div>
      </section>
    </div>
  </div>
</template>

<style scoped>
p {
  margin: 16px;
  font-size: 50px;
  color: #333;
  text-transform: uppercase;
  transition: all 1s ease-in-out;
  position: relative;
}

.cargo {
  text-transform: uppercase;
  transition: all 1s ease-in-out;
  font-size: 20px;
}

.hola {
  border-radius: 4px;
  display: inline;
  padding: 4px;
  background-color: #2ecfa8;
  color: white;
}

.center {
  position: absolute;
  left: 50%;
  top: 50%;
  text-align: center;
  transform: translate(-50%, -50%);
  -webkit-transform: translate(-50%, -50%);
}
</style>

<script>
export default {};
</script>
