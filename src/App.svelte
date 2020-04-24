<script>

import AppHeader from './Header.svelte';
	let userName = 'Omar';
	let age = 20;
	function AddOne(){
		//age = age +1;
		age += 1;
	}
	function UpdateUserName(event){
		userName = event.target.value;
	}
</script>


<style>
h1{
color:purple;
}
</style>

<AppHeader></AppHeader>

<h1>Hello {userName}, My age is {age} </h1>
 <!-- <input type="text" class="form-control" placeholder="Username" value="{userName}" on:input="{UpdateUserName}"  >
  -->
  <input type="text" class="form-control" placeholder="Username" bind:value="{userName}"   >
 
<button  class="btn btn-primary" on:click="{AddOne}"  >Change Age</button>