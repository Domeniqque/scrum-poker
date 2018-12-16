<template>
  <div class="card">
    <p>{{ number }}</p>
  </div>
</template>

<script>
export default {
  name: 'card',
  props: ['number']
}
</script>

<style scoped>
.card {
  display: inline-block;
  box-shadow: 1px 3px 5px rgba(0,0,0,0.2);
  margin-left: 10px;
  display: flex;
  align-items: center;
  justify-content: center;
  border-radius: 5px;
  cursor: pointer;
}

.card::before {
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

.card:focus {
    outline: 0;
    color: var(--primary-color);
}

.card:focus::before {
  animation: click_effect 0.8s ease-out;
}

.card p {
  font-size: 4rem;
  margin: 40px 0;
  color: var(--primary-color);
  font-weight: 300;
}
</style>
