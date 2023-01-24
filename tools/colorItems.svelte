<script>
    let str="";
    let arr=[];
    let  del=" ";
    let sep=",";
    let colors="black";
    export let visible;
    
   
$: arr = str.split(del);
    
</script>
    <p style="color: darkorange;" hidden={!visible}><b>Color List Items</b></p>
    <div style="border-style:solid;height: 1200px;width: 1300px;">
    <section>

        {#if visible}
        <p><b>List</b></p><br>
            <div class="abc">
                <textarea bind:value={str}></textarea> 
            </div> 
            <br>
            

            <p ><b>coloured List Items</b></p><br>
            <div class="output" style="color: {colors};">
                    {#each Array(arr.length) as _,i}
                        {arr[i]}{(i<arr.length-1)? sep:""}
                    {/each}
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
                <p>
                    Enter the Color Name
                </p>
                <input type="color" bind:value={colors}>
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
    .abc
    {
        margin-left: 190px;
        height:300px;
        width:800px;
    }
    .delimeter
    {
        padding-top: 10px;
        margin-left: 450px;
        box-shadow: 0px 0px 2px 2px black;
        width:300px;
        height:400px;
        line-height: 40px;
        background-color: blue;
       
    }
    .output
    {
        height: 200px;
        width: 300px;
        border: 2px solid white;
        margin-left: 450px;
        background-color: azure;
        text-align: left;
        padding: 20px;
        border-color: black;
       }
    input
    {
        background-color: aliceblue;
        color: black;
    }
    p
    {
        color:springgreen;
        font-size: 20px;
        
    }
</style>