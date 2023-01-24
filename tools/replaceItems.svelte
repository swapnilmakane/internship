<script>
    let str="";
    let arr=[];
    let  del=" ";
    let sep=",";
    let w1="",w2="";
    export let visible;
    let checking=()=>
    {
            for (let i = 0; i < arr.length; i++) 
            {
                if(arr[i]==w1)
                {
                    arr[i]=w2;
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
<p style="color: darkorange;" hidden={!visible}><b>Replace List items</b></p>
<div style="border-style:solid;height: 1400px;width: 1300px;">

    <section>
        
        {#if visible}
        <p><b>List</b></p><br>
            <div class="abc">
                <textarea bind:value={str}></textarea> 
            </div> 
            <br>
            
            <p ><b>List Items</b></p><br>
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

                <div  style="height:330px;width:250px;margin-left:20px;box-shadow: 0px 0px 2px 2px white;background-color:cornflowerblue">
                    <p>
                        Enter the which item want to change
                    </p>
                    <input type="text" bind:value={w1} >
                    <p>
                        By which word
                    </p>
                    <input type="text" bind:value={w2} ><br><br>
                    <button on:click={checking}>change</button>
                </div>
            </div>
        {/if}
    </section>
</div>    

<style>
    section{  
        place-content: center;
        text-align: center;
        height: 1200px;
        width: 900px;
    }
    textarea
    {
        margin-left: 140px;
        height: 200px;
        width:300px;
        background-color: azure;
        color: black;
    }
    .abc
    {
        margin-left: 90px;
        padding-left: 190px;
        height:300px;
        width:800px;
    }
    .delimeter
    {
        padding-top: 10px;
        margin-left: 500px;
        box-shadow: 0px 0px 2px 2px black;
        width:300px;
        height:600px;
        line-height: 40px;
        background-color: blue;
        color: white;
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
</style>