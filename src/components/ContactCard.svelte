<script>

    export let userName;
    export let	jobTitle;
    export	let	UserImage;
    export   let description;
            
</script>

<style>

</style>
<div class="row">
  <div class="col-sm-4">
        <div class="card" >
        <img src={UserImage} class="card-img-top" alt={userName}>
            <div class="card-body">
            <h5 class="card-title">{userName}</h5>
            <h6 class="card-title">{jobTitle}</h6>
            <p class="card-text">{description}</p>
            </div>
        </div>
  </div>
</div>