<script>
    let str="";
    let arr=[];
    let dupli=[];
    let  del=" ";
    let sep=",";
    let ans=[];
    let k=0;
    let hide=true;
    export let visible;
    let count;

$: arr = str.split(del);
let concate=()=>
    {

        dupli=arr;
        k=0;
        for (let i = 0; i < dupli.length-1; i++) 
        {
            count=1;
            for (let j = i+1; j < dupli.length; j++) 
            {
                if(dupli[i]==dupli[j])
                {
                    count++;
                    dupli[j]="0"
                }
            }   
            if(count > 1 && dupli[i] != "0")
            {
                ans[k]=dupli[i];
                k++;
            }
        }
        k=0;
        hide=false;
    }
 
    
    
</script>
<p style="color: darkorange;" hidden={!visible}><b>Find Duplicate List Items</b></p>
<div style="border-style:solid;height: 1020px;width: 1300px;">

<section>

    {#if visible}
    <p><b>List</b></p><br>
        <div class="abc">
             <textarea bind:value={str} on:click={()=>{hide=true}}></textarea> 
        </div> 
        <br>
        <button on:click={concate}> Find</button>
        <p  hidden={hide}><b>Duplicate List Items</b></p><br>
        <div class="output" hidden={hide}>
          <!-- <p hidden={true}>{concate()}</p> -->
            
            {ans}
        </div><br><br><br>


        <div class="delimeter"  hidden={!hide}>
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
        margin-left: 200px;
        height:300px;
        width:800px;
    }
    .delimeter
    {
        padding-top: 10px;
        margin-left: 450px;
        box-shadow: 0px 0px 2px 2px black;
        width:300px;
        height:250px;
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
    }p
    {
        color:springgreen;
        font-size: 20px;
        
    }
    button{
        background-color: greenyellow;
        color: black;
        border-color: black;
        margin-left: 250px;
        margin-bottom: 100px;
    }
</style>