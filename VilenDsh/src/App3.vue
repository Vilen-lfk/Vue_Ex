<script>
	export default {
    props: ['name', 'surn'],    
	data() {
    return{
        //48
        nativeLanguage: '', // Здесь будет храниться выбранный язык
        languages: [      
            { id: 'ru', name: 'Русский' },
            { id: 'en', name: 'Английский' },
            { id: 'es', name: 'Испанский' },
            { id: 'tt', name: 'Татарский' }
        ],
        //49
        selectedCity: '', // Здесь будет храниться выбранный город
        cities: [     
            'Москва',
            'Санкт-Петербург',
            'Новосибирск',
            'Екатеринбург',
            'Казань'
        ],
        //50
        selectedDay: 'Понедельник', // Значение по умолчанию
        daysOfWeek: [
            'Понедельник',
            'Вторник',
            'Среда',
            'Четверг',
            'Пятница',
            'Суббота',
            'Воскресенье'
        ],
        //51
        isInputDisabled: false, // заблокирован
        //52
        inputText: '',
        displayText: '',
        //53
        newItem: '',
		items: ['a', 'b', 'c', 'd', 'e'],
        //54
        items1: ['a', 'b', 'c', 'd', 'e'],
        //55
        users: [
                    { id: 1, name: 'name1', salary: 100, age: 30 },
                    { id: 2, name: 'name2', salary: 200, age: 40 },
                    { id: 3, name: 'name3', salary: 300, age: 50 }
                ],
                
        }       
    },
methods: {
    handleEnter() {
      this.displayText = this.inputText; // Копируем текст при нажатии Enter
      this.inputText = ''; // Очищаем инпут (опционально)
    }
  },
methods: {
	addItem: function() {
		this.items.push(this.newItem);
	}
},
//54
methods: {
	removeItem: function(index) {
		this.items1.splice(index, 1);
	}
},
//55
methods: {
    removeUser(id) {
      this.users = this.users.filter(user => user.id !== id)
    }
  },
}


</script>
    <template>
        <div>
            <h1>48</h1>
            <h3>Какой язык для вас родной?</h3>
    
            <label>
            <input type="radio" v-model="nativeLanguage" value="ru" name="lang">
            Русский
            </label><br>
            
            <label>
            <input type="radio" v-model="nativeLanguage" value="en" name="lang">
            Английский
            </label><br>
            
            <label>
            <input type="radio" v-model="nativeLanguage" value="es" name="lang">
            Испанский
            </label><br>
            
            <label>
            <input type="radio" v-model="nativeLanguage" value="tt" name="lang">
            Татарский
            </label>
            
            <p v-if="nativeLanguage === 'ru'">Вы выбрали: Русский</p>
            <p v-else-if="nativeLanguage === 'en'">Вы выбрали: Английский</p>
            <p v-else-if="nativeLanguage === 'es'">Вы выбрали: Испанский</p>
            <p v-else-if="nativeLanguage === 'tt'">Вы выбрали: Татарский</p>
            <p v-else>Пожалуйста, сделайте выбор</p>
            
            <h1>49</h1>
            <h3>В каком городе вы живете?</h3>
    
            <select v-model="selectedCity">
            <option disabled value="">Выберите город</option>
            <option v-for="city in cities" :key="city" :value="city">
                {{ city }}
            </option>
            </select>
            
            <p v-if="selectedCity">
            Вы выбрали город: {{ selectedCity }}
            </p>
            <p v-else style="color: gray">
            Пожалуйста, выберите город из списка
            </p>

            <h1>50</h1>
            <h3>Выберите день недели:</h3>
    
            <select v-model="selectedDay">
            <option v-for="day in daysOfWeek" :key="day" :value="day">
                {{ day }}
            </option>
            </select>
            
            <p>Вы выбрали: {{ selectedDay }}</p>
               
            <h1>51</h1>
            <input type="text" :disabled="isInputDisabled">
            <button @click="isInputDisabled = !isInputDisabled">Переключить</button>
            
            <h1>52</h1>
            <div>
                <input 
                type="text" 
                v-model="inputText"
                @keyup.enter="handleEnter"
                placeholder="Напишите текст и нажмите Enter"
                >
                <p v-if="displayText">{{ displayText }}</p>

            <h1>53</h1>
            <input v-model="newItem">
	        <button @click="addItem">add</button>
            <ul>
                <li v-for="(item, index) in items" :key="index">
                    {{ item }}
                </li>
            </ul>
            <h1>54</h1>
            <ul>
                <li v-for="(item, index) in items1" :key="index">
                    {{ item }}
                    <button @click="removeItem(index)">remove</button>
                </li>
            </ul>

            <h1>55</h1>
            <table border="1" cellpadding="8" cellspacing="0">
                <thead>
                <tr>
                    <th>ID</th>
                    <th>Имя</th>
                    <th>Зарплата</th>
                    <th>Возраст</th>
                    <th>Действия</th>
                </tr>
                </thead>
                <tbody>
                <tr v-for="user in users" :key="user.id">
                    <td>{{ user.id }}</td>
                    <td>{{ user.name }}</td>
                    <td>{{ user.salary }}$</td>
                    <td>{{ user.age }} лет</td>
                    <td>
                    <button @click="removeUser(user.id)">Удалить</button>
                    </td>
                </tr>
                </tbody>
            </table>
            <h1></h1>
            </div>
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
