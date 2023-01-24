<script>
    let str="";
    let arr=[];
    let  del=" ";
    let sep=",";
    let hide=true;
    let pre="";
    export let visible;



    let removePrefix=()=>
    {
        arr=str.split(del);
        let a;
        for (let w = 0; w < arr.length; w++) 
        {
            if(arr[w].startsWith(pre))
        {
            a=arr[w].slice(pre.length,arr[w].length);
            arr[w]=a; 
        }    
        }
        hide=false;
}
</script>
<p style="color: darkorange;" hidden={!visible}><b>Find the length of a List</b></p>
<div style="border-style:solid;height: 1000px;width: 1300px;">

    <section>

        {#if visible}
        <p><b>List</b></p><br>
            <div class="abc">
                <textarea bind:value={str} on:click={()=>{hide=true}}></textarea> 
            </div> 
            <br>

            <button on:click={removePrefix} hidden={!hide}> Remove Prefix</button>
            <p hidden={hide}><b>List Items after removal of Prefix</b></p><br>

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
                    Enter the prefix
                </p>
                <input type="text" bind:value={pre} placeholder="Prefix">

               
            </div>
        {/if}
    </section>
    </div>

<style>
    section{  
        place-content: center;
        text-align: center;
        height: 850px;
        width: 900px;
    }
    p
    {
        color:springgreen;
        font-size: 20px;
        
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
        margin-left: 450px;
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
        margin-left: 450px;
        background-color: azure;
        color: black;
        text-align: left;
        padding: 20px;
        border-color: black;
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