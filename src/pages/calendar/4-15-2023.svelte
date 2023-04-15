<script>
    import { afterPageLoad } from "@roxi/routify"  
    let todayDate        
   
    $afterPageLoad(page => {
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
        // get current url and convert to week, weekday, year
        const getUrl = window.location.href.split("/").pop()
        const weekday = getUrl.charAt(0);
        // current week
        const currentWeek = getUrl.substring(1, 4).replace(/-/g, '');
        // end current week
        const currentYear = getUrl.slice(-4);
        let dateFormatMath = weekToDate(currentYear, currentWeek, weekday);
        let dateFormat = new Date(dateFormatMath)

        todayDate = dateFormat
        console.log(dateFormat)

               
        const weekdays = document.querySelectorAll(".weekday") 

        //add dynamic href base on id
        weekdays.forEach((item) => {
            const weekdayId = item.getAttribute("id")
            item.setAttribute("href", weekdayId + "-" + currentWeek + "-" + currentYear);

        });
        document.getElementById(weekday).classList.add("today")
        
   

    });
</script>
<a class="weekday" id="1" href="">mon</a>
<a class="weekday" id="2" href="">tue</a>
<a class="weekday" id="3" href="">wed</a>
<a class="weekday" id="4" href="">thu</a>
<a class="weekday" id="5" href="">fri</a>
<a class="weekday" id="6" href="">sat</a>
<a class="weekday" id="7" href="">sun</a>

<h1>Today Date is:</h1>
<p>{todayDate}</p>
<input bind:value={todayDate}>

<style>
:global(a) {
    color: #000!important;
    padding: 12px;
}
:global(.today) {
    color: blue!important;
    font-weight: 900;
}
</style>
    
