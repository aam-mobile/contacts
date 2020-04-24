<script>
	let name = 'Smith';
	let age = 20;
	function AddOne(){
		//age = age +1;
		age += 1;
	}
</script>


<style>
h1{
color:purple;
}
</style>


<h1>Hello {name}, My age is {age} </h1>

<button  class="btn btn-primary" on:click="{AddOne}"  >Change Age</button>