<script>
    let str="";
    let arr=[];
    let  del=" ";
    let hide=true;
    let max;
    let min;
    let maxItems=[],minItems=[];
    export let visible;
    
   let find=()=>
   {
        arr = str.split(del);
        arr=arr.sort((a,b)=>a.length-b.length);
        
        max=arr[arr.length-1];
    
        max=max.length;
        
        
        maxItems=[];
        if (arr.length==1) 
        {
            maxItems[0]=arr[0];
        }
        else
        {
            let i=arr.length-1;
            while (arr[i].length==max) 
            {
                maxItems[maxItems.length]=arr[i];
                i--;    
            }           
        }
        minItems=[];
        min=arr[0].length;
        console.log(min)
        if (arr.length==1) 
        {
            minItems[0]=arr[0];
        }
        else
        {
            let i=0;
            while (arr[i].length==min) 
            {
                minItems[minItems.length]=arr[i];
                i++;    
            }           
        }
        hide=false;
   }


    
</script>
<p style="color: darkorange;" hidden={!visible}><b>Max and Min length list Items</b></p>
<div style="border-style:solid;height: 800px;width: 1300px;">
    <section>

        {#if visible}
        <p><b>List</b></p><br>
            <div class="abc">
                <textarea bind:value={str} on:click={()=>{hide=true}}></textarea> 
            </div> 
            <br>

            <button on:click={find}> Find</button>
 
            <div class="output" hidden={hide}>
               Item with Maximum length :<br>
                    <p style="margin: 10px;margin-left:20px;height:10px">{maxItems}</p>
                    -------------------------------------<br>
                    Maximum length:{max}<br>
                    -------------------------------------<br>
                    Item with Minimum length :<br>
                    <p style="margin: 10px;margin-left:20px;height:10px">{minItems}</p>
                    -------------------------------------<br>
                    Minimun length:{min}<br>
                    -------------------------------------
            </div>
            <br><br>


            <div class="delimeter" hidden={!hide}>
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
        margin-left: 80px;
        padding-left: 190px;
        height:300px;
        width:800px;
    }
    .delimeter
    {
        
        padding-top: 10px;
        margin-left: 440px;
        box-shadow: 0px 0px 2px 2px black;
        width:300px;
        height:150px;
        line-height: 40px;
        background-color: blue;
        color: white;
    }
    .output
    {
        overflow-y:auto;
        scroll-behavior: smooth;
        height: 250px;
        width: 300px;
        border: 2px solid white;
        margin-left: 435px;
        background-color: azure;
        color: black;
        text-align: left;
        padding: 20px;
        border-color: black;
    }
    input
    {
        overflow-y: auto;
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
    p
    {
        color:springgreen;
        font-size: 20px;
        
    }
    </style>