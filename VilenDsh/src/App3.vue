<script>
	export default {
	data() {
    return{
        nativeLanguage: '', // Здесь будет храниться выбранный язык
        languages: [      
            { id: 'ru', name: 'Русский' },
            { id: 'en', name: 'Английский' },
            { id: 'es', name: 'Испанский' },
            { id: 'tt', name: 'Татарский' }
        ],
        selectedCity: '', // Здесь будет храниться выбранный город
        cities: [     
            'Москва',
            'Санкт-Петербург',
            'Новосибирск',
            'Екатеринбург',
            'Казань'
        ],
        selectedDay: 'Понедельник', // Значение по умолчанию
        daysOfWeek: [
            'Понедельник',
            'Вторник',
            'Среда',
            'Четверг',
            'Пятница',
            'Суббота',
            'Воскресенье'
        ]
        }       
    }
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
