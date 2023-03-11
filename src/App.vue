<template>
  <!-- ================================================== -->
  <input type="text" v-model="firstName" @input.prevent="updateFirstName">
  <label>
    <input type="checkbox" v-model="isPurple" /> Purple
  </label>
  <input type="number" v-model="size">
  <select v-model="selectedColor">
    <option value="">White</option>
    <option value="text-black">Black</option>
    <option value="text-orange">Orange</option>
  </select>
  <div class="circle" :style="[{
    width: size + 'px', height: size + 'px', lineHeight: size + 'px'
  }, { transform: 'rotate(-50deg)' }]
  " :class="[selectedColor, circle_classes]">
    Hi!
  </div>
  <!-- ================================================== -->
  <select v-model="mode">
    <option value="">V-if</option>
    <option value="2">v-else-if</option>
    <option value="3">v-else</option>
  </select>
  <p v-if="mode == 1">V-if show content</p>
  <!-- It is better to keep elements structure (use template) -->
  <template v-else>
    <h3>Bonus Content</h3>
    <p>HEY I AM JUST HERE TOO</p>
  </template>
  <!-- Alternative for v-if: v-show -->
  <ul>
    <li v-for="(bird, index) in birds" :key="index" :class="bird">
      {{ bird }} - {{ index }}
    </li>
  </ul>
  <hr />
  <ul>
    <li v-for="(key, value, pid) in people" :key="pid">
      <div>{{ key }} : {{ value }} - Index {{ pid }}</div>
    </li>
  </ul>
</template>

<script>
export default {
  name: 'App',
  data() {
    return {
      birds: ['Pigeons', 'Eagles', 'Doves', 'Parrots'],
      people: [
        { name: 'John', age: 20 },
        { name: 'Rick', age: 18 },
        { name: 'Amy', age: 33 }
      ],
      mode: 2,
      firstName: "Honorine",
      isPurple: false,
      selectedColor: '',
      size: 150
    }
  },
  methods: {
    updateFirstName(event) {
      this.firstName = event.target.value
    }
  },
  // Return methods as necessary only when the properties in computed are updated
  computed: {
    circle_classes() {
      return { purple: this.isPurple };
    }
  }
}
</script>

<style>
body {
  font-size: 20px;
  font-family: sans-serif;
}

label {
  margin-bottom: 20px;
  font-size: 20px;
  display: block;
}

select {
  font-size: 20px;
  margin-bottom: 20px;
}

input[type=number] {
  display: block;
  font-size: 20px;
  margin-bottom: 20px;
}

.circle {
  width: 150px;
  height: 150px;
  border-radius: 100%;
  background-color: #45D619;
  text-align: center;
  color: #fff;
  line-height: 150px;
  font-size: 32px;
  font-weight: bold;
}

.purple {
  background-color: #767DEA;
}

.text-black {
  color: #424242;
}

.text-orange {
  color: #FFC26F;
}
</style>
