<h1>Welcome to SvelteKit { name }</h1>
<p>Visit <a href="https://kit.svelte.dev">kit.svelte.dev</a> to read the documentation</p>

<h2>{@html html}</h2>

<button on:click="{handleClick}"> count add</button>
{count} double: {double}

<p>Arr listen {numbers.join(' + ')} = {sum}</p>

<button on:click="{addNumber}"> num add</button>


<Header count={count} {...obj} />



<script>
	import Header from '../components/Header.svelte'

	const name =  'Xushaopign'
	const html = 'this is <span>qweqe</span>'

	const obj = {
		name: 'xu',
		value: 'shaoping'
	}

	let numbers = [1,2,3]
	$: sum = numbers.reduce((prev, cur) => prev + cur, 0)

	function addNumber() {
		numbers.push(numbers.length + 1)
		numbers = numbers;
	}

	let count = 0;
	$: double = count * 2
	$: {
		console.log(111, `${count}`)
	}
	$: if (count > 10) {
		alert(`count value is high ${count}`)
		count = 0
	}

	function handleClick () {
		count += 1
	}

</script>

<style>
	p {
			color: aqua;
			font-size: 24px;
	}

	h2 {
			color: rebeccapurple;
	}
</style>