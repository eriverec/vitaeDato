<template>
  <div>
    <div class="center">
      <section>
        <div class="hola">Hola</div>
      </section>
      <div class="center__soy">Soy <strong>Eri Vera</strong></div>
      <section>
        <div class="cargo">Developer Web</div>
      </section>
    </div>
  </div>
</template>

<style scoped>
.center__soy {
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
