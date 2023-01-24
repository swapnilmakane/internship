<script>
    let str="";
    let arr=[];
    let count=0;
    let  del=" ";
    export let visible;
    
   
$: arr = str.split(del);
    
</script>
<p style="color: darkorange;" hidden={!visible}><b>Find the length of a List</b></p>
<div style="border-style:solid;height: 800px;width: 1300px;">
    <section>
        {#if visible}
  


        <p><b>List</b></p><br>
            <div class="abc">
                <textarea bind:value={str}></textarea> 
            </div> 
            <br>

            <div >
                
                {#if str.charAt(0)==""}
                    <p style="margin-left: 250px;width=50px;border-color: black;border-style:solid">Empty List</p>
                 {:else}
                    <p style="margin-left: 425px;width:300px;border-color: black;border-style:solid">The number of items in a list is {arr.length}</p>
                 {/if}<br><br>

            </div>

            <div class="delimeter">
                <p>
                    Enter the Delimeter
                </p>
                <input type="text" bind:value={del}>
                
            </div>
        {/if}
    </section>
</div>
    

<style>
    section{ 
        place-content: center;
        text-align: center;
        height: 550px;
        width: 900px;
    }
    textarea
    {
        padding: 20px;
        margin-left: 160px;
        height: 200px;
        width:300px;
    }
    .abc
    {
        padding-left: 190px;
        height:300px;
        width:800px;
    }
    .delimeter
    {
        margin-left: 480px;
        box-shadow: 0px 0px 2px 2px black;
        width:200px;
        height:125px;
        line-height: 40px;
        background-color: blue;
        color: white;
    }
    p
    {
        color:springgreen;
        font-size: 20px;
        
    }
</style>