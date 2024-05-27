<template>
  <div class="header">
    Tugas4 PBK
  </div>
  <div id="wrapper">
    <h1>Sushi</h1>
    <div class="card" v-for="x in Sushi" :key="x.name">
      <Makanan
        :Makanan-name="x.name"
        :Makanan-desc="x.desc"
        :is-favorite="x.favorite" 
        @toggle-favorite="receiveEmit" />
    </div>
    <br>
    <h1>Minuman</h1>
    <div class="card" v-for="x in Minuman" :key="x.name">
      <Minuman
        :Minuman-name="x.name"
        :Minuman-desc="x.desc"
        :is-favorite="x.favorite" 
        @toggle-favorite="receiveEmit" />
    </div>
    <br>
    <h1>Snack</h1>
    <div class="card" v-for="x in Snack" :key="x.name">
      <Snack
        :Snack-name="x.name"
        :Snack-desc="x.desc"
        :is-favorite="x.favorite" 
        @toggle-favorite="receiveEmit" />
    </div>
  </div>
</template>

<script>
import Makanan from './components/Makanan.vue';
import Minuman from './components/Minuman.vue';
import Snack from './components/Snack.vue';

export default {
  components: {
    Makanan,
    Minuman,
    Snack
  },
  data() {
    return {
      Sushi: [
        { name: 'Nigiri', desc: 'Slices of raw fish atop a small bed of rice', favorite: true },
        { name: 'Sashimi', desc: 'Thin slices of raw fish', favorite: false },
        { name: 'Maki', desc: 'Sushi rolls with seaweed on the outside', favorite: true },
        { name: 'Temaki', desc: 'Hand-rolled sushi in a cone shape', favorite: true }
      ],
      Minuman: [
        { name: 'Sake', desc: 'Japanese rice wine', favorite: true },
        { name: 'Green Tea', desc: 'Traditional Japanese green tea', favorite: false },
        { name: 'Plum Wine', desc: 'Sweet and fruity Japanese plum wine', favorite: true },
        { name: 'Ramune', desc: 'Japanese carbonated soft drink', favorite: true }
      ],
      Snack: [
        { name: 'Edamame', desc: 'Boiled and salted soybeans', favorite: true },
        { name: 'Tempura', desc: 'Lightly battered and fried seafood or vegetables', favorite: false },
        { name: 'Seaweed Salad', desc: 'Salad made from various seaweeds', favorite: true },
        { name: 'Mochi', desc: 'Sweet glutinous rice cakes', favorite: true }
      ],
    };
  },
  methods: {
    receiveEmit() {
      alert('Telah ditambahkan ke favorite!');
    }
  }
};
</script>

<style>
  .header {
    display: flex;
    justify-content: center;
    align-items: center;
    margin: 20px 0;
    padding: 10px 20px;
    background-color: #007BFF; /* Bright blue background */
    border: none;
    border-radius: 50px;
    font-size: 1.8em;
    font-weight: bold;
    color: white;
    cursor: pointer;
    transition: background-color 0.3s, transform 0.3s;
  }
  
  .header:hover {
    background-color: #0056b3; /* Darker blue on hover */
    transform: scale(1.05);
  }

  #wrapper {
    display: flex;
    flex-direction: column;
    align-items: center;
    gap: 30px;
    padding: 30px;
    background-color: #E3F2FD; /* Light blue background */
    border-radius: 15px;
    box-shadow: 0 4px 10px rgba(0, 0, 0, 0.1);
  }

  h1 {
    color: #007BFF; /* Bright blue text */
    text-align: center;
    font-size: 2.5em;
    margin-bottom: 20px;
  }

  .card {
    display: flex;
    flex-direction: column;
    align-items: center;
    width: 90%;
    max-width: 450px;
    padding: 25px;
    border: 1px solid #64B5F6; /* Blue border */
    border-radius: 15px;
    box-shadow: 0 6px 18px rgba(0, 0, 0, 0.15);
    background-color: white;
    transition: transform 0.3s, box-shadow 0.3s;
  }

  .card:hover {
    transform: scale(1.05);
    box-shadow: 0 8px 24px rgba(0, 0, 0, 0.2);
  }

  .card h2 {
    margin: 10px 0;
    font-size: 1.8em;
    color: #007BFF; /* Bright blue text */
  }

  .card p {
    color: #666;
    text-align: center;
    font-size: 1.1em;
  }

  .card button {
    margin-top: 15px;
    padding: 12px 35px;
    background-color: #007BFF; /* Bright blue background */
    border: none;
    border-radius: 10px;
    color: white;
    font-size: 1.1em;
    cursor: pointer;
    transition: background-color 0.3s, transform 0.3s;
  }

  .card button:hover {
    background-color: #0056b3; /* Darker blue on hover */
    transform: scale(1.05);
  }
</style>
