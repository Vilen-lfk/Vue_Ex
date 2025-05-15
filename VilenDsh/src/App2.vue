<script>
	export default {
	data() {
    return{
        hrefs: [
        {href: '1.html', text: 'text1'},
        {href: '2.html', text: 'text2'},
        {href: '3.html', text: 'text3'},
      ],
      //33
        items: [1, -2, 3, -4, 5 , 6],
      //35
        arr: ['a', 'b', 'c'],
        //37
        cssClasses: 'text-bold text-red' ,// Пример CSS классов 
        //38
        obj: {
            done: true,
            selected: true,
        
      },
        
         message: "Изначальный текст",
        styles: {
          done: false,
        }, 
        //43
         inputText: '', // Инициализируем пустую строку для хранения текста
         //44
         num: 0,
         res: 0,
    }
},
methods: {
	add: function() {
		this.arr.push('xxx');
	}
},
methods: {
    changeText() {
      this.message = "Новый текст после клика";
      this.obj.done = !this.obj.done;
      this.obj.selected = !this.obj.selected;
    }
  },
//39  
methods: {
	setDone: function() {
		this.styles.done = true;
	}
},
//44 для кнопки
methods: {
	calc: function() {
		this.res = this.num ** 2;
	}
},
}



</script>
    <template>
        <div>
            <h1>31</h1>
            <ul>
            <li v-for="ss in hrefs" :key="ss.href">
            <a :href="ss.href">{{ ss.text }}</a>
        </li>
    </ul>
    <h1>32</h1>
        <p v-for="num in 20" :key="num">		
            {{ num }}
        </p>

        <h1>33</h1>
        <ul>
            <template v-for="elem in items">
                <li v-if="elem > 0" :key="elem.items">
                    {{ elem }}
                </li>
            </template>
        </ul>

        <h1>35</h1>
        <p v-for="elem in arr" :key = "elem.arr">
            {{ elem }}
        </p>
        <button @click="add">add</button>

        <h1>37</h1>
        <p :class="cssClasses">Этот абзац получит CSS классы из свойства cssClasses</p>   
        
        <H1>38</H1>
        <p :class="obj">{{ message }}</p>
        <button @click="changeText">Изменить текст и классы</button>

        <h1>39</h1>
        <p :class="styles">text</p>
        <button @click="setDone">hide</button>
        
        <h1> 42</h1>
        <p :style="{color: 'green', backgroundColor: 'yellow'}">
        Зеленый текст на желтом фоне
        </p>
        -----------
        <p :style="{fontWeight: 'bold', fontStyle: 'italic'}">
          Жирный и курсивный текст
        </p>

        <h1>43</h1>
         <input v-model="inputText" placeholder="Введите текст">
        <p>{{ inputText }}</p>

        <h1>44</h1>
        
        <p>{{ res }}</p>
        <input v-model="num">
        <button v-on:click="calc">найди корень числа</button>
      
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
