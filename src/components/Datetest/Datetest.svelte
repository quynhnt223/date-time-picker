<script>
   import { afterPageLoad } from "@roxi/routify"   
   import T1est from "../test/T1est.svelte";
   import { alertme, ScrollToCurrentWeek, DateList } from './function.svelte'
    
   let getUrl
   let dates = DateList(getUrl)


   //test
   const testDate =  document.querySelectorAll(".date")
   testDate.forEach(item => {
      item.style.setProperty("background-color", e, "important");

   });

   
    
   $afterPageLoad(page => {       
      const e = window.location.href.split("/").pop()
      const getUrl = e 
      dates = DateList(getUrl)
           console.log(getUrl)
           ScrollToCurrentWeek()
        
            
   })
</script>
   <div id="date-bar">
      {#each dates as date}
      <a href="/" class="date {date.class}">
      <div class="date-of-month">{date.name}</div>
      <div class="day-of-week">Mon</div>
      </a>
      {/each}
   </div>

   <T1est/>

<style>
a {
    color: black!important;
    display: inline-block;
    padding-left: 12px;
    padding-right: 12px;
}
#date-bar {
    width: 200px;
    white-space: nowrap;
    overflow: auto;
}
.current-date {
    color:blue!important
}
</style>