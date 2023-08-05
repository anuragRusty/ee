<script>
    export let searchText = "";
</script>

<div>
    <input class="search" type="text" placeholder="Search..." bind:value={searchText} />
</div>

<style>
    input{
    width: calc(25% - 8px);
    border: 1px solid #ccc;
    border-radius: 5px;
    font-size: 24px;
    margin-bottom: 10px;
    }
    
    @media (max-width: 768px)  {
    input {
      width:calc(100% - 8px);
    }
   }
    
</style>