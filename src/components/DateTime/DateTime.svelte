<script>
    import {onMount} from 'svelte'
    import { afterPageLoad } from "@roxi/routify"

    let days2 = []
    // convert url to date format
    function weekToDate(year, week, weekDay) {
        
        const getZeroBasedIsoWeekDay = date => (date.getDay() + 6) % 7;
        const getIsoWeekDay = date => getZeroBasedIsoWeekDay(date) + 1;
        const zeroBasedWeek = week - 1;
        const zeroBasedWeekDay = weekDay - 1;
        let days = (zeroBasedWeek * 7) + zeroBasedWeekDay;
        // Dates start at 2017-01-01 and not 2017-01-00
        days += 1;

        const firstDayOfYear = new Date(year, 0, 1);
        const firstIsoWeekDay = getIsoWeekDay(firstDayOfYear);
        const zeroBasedFirstIsoWeekDay = getZeroBasedIsoWeekDay(firstDayOfYear);

        // If year begins with W52 or W53
        if (firstIsoWeekDay > 4) {
        days += 8 - firstIsoWeekDay; 
        // Else begins with W01
        } else {
        days -= zeroBasedFirstIsoWeekDay;
        }

        return new Date(year, 0, days);
    }
    
//------------------------------------------------------------------------


  
    
$afterPageLoad(page => {
    const getUrl = "9-15-2023"
        const currentWeek = getUrl.substring(1, 4).replace(/-/g, '');
        const weeknumber = parseInt(currentWeek, 10)
        const currentYear = getUrl.slice(-4);

        console.log(getUrl)
        
                
     days2 = [
            {dataid: "6", href: "6" + "-" + (weeknumber - 2) + "-" + currentYear, weekday: (weeknumber - 2), class: "week"},
    {dataid: "0", href: "0" + "-" + (weeknumber - 2) + "-" + currentYear, weekday: "SUN"},
    {dataid: "1", href: "1" + "-" + (weeknumber - 2) + "-" + currentYear, weekday: "MON"},
    {dataid: "2", href: "2" + "-" + (weeknumber - 2) + "-" + currentYear, weekday: "TUE"},
    {dataid: "3", href: "3" + "-" + (weeknumber - 2) + "-" + currentYear, weekday: "WED"},
    {dataid: "4", href: "4" + "-" + (weeknumber - 2) + "-" + currentYear, weekday: "THU"},
    {dataid: "5", href: "5" + "-" + (weeknumber - 2) + "-" + currentYear, weekday: "FRI"},
    {dataid: "6", href: "6" + "-" + (weeknumber - 2) + "-" + currentYear, weekday: "SAT"},
    {dataid: "6", href: "6" + "-" + (weeknumber - 2) + "-" + currentYear, weekday: (weeknumber - 1), class: "week"},
    {dataid: "0", href: "0" + "-" + (weeknumber - 1) + "-" + currentYear, weekday: "SUN"},
    {dataid: "1", href: "1" + "-" + (weeknumber - 1) + "-" + currentYear, weekday: "MON"},
    {dataid: "2", href: "2" + "-" + (weeknumber - 1) + "-" + currentYear, weekday: "TUE"},
    {dataid: "3", href: "3" + "-" + (weeknumber - 1) + "-" + currentYear, weekday: "WED"},
    {dataid: "4", href: "4" + "-" + (weeknumber - 1) + "-" + currentYear, weekday: "THU"},
    {dataid: "5", href: "5" + "-" + (weeknumber - 1) + "-" + currentYear, weekday: "FRI"},
    {dataid: "6", href: "6" + "-" + (weeknumber - 1) + "-" + currentYear, weekday: "SAT"},
    {dataid: "6", href: "6" + "-" + (weeknumber - 2) + "-" + currentYear, weekday: weeknumber, class: "week"},
    {dataid: "0", href: "0" + "-" + weeknumber + "-" + currentYear, weekday: "SUN", class: "cool"},
    {dataid: "1", href: "1" + "-" + weeknumber + "-" + currentYear, weekday: "MON"},
    {dataid: "2", href: "2" + "-" + weeknumber + "-" + currentYear, weekday: "TUE"},
    {dataid: "3", href: "3" + "-" + weeknumber + "-" + currentYear, weekday: "WED"},
    {dataid: "4", href: "4" + "-" + weeknumber + "-" + currentYear, weekday: "THU"},
    {dataid: "5", href: "5" + "-" + weeknumber + "-" + currentYear, weekday: "FRI"},
    {dataid: "6", href: "6" + "-" + weeknumber + "-" + currentYear, weekday: "SAT"},
    {dataid: "6", href: "6" + "-" + (weeknumber - 2) + "-" + currentYear, weekday: (weeknumber + 1), class: "week"},
    {dataid: "0", href: "0" + "-" + (weeknumber + 1) + "-" + currentYear, weekday: "SUN"},
    {dataid: "1", href: "1" + "-" + (weeknumber + 1) + "-" + currentYear, weekday: "MON"},
    {dataid: "2", href: "2" + "-" + (weeknumber + 1) + "-" + currentYear, weekday: "TUE"},
    {dataid: "3", href: "3" + "-" + (weeknumber + 1) + "-" + currentYear, weekday: "WED"},
    {dataid: "4", href: "4" + "-" + (weeknumber + 1) + "-" + currentYear, weekday: "THU"},
    {dataid: "5", href: "5" + "-" + (weeknumber + 1) + "-" + currentYear, weekday: "FRI"},
    {dataid: "6", href: "6" + "-" + (weeknumber + 1) + "-" + currentYear, weekday: "SAT"},
    {dataid: "6", href: "6" + "-" + (weeknumber - 2) + "-" + currentYear, weekday: (weeknumber + 2), class: "week"},
    {dataid: "0", href: "0" + "-" + (weeknumber + 2) + "-" + currentYear, weekday: "SUN"},
    {dataid: "1", href: "1" + "-" + (weeknumber + 2) + "-" + currentYear, weekday: "MON"},
    {dataid: "2", href: "2" + "-" + (weeknumber + 2) + "-" + currentYear, weekday: "TUE"},
    {dataid: "3", href: "3" + "-" + (weeknumber + 2) + "-" + currentYear, weekday: "WED"},
    {dataid: "4", href: "4" + "-" + (weeknumber + 2) + "-" + currentYear, weekday: "THU"},
    {dataid: "5", href: "5" + "-" + (weeknumber + 2) + "-" + currentYear, weekday: "FRI"},
    {dataid: "6", href: "6" + "-" + (weeknumber + 2) + "-" + currentYear, weekday: "SAT"},

]

    let dateFormatMath = weekToDate(12, 5, 2023);
    let dateFormat = new Date(dateFormatMath)

    let todayDate = dateFormat.getDate()       




//------------------------------------------------------------------------


//------------------------------------------------------------------------

const days =  document.querySelectorAll(".day")
days.forEach(item => {
    const itemHref = item.getAttribute("href");
    const itemWeek = itemHref.substring(1, 4).replace(/-/g, '');    
    const itemYear = itemHref.slice(-4);
    const itemDay = itemHref.charAt(0);
    const dateFormat = weekToDate(itemYear, itemWeek, itemDay)

    const itemDate = dateFormat.getDate();
    const ok = item.querySelector("div")
    const ok2 = ok.querySelector(".date")
    ok2.innerText = itemDate


})

const weeks =  document.querySelectorAll(".week")
    weeks.forEach(item => {
        const ok = item.querySelector("div")
        const ok2 = ok.querySelector(".date")
        ok2.innerText = "week"

        console.log("cool.offsetLeft")
    })


var e = document.getElementById("view")
    var cool = document.querySelector(".cool")

    e.scrollTo(cool.offsetLeft, 0)

    console.log(cool.offsetLeft)

    
    

})
    
    

     
    
      
      

     

  

