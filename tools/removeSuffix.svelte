<script>
    let str="";
    let arr=[];
    let  del=" ";
    let sep=",";
    let hide=true;
    let suff="";
    export let visible;


    
    let removeSuffix=()=>
    {
        arr=str.split(del);
        let a;
        for (let w = 0; w < arr.length; w++) 
        {
            if(arr[w].endsWith(suff))
        {
            a=arr[w].slice(0,arr[w].length-suff.length)
            arr[w]=a;
        }

        }
         hide=false;
    }
</script>
<p style="color: darkorange;" hidden={!visible}><b>Remove a list item Suffix</b></p>
<div style="border-style:solid;height: 1100px;width: 1300px;">

    <section>

        {#if visible}
        <p><b>List</b></p><br>
            <div class="abc">
                <textarea bind:value={str} on:click={()=>{hide=true}}></textarea> 
            </div> 
            <br>

            <button on:click={removeSuffix} hidden={!hide}> Remove Suffix</button>
 
            <p hidden={hide}><b>List Items after removal of Suffix</b></p><br>
            <div class="output" hidden={hide}>
                {#each Array(arr.length) as _,i}
                    
                     {arr[i]}{(i<arr.length-1)? sep:""}
                {/each}
            </div><br><br>


            <div class="delimeter" hidden={!hide}>
                <p>
                    Enter the Delimeter for Input
                </p>
                <input type="text" bind:value={del} placeholder="Delimeter">
                <br>
                <p>
                    Enter the Seperator for Output
                </p>
                <input type="text" bind:value={sep} placeholder="Seperator">
                <br>
                <p>
                    Enter the Suffix
                </p>
                <input type="text" bind:value={suff} placeholder="Suffix">

               
            </div>
        {/if}
    </section>
</div>

<style>
    section{  
        margin-top: 100px;
        place-content: center;
        text-align: center;
        height: 900px;
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
    .abc
    {
        margin-left: 100px;
        padding-left: 190px;
        height:300px;
        width:800px;
    }
    .delimeter
    {
        padding-top: 10px;
        margin-left: 460px;
        box-shadow: 0px 0px 2px 2px black;
        width:300px;
        height:350px;
        line-height: 40px;
        background-color: blue;
        color: white;
    }
    .output
    {
        height: 200px;
        width: 300px;
        border: 2px solid white;
        margin-left: 460px;
        background-color: azure;
        color: black;
        text-align: left;
        padding: 20px;
        border-color: black;
    }
    p
    {
        color:springgreen;
        font-size: 20px;
        
    }
    input
    {
        background-color: aliceblue;
        color: black;
    }
    button{
        background-color: greenyellow;
        color: black;
        border-color: black;
        margin-left: 250px;
        margin-bottom: 100px;
    }
</style>