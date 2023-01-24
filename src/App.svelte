<script>
  import ToolBlock from "../tools/toolBlock.svelte";
  import ListLength from "../tools/listLength.svelte";
  import UniqueItems from "../tools/uniqueItems.svelte";
  import DuplicateItems from "../tools/duplicateItems.svelte";
  import ColorItems from "../tools/colorItems.svelte";
  import ReplaceItems from "../tools/replaceItems.svelte";
  import DeleteItems from "../tools/deleteItems.svelte";
  import ReverseList from "../tools/reverseList.svelte";
  import SortList from "../tools/sortList.svelte";
  import Quoter from "../tools/quoter.svelte" ;
  import AddPrefix from "../tools/addPrefix.svelte";
  import RemovePrefix from "../tools/removePrefix.svelte";
  import AddSuffix from "../tools/addSuffix.svelte";
  import RemoveSuffix from "../tools/removeSuffix.svelte";
  import Maxmin from "../tools/maxmin.svelte";

  let visible=[false,false,false,false,false,false,false,false,false,false,false,false,false,false];
  let toolBlockvisible=[true,true,true,true,true,true,true,true,true,true,true,true,true,true];
  let h2vis=true;
 

  let clicke=()=>
  {
     for (let i = 0; i < toolBlockvisible.length; i++) 
     {
        toolBlockvisible[i]=false;    
     }
     h2vis=false;

  }

  let clickClose=()=>
  {
      for(let i=0;i<toolBlockvisible.length;i++)
      {
        toolBlockvisible[i]=true;
        visible[i]=false;
      }
      h2vis=true;
  }



</script>


