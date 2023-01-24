<script>
    let str="";
    let arr=[];
    let  del=" ";
    let sep=",";
    let hide=true;
    let quoter="\"";
    export let visible;
    let ans=[];



    let addQuote=()=>
    {
        arr=str.split(del);
       for (let i = 0; i < arr.length; i++) 
       {
           
        let a="";
            a=quoter+arr[i]+quoter;
            arr[i]=a;
            console.log(arr[i]);
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

            <button on:click={addQuote}> Add Quote</button>
            
            <p hidden={hide}><b>Quoted List Items</b></p><br>
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
                    Enter the quoter
                </p>
                <input type="text" bind:value={quoter} placeholder="quoter">

               
            </div>
        {/if}
    </section>
    </div>

<style>
    section{  
        place-content: center;
        text-align: center;
        height: 1000px;
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
        margin-left: 220px;
        margin-bottom: 100px;
    }
</style>