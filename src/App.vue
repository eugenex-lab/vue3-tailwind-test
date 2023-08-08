<template>
  <main class="min-h-screen bg-gray-100 p-12">
        <TotalExpenses :label="'hu'" :totalExpenses="totalUserExpenses" />
    <div class="my-3"></div>
    <h4 class="text-xl">{{ PageTitle }}</h4>
    <div class="border border-black"></div>
    <ul class="mt-4">
      <li class="my-1"  v-for="user in userData" :key="user.numericValue" >
  
         <Card :user="user" />
      </li>
     
    </ul>
  </main>
</template>

<script>
import TotalExpenses from './components/TotalExpenses.vue';

/**
 * 1 - Call this API url https://jsonplaceholder.typicode.com/users, supplying only the name and numeric value.
 *
 * 2 - Convert from design to code the component <TotalExpenses /> with input directives for label and number
 *
 * 3 - Use a computed property of this.existingExpenses to get the sum of each totalValue and pass it as an input in <TotalExpenses />
 */
export default {
  name: 'App',
  components: {
    TotalExpenses,
    
  },
  data() {
    return {
      PageTitle: 'Friend List',
      existingExpenses: [
        {
          totalValue: 663651,
          totalTransactions: 136,
        },
        {
          totalValue: 841600,
          totalTransactions: 171,
        },
        {
          totalValue: 991305,
          totalTransactions: 201,
        },
      ],

      userData: []

    };
  },
  methods: {
    fetchUsers() {
      const fetchUrl = 'https://jsonplaceholder.typicode.com/users';

      fetch(fetchUrl)
          .then(response => {
            if (!response.ok) {
              throw new Error('Network response was not ok');
            }
            return response.json();
          })
          .then(data => {
            this.userData = data.map(user => ({
              name: user.name,
              phoneNUmber: user.phone, // Use phone number as the numeric value
            }));
          })
          .catch(error => {
            console.error('Error fetching users:', error);
          });
    },
  },



  mounted() {
    this.fetchUsers(); 
  },



};
</script>