<main style="height:1400px;background-color:seashell;overflow-y:scroll">

  <div  class="card1 shadow" style=":background-color: red;margin-top:20px;padding-left:10px"><h1 style="font-family:Verdana, Geneva, Tahoma, sans-serif">
      Online List Tools
  </h1></div>
    <br><br><br><br>
  
  <h2>
      Online List Tool   
      <span style="font-size: 16px;color:gray">
          world's simplest tool list utilities
      </span>
   </h2>

  <p style="margin:40px;font-family:'Times New Roman', Times, serif"> 
        Online list tools offers a collection of useful browser-based utilities for working with lists, such as comma-separated
        lists and to-do lists.All list tools are simple, free, and easy to use. There are no ads, popups, or other garbage, just
         list utilities that work right in your browser. And all utilities work exactly the same way – load a list and get the result.
  </p>
  <br>
  
  <h2 style="color:#AD02FD">
    {h2vis? "List Tools":"List Tool : "}
  </h2>
    
  

  <div class="container">
     <div class="row">
      <div class="col">
     
    <ToolBlock on:click={()=>{visible[0]=!visible[0];clicke();}}  funcName={'Find the length of a List'} desc={'Quickly count the number of items in a list.'} blockvis={toolBlockvisible[0]}/>
      
      {#if visible[0]}
    
        <ListLength  visible={visible[0]}/><br><br><br>
        <button class="close" on:click={clickClose}>Close</button>
       
      {/if}
      </div>
      <div class="col">
        <ToolBlock on:click={()=>{visible[1]=!visible[1];clicke();}}  funcName={'Find Unique List Items'} desc={'Quickly print all distinct items of a list.'} blockvis={toolBlockvisible[1]}/>
          {#if visible[1]}
          
              <UniqueItems visible={visible[1]}/><br><br><br>
              <button class="close" on:click={clickClose}>Close</button>
             
          {/if}
          </div>
    
          <div class="col">
      <ToolBlock on:click={()=>{visible[2]=!visible[2];clicke();}}  funcName={'Find Duplicate List Items'} desc={'Quickly print all repeating items of a list.'} blockvis={toolBlockvisible[2]}/>
        {#if visible[2]}
        
            <DuplicateItems visible={visible[2]}/><br><br><br>
            <button class="close" on:click={clickClose}>Close</button>
           
        {/if}

        </div>
        </div>
        <div class="row">
        <div class="col">
        <ToolBlock on:click={()=>{visible[3]=!visible[3];clicke();}}  funcName={'Color List Items'} desc={'Quickly display list items in multiple colors'} blockvis={toolBlockvisible[3]}/>
          {#if visible[3]}
          
              <ColorItems visible={visible[3]}/><br><br><br>
              <button class="close" on:click={clickClose}>Close</button>
             
          {/if}
          </div>
          <div class="col">
          <ToolBlock on:click={()=>{visible[4]=!visible[4];clicke();}}  funcName={'Replace List items'} desc={'Quickly replace certain items in a list with new items.'} blockvis={toolBlockvisible[4]}/>
            {#if visible[4]}
            
                <ReplaceItems visible={visible[4]}/><br><br><br>
                <button class="close" on:click={clickClose}>Close</button>
            {/if}
            </div>
            <div class="col">

          <ToolBlock on:click={()=>{visible[5]=!visible[5];clicke();}}  funcName={'Delete List items'} desc={'Quickly remove items from list.'} blockvis={toolBlockvisible[5]}/>
            {#if visible[5]}
               <DeleteItems visible={visible[5]}/><br><br><br>
                <button class="close" on:click={clickClose}>Close</button>
            {/if}
            </div>
            </div>
            <div class="row">
              <div class="col">
            <ToolBlock on:click={()=>{visible[6]=!visible[6];clicke();}}  funcName={'Reverse a list'} desc={'Quickly print list items in reverse order.'} blockvis={toolBlockvisible[6]}/>
            {#if visible[6]}
               <ReverseList visible={visible[6]}/><br><br><br>
                <button class="close" on:click={clickClose}>Close</button>
            {/if}</div>
            <div class="col">
            <ToolBlock on:click={()=>{visible[7]=!visible[7];clicke();}}  funcName={'Sort a list'} desc={'Quickly sort list items allphabetically'} blockvis={toolBlockvisible[7]}/>
              {#if visible[7]}
                 <SortList visible={visible[7]}/><br><br><br>
                  <button class="close" on:click={clickClose}>Close</button>
              {/if}
              </div>
              <div class="col">
              <ToolBlock on:click={()=>{visible[8]=!visible[8];clicke();}}  funcName={'Quote List items'} desc={'Quickly wrap all list items in quotes'} blockvis={toolBlockvisible[8]}/>
                {#if visible[8]}
                   <Quoter visible={visible[8]}/><br><br><br>
                    <button class="close" on:click={clickClose}>Close</button>
                {/if}
                </div>
                </div>
                <div class="row">
                  <div class="col">

                <ToolBlock on:click={()=>{visible[9]=!visible[9];clicke();}}  funcName={'Add a list item Prefix'} desc={'Quickly prepend a prefix before each list items'} blockvis={toolBlockvisible[9]}/>
                  {#if visible[9]}
                     <AddPrefix visible={visible[9]}/><br><br><br>
                      <button class="close" on:click={clickClose}>Close</button>
                  {/if}
                  </div>
                  <div class="col">

                  <ToolBlock on:click={()=>{visible[10]=!visible[10];clicke();}}  funcName={'Remove a list item Prefix'} desc={'Quickly removes any prefix from all list items'} blockvis={toolBlockvisible[10]}/>
                    {#if visible[10]}
                       <RemovePrefix visible={visible[10]}/><br><br><br>
                        <button class="close" on:click={clickClose}>Close</button>
                    {/if}
                    </div>
                    <div class="col">
                    <ToolBlock on:click={()=>{visible[11]=!visible[11];clicke();}}  funcName={'Add a list item Suffix'} desc={'Quickly append a suffix after each list items'} blockvis={toolBlockvisible[11]}/>
                      {#if visible[11]}
                         <AddSuffix visible={visible[11]}/><br><br><br>
                          <button class="close" on:click={clickClose}>Close</button>
                      {/if}
                      </div>
                      </div>
                      <div class="row">
                        <div class="col">
                      <ToolBlock on:click={()=>{visible[12]=!visible[12];clicke();}}  funcName={'Remove a list item Suffix'} desc={'Quickly removes any suffix from all list items'} blockvis={toolBlockvisible[12]}/>
                        {#if visible[12]}
                           <RemoveSuffix visible={visible[12]}/><br><br><br>
                            <button class="close" on:click={clickClose}>Close</button>
                        {/if}
                        </div>
                        <div class="col">
                        <ToolBlock on:click={()=>{visible[13]=!visible[13];clicke();}}  funcName={'max and min length list Items'} desc={'Quickly Finds Items with maximum and minimum length in list'} blockvis={toolBlockvisible[13]}/>
                          {#if visible[13]}
                             <Maxmin visible={visible[13]}/><br><br><br>
                              <button class="close" on:click={clickClose}>Close</button>
                          {/if}
                          </div>
                          <div class="col"></div>
                          </div>
  
        
    </div>
    
  

    

</main>


<style>
  h2
  {
    font-family: Cambria, Cochin, Georgia, Times, 'Times New Roman', serif;
    color:rgba(17, 255, 0, 0.923);
    text-align: left;
    margin: 20px;
  }

  p
  {
    text-align:left;
    font-size: 25px;
    line-height: 30px;
  }


  .close
  {
    background-color: red;
    color:black;
    height: 50px;
    width:100px;
    margin-left: 1000px;
    margin-bottom: 50px;
  }
  .card1 {
  background-color: rgb(56, 92, 249);

}
</style>