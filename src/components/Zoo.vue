<template>
  <div>

      <form @submit.prevent="addAnimal">
          <label>Species</label>
          <input v-model="newAnimal.species" />
          <p>{{species}}</p>

          <label>Name</label>
          <input v-model="newAnimal.name"/>
          <p>{{name}}</p>

          <label>Day of birth</label>
          <input v-model="newAnimal.dayOfBirth"/>
          <p>{{dayOfBirth}}</p>

          <label>Select sector</label>  
          <select v-model="newAnimal.sector">
            <option v-for="(sector,index) in sectors" :key="index" v-bind:value="sector">
                {{ sector.name }}
            </option>
            </select><br>

          <button type="submit">Add animal</button>
      </form><br>

      <table border=1>
          <thead>
              <th>Species</th>
              <th>Name</th>
              <th>Day of birth</th>
              <th>Sector</th> 
              <th>Button move</th>  
              <th>Remove button</th>       
          </thead>
          <tbody>
              <tr v-for="(animal,index) in animals" :key="index">
                  <td>{{animal.species}}</td>
                  <td>{{animal.name}}</td>
                  <td>{{animal.dayOfBirth == '' ? 'Unknown' : animal.dayOfBirth}}</td>
                  <td>{{animal.sector.name}}</td>
                  <td><button @click="moveToTop(animal)">Move to top</button></td>
                  <td><button @click="removeAnimal(animal)">Remove animal</button></td>                 
              </tr>
          </tbody>
      </table>
  </div>  
</template>

<script>

const sectors = [
    {name: 'Water-animals', surface: 'Water'},
    {name: 'Fawl', surface: 'Kages'},
    {name: 'Predators', surface: 'Kages'}
];

export default {
    data() {
        return {

            newAnimal: {
                species: '', name: '', dayOfBirth: ''
            },

            animals: [
                { species: 'panda', name: 'Meda', dayOfBirth: '24.05.1988', sector:sectors[1]},
                { species: 'slon', name: 'Sloncic', dayOfBirth: '', sector:sectors[1]},
                { species: 'pingvin', name: 'Pingvincic', dayOfBirth: '08.10.1997', sector:sectors[0]},
                { species: 'soko', name: 'Belo oko', dayOfBirth: '22.08.1990', sector:sectors[2]},
                { species: 'pas', name: 'Silja', dayOfBirth: '26.04.1994', sector:sectors[1]},
                { species: 'zaba', name: 'Zapcic', dayOfBirth: '', sector:sectors[0]},
                {species: 'delfin', name: 'Delfincic', dayOfBirth: '31.12.1993', sector:sectors[0]},               
            ],

            sectors:sectors, //ovde smo morali da dodamo jer nam je const sectors van export
        };
    },

    methods: {
        removeAnimal(animal) {
            this.animals.splice((this.animals.indexOf(animal)),1);
        },

        moveToTop(animal) {
            this.removeAnimal(animal); //iskoristili metodu odozgo i animal smo prvo sklonili iy niza
            this.animals.unshift(animal); //a ovde ga dodali na pocetak niza
        },

        addAnimal() {
            this.animals.push(this.newAnimal);
            this.newAnimal = {};
        }
    }
}
</script>

