<script>
import Employee from './components/Employee.vue';
import User from './components/User.vue';
import Child from './components/Child.vue';
import Employee1 from './components/Employe1.vue';
import UserForm from './components/UserForm.vue'; // обязательно импортируйте

export default {
  components: {
    User,
    Employee,
    Employee1,
    Child,
    UserForm
  },
  data() {
    return {
      name1: 'John',
      surn1: 'Smith',
      price1: 150,
      users: [
        { id: 1, name: 'Иван', surn: 'Иванов', salary: 100, age: 30 },
        { id: 2, name: 'Петр', surn: 'Петров', salary: 200, age: 40 },
        { id: 3, name: 'Сергей', surn: 'Сергеев', salary: 300, age: 50 }
      ]
    };
  },
  methods: {
    firstAction() {
      alert('Вызвана первая функция из родителя!');
    },
    secondAction() {
      alert('Вызвана вторая функция из родителя!');
    },
    func(name) {
      console.log('Получено имя от дочернего:', name);
    },
    addUser(name, surn) {
      const id = this.users.length + 1;
      this.users.push({ id, name, surn, salary: 0, age: 0 }); // можно дописать поля по умолчанию
    }
  }
};
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

    <h1>66</h1>
    <Employee1
      v-for="user in users"
      :key="user.id + '-emp1'"
      :name="user.name"
      @sendName="func"
    />

    <h1>67</h1>
    <!-- Эти кнопки не будут работать без родителя -->
    <!-- Уберите их или вставьте в отдельный компонент -->

    <h1>70</h1>
    <h2>Список работников</h2>
    <ul>
      <li v-for="user in users" :key="user.id + '-list'">
        {{ user.id }}. {{ user.name }} {{ user.surn }}
      </li>
    </ul>

    <h2>Добавить нового работника</h2>
    <UserForm @add="addUser" />
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
