<script> 
    export let funcName;
    export let desc;
    export let blockvis;
</script>


  <div class="card  w-85" hidden={!blockvis}>
    
        <div class="card-body">
          <h5 class="card-title">{funcName}</h5>
          <p class="card-text">{desc}</p>
          <button class="btn btn-primary" on:click>Click Here</button>

  
    </div>
    </div>

<!-- <style>

  .abc
  {
    display: block;
    border: 2px solid gray;
    width:400px;
  }
  .def
  {
    /* display:grid; */
    border: 2px solid white;
    padding: 5px;
    height:120px;
    width: 400px;
    background-color:#13CDF6;
    font-size: 20px;

  }
  .ghi
  {
    margin-top: 20px;
    line-height:20px;
    text-align:center;
  }
button
{
  background-color: #13CDF6;
  color: black;
  font-size: 25px;
  padding: 10px;
  border-color: blue;
  margin-top: 3px;
  margin-bottom: 3px;
}
</style> -->