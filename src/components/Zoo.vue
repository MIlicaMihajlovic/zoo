<template>
  <div>
      <table border=1>
          <thead>
              <th>Species</th>
              <th>Name</th>
              <th>Day of birth</th>       
          </thead>
          <tbody>
              <tr v-for="animal in animals" :key="key">
                  <td>{{animal.species}}</td>
                  <td>{{animal.name}}</td>
                  <td>{{animal.dayOfBirth}}</td>
              </tr>
          </tbody>
      </table>
  </div>  
</template>

<script>
export default {
    data() {
        return {
            animals: [
                { species: 'panda', name: 'Meda', dayOfBirth: '24.05.1988'},
                { species: 'slon', name: 'Sloncic', dayOfBirth: '09.09.1990'},
                { species: 'pingvin', name: 'Pingvincic', dayOfBirth: '08.10.1997'},
                { species: 'soko', name: 'Belo oko', dayOfBirth: '22.08.1990'},
                { species: 'pas', name: 'Silja', dayOfBirth: '26.04.1994'},
                { species: 'zaba', name: 'Zapcic', dayOfBirth: '20.04.1990'},
                {species: 'delfin', name: 'Delfincic', dayOfBirth: '31.12.1993'},               
            ]
        }
    }
}
</script>

