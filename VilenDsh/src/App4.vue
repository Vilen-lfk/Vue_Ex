<script>
import Employee from './components/Employee.vue'
import User from './components/User.vue'
import Child from './components/Child.vue'
export default {
  components: {
    User,
    Employee,
    Child // добавьте сюда Child, а не внутрь data()
  },
  data() {
    return {
      users: [
        {
          id: 1,
          name: 'name1',
          salary: 100,
          age: 30,
        },
        {
          id: 2,
          name: 'name2',
          salary: 200,
          age: 40,
        },
        {
          id: 3,
          name: 'name3',
          salary: 300,
          age: 50,
        },
      ],
      name1: 'John',     // добавьте, если используете в <User :name1="name1" />
      surn1: 'Smith',
      price1: 150
    };
  },
  methods: {
    firstAction() {
      alert('Вызвана первая функция из родителя!');
    },
    secondAction() {
      alert('Вызвана вторая функция из родителя!');
    }
  }
}
</script>



<template>
    <div>
        <User />
        
        <h1>59</h1>
        <User names="john" surn="smit" />
        
        <h1>61</h1>
        <User :name1="name1" :surn1="surn1" :price1="price1" />

        <h1>63</h1>
        <Employee
      v-for="user in users"
      :key="user.id"
      :name="user.name"
      :salary="user.salary"
      :age="user.age"
    />

    <h1>65</h1>
    <Child @clickOne="firstAction" @clickTwo="secondAction" />
    </div>
</template>

<style scoped>
p.done {
	text-decoration: line-through;
}
p{
    color: green;
}

header {
  line-height: 1.5;
}

.logo {
  display: block;
  margin: 0 auto 2rem;
}

@media (min-width: 1024px) {
  header {
    display: flex;
    place-items: center;
    padding-right: calc(var(--section-gap) / 2);
  }

  .logo {
    margin: 0 2rem 0 0;
  }

  header .wrapper {
    display: flex;
    place-items: flex-start;
    flex-wrap: wrap;
  }
}
</style>