</script>

<div id="view" class="list-wrap">
    <a href="/">More</a>
{#each days2 as day}
<a  class="day {day.class}" href={day.href} data-id={day.dataid}>
    <div>
        <div class="date">{day.weekday}</div>
        <div>{day.weekday}</div>
    </div>
</a>
{/each}
<a href="/">More</a>
</div>
<style>

a{
    color: blue!important;
    padding: 12px;
    height: 68px;
    display: inline-block;
    width: 14.2857142857%;

}
.list-wrap {
    overflow-y: auto;
    white-space: nowrap;
    max-width: 440px;
    margin: auto;
    position: fixed;
    top: 36px;
    left: 0;
    right: 0;
    background-color: #fff;
    height: 68px;
    cursor: grab;
    box-shadow: rgba(50, 50, 93, 0.25) 0px 30px 60px -12px, rgba(0, 0, 0, 0.3) 0px 18px 36px -18px;
    
}
:global(.cool) {
    background:red!important
}
/* width */
::-webkit-scrollbar {
  height: 0px;
  width: 0;
}

/* Track */
::-webkit-scrollbar-track {
  background: #f1f1f1; 
}
 
/* Handle */
::-webkit-scrollbar-thumb {
  background: #888; 
}

/* Handle on hover */
::-webkit-scrollbar-thumb:hover {
  background: #555; 
}
:global(.week) {
    background-color: green;
    color: #fff!important;
    width: 86px!important;
    
}
:global(.week div) {
   
    color: #fff!important;
}
</style>