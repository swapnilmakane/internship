<script>
    let str="";
    let arr=[];
    let  del=" ";
    let sep=",";
    let w1="";
    export let visible;
    let checking=()=>
    {
            for (let i = 0; i < arr.length; i++) 
            {
                if(arr[i]===w1)
                {
                    let a=arr.splice(i,1);
                }    
            }
            str="";
            for (let i = 0; i < arr.length; i++)
            {
                str=str+arr[i];
                if((i<arr.length-1))
                {
                    str=str+del;
                }
            }
           
        }
   
$: arr = str.split(del);
    
</script>
    <p style="color: darkorange;" hidden={!visible}><b>Delete List items</b></p>
    <div style="border-style:solid;height: 1300px;width: 1300px;">

    <section>

        {#if visible}
        <p><b>List</b></p><br>
            <div class="abc">
                <textarea bind:value={str}></textarea> 
            </div> 
            <br>
            
            <p ><b> List Items</b></p><br>
            <div class="output">
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
                <input type="text" bind:value={sep} placeholder="Seperator"><br><br>

                <div  style="height:215px;width:250px;margin-left:20px;box-shadow: 0px 0px 2px 2px white;background-color:cornflowerblue">
                    <p>
                        Enter the which item want to delete
                    </p>
                    <input type="text" bind:value={w1} >
                    <br>
                   
                    <button on:click={checking} style="margin-top:10px">change</button>
                </div>
            </div>
        {/if}
    </section>
    </div>

<style>
    section{  
        place-content: center;
        text-align: center;
        height: 1150px;
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
        height:500px;
        line-height: 40px;
        color:white;
        background-color: blue;
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
    p
    {
        color:springgreen;
        font-size: 20px;
        
    }
</style>