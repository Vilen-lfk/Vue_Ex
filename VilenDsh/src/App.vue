<script>
	export default {
	data() {
	return {
		name: 'john',
		surn: 'smit',
    // 5
    text: 'page',
		href: 'page.html',
    // 6 
    num: 5,
    // 7 
    arr: ['x', 'y', 'z'],
    // 8
    obj: {x: 1, y: 2, z: 4},
    // 11
    num1: 1,
    num2: 2,
    // 12
    num3: 4,
    //14
    text: 'VIlen',
    //15
    cost: 130,
    amount: 3,
    //17
    visible: true,
    visible1: false,
     //А вот если visible поставить в значение false, то абзац будет скрыт:
  }
},
    // 9 - 10
 methods: {
    show: function() {
      const currentDate = new Date().toLocaleDateString();
    alert(currentDate);
  },
    sum: function(){
      let sum = this.num1 + this.num2;
      console.log(sum)
    },
    //12
    show1: function() {
		  let text = this.cape(this.text);
		console.log(text);
	},
	  cape: function(str) {
		  return str[0].toUpperCase() + str.slice(1);//делает первую букву заглавную
	},
    kv: function(num3){
      const proisv = this.num3 * this.num3; 
      alert(proisv);
    },
    change: function() {
		this.text = 'Dasha';
	},
  //16
    handleClick(event) {
      event.preventDefault(); // Отменяем стандартное поведение ссылки
      alert('Клик по ссылке обработан, но переход отменен');
      // Здесь может быть ваша логика обработки клика
    }
    
},
//15
computed: {
        price() {
          return this.cost * this.amount;
        }
  }
}
  


</script>
<template>
	<div>
		Hello World
    <p> My name is Vilen</p>

    <div>
      <h1>4 задание</h1>
      {{ name }}
      {{ surn }}
    </div>
      <h1>5 задание</h1>
      <a href="page.html">page</a>

      <h1>6 задание</h1>
      {{ num * num }}

      <h1>7 задание</h1>
      <p> {{ arr[0] }}</p>
      <p> {{ arr[1] }}</p>
      <p> {{ arr[2] }}</p>

      <h1>8 задание</h1>
      {{ obj.x + obj.y + obj.z }}

      <h1>9 задание</h1>
      <button @click="show">Показать дату</button>

      <h1>10 задание</h1>
      <button v-on:click="show">text</button>

      <h1> 11</h1>
      <button v-on:click="sum">сумма чисел num1 и num2</button>

      <h1> 12</h1>
      {{ show1() }}

      <h1> 13</h1>
      <button @click="kv('proisv')">Квадрат числа num3</button>
      <h1>14</h1>
      {{ text }}
	  <button @click="change">text</button>   
    <div>
    <h2>15 задание</h2>
    <p>Цена за единицу: {{ cost }}</p>
    <p>Количество: {{ amount }}</p>
    <p>Общая стоимость: {{ price }}</p> <!-- Вот здесь выводится price -->
  </div>
    <h1>16</h1>
     <a href="https://example.com" @click="handleClick">
      Нажми меня (перехода не будет)
    </a>
    <h1>17</h1>
    <p v-if="visible">text</p>
    <p v-if="visible1">text</p>
    </div>
    
    
</template>

<style scoped>
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
