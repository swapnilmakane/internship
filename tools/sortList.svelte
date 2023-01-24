<script>
    let str="";
    let arr=[];
    let  del=" ";
    let sep=",";
    let temp=[];
 
    let hide=true;
    let opt;
    export let visible;
    
    $: arr = str.split(del);
    $:temp=arr.sort();
   
</script>
<p style="color: darkorange;" hidden={!visible}><b>Sort a list</b></p>
<div style="border-style:solid;height: 1350px;width: 1300px;">
    <section>
        {#if visible}
        <p><b>List</b></p><br>
            <div class="res">
                <textarea id="ab" bind:value={str}></textarea> 
            </div> 
            <br>

            <br><br><br> 
            
            <p ><b>Ascending ordered list</b></p><br>
            <div class="output">
                
                {#each Array(temp.length) as _,i}
                {temp[i]}{(i<temp.length-1)? sep:""}
            {/each}
            
            </div>
            <br><br>
            <p ><b>Descending ordered list</b></p><br>
            <div class="output">
                
                {#each Array(temp.length) as _,i}
                {temp[temp.length-1-i]}{(i<temp.length-1)? sep:""}
            {/each}
            <br>
            </div><br><br>
       

            <div class="delimeter">
                <p>
                    Enter the Delimeter for Input
                </p>
                <input type="text" bind:value={del} placeholder="Delimeter">
                <br>
                <p>
                    Enter the Seperator for Output
                </p>
                <input type="text" bind:value={sep} placeholder="Seperator">
            </div>
         {/if}
        
    </section>
    </div>

<style>
    section{  
        place-content: center;
        text-align: center;
        height: 1100px;
        width: 900px;
    }
    textarea
    {
        padding: 20px;
        height: 200px;
        width:300px;
        background-color: azure;
        color: black;
    }
    .res
    {
        margin-left: 150px;
        padding-left: 190px;
        height:200px;
        width:800px;
    }

    .output
    {
        overflow: auto;
        height: 200px;
        width: 300px;
        border: 2px solid white;
        margin-left: 500px;
        background-color: azure;
        text-align: left;
        padding: 20px;
        color: black;
        border-color: black;
    }
    p
    {
        color:springgreen;
        font-size: 20px;
        
    }
    .delimeter
    {
        color:white;
        box-shadow: 0px 0px 2px 2px black;
        padding-top: 10px;
        margin-left: 500px;
        width:300px;
        height:250px;
        line-height: 40px;
        background-color: blue;
        color: white;
    }
</style>