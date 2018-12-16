<template>
  <div class="card">
    <p>{{ selected }}</p>
    <button @click="$emit('close')">Voltar</button>
  </div>
</template>

<script>
export default {
  name: 'show-card',
  props: ['selected']
}
</script>

<style scoped>
.card {
  position: fixed;
  display: flex;
  align-items: center;
  justify-content: center;
  flex-direction: column;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background-color: #fff;
  margin: 0;
  opacity: 1;
  animation: fade 0.3s;
}

.card p {
  font-size: 14rem;
  color: var(--primary-color);
  font-weight: 300;
  margin: auto 0 0 0;
}

.card button {
  display: block;
  position: relative;
  align-self: flex-end;
  margin: auto;
  border: 1px solid var(--primary-color);
  background-color: #fff;
  color: var(--primary-color);
  border-radius: 50%;
  font-weight: 300;
  font-size: 1rem;
  width: 78px;
  height: 78px;
  cursor: pointer;
  transition: all 0.4s ease-in;
}

button::before {
  content: '';
  background-color: var(--primary-color);
  border-radius: 50%;
  display: block;
  position: absolute;
  top: 0;
  right: 0;
  bottom: 0;
  left: 0;
  transform: scale(0.001, 0.001);
}

button:focus {
    outline: 0;
    color: var(--primary-color);
}

button:focus::before {
  animation: click_effect 0.8s ease-out;
}

@keyframes fade {
  from { opacity: 0 }
  to { opacity: 1 }
}
</style>
