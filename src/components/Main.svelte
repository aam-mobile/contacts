<script>

	import ContactCard from "./ContactCard.svelte"

	let name = 'Bill Gates';
	let title = 'Programmer';
	let image = 'https://pbs.twimg.com/profile_images/988775660163252226/XpgonN0X_400x400.jpg';
	let description = 'Owner of Microsoft';	
	let formState = 'empty';
	let contacts = [];

	function addContact()
	{
		if(name.trim().length == 0 || title.trim().length == 0  || image.trim().length == 0  || description.trim().length == 0 )
		{			
			formState = 'invalid'
			return;
		}

		//The input is valid. Go ahead and add the contact.

		contacts = [
				...contacts,
				{
					userName:name,
					jobTitle:title,
					imageUrl:image,
					desc: description
				}
		]	
				
		formState = 'completed'
	}
	

</script>
<style>
</style>
 
<div class="container">
      
		<h1>Contacts</h1>
		
			<div class="form-group">
				<label for="txtUserName">User Name</label>
				<input type="text" class="form-control" id="txtUserName" bind:value={name} >
			</div>
			<div class="form-group">
				<label for="txtJobTitle">Job Title</label>
				<input type="text" class="form-control" id="txtJobTitle" bind:value={title}  >
			</div>
			<div class="form-group">
				<label for="txtImageUrl">Image URL</label>
				<input type="text" class="form-control" id="txtImageUrl"  bind:value={image} >
			</div>
			<div class="form-group">
				<label for="txtDescription">Description</label>
				<input type="text" class="form-control" id="txtDescription"  bind:value={description} >
			</div>

			<button type="submit" class="btn btn-primary"   on:click ={addContact}   >Add Contact</button>
		 

		{#if formState == 'invalid'}
			<div class="alert alert-danger" role="alert">
				Invalid Input
				</div>
		{:else}
			<p>Please add contact info.</p>
		{/if}

		{#each contacts as contact, i }
		<h6>#{i + 1}</h6>
 
<ContactCard
			userName = {contact.userName}
			jobTitle ={contact.jobTitle} 
			UserImage = {contact.imageUrl}
			description ={contact.desc} 
			
			></ContactCard>
 
			

		{/each}
 
 
		
</div>
