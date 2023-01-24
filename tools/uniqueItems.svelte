<script>
    let str="";
    let arr=[];
    let  del=" ";
    let sep=",";
    export let visible;
    
   
$: arr = str.split(del);
    
</script>
<p style="color: darkorange;" hidden={!visible}><b>Find Unique List Items</b></p>
<div style="border-style:solid;height: 1000px;width: 1300px;">
    <section>

        {#if visible}
        <p><b>List</b></p><br>
            <div class="abc">
                <textarea bind:value={str}></textarea> 
            </div> 
            <br>
            

            <p ><b>Unique List Items</b></p><br>
            <div class="output">
                    {#each Array(arr.length) as _,i}
                {i==arr.indexOf(arr[i])?arr[i]:""}{(i<arr.length-1)? sep:""}
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
            </div>
        {/if}
    </section>
    </div>

<style>
    section{  
        place-content: center;
        text-align: center;
        height: 800px;
        margin-bottom: 50px;
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
        padding-left: 190px;
        height:300px;
        width:800px;
        margin-left: 150px;
    }
    .delimeter
    {
        padding-top: 10px;
        margin-left: 500px;
        box-shadow: 0px 0px 2px 2px black;
        width:300px;
        height:250px;
        line-height: 40px;
        background-color: blue;
        color: white;
    }
    p
    {
        color:springgreen;
        font-size: 20px;
        
    }
    .output
    {
        height: 200px;
        width: 300px;
        border: 2px solid white;
        margin-left: 500px;
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
</style>