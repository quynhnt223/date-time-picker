<script>
	import { DateTime } from "luxon";
    import { goto } from '@roxi/routify'  
    
    

    const currentDate = new Date();
    const currentYear = currentDate.getFullYear()
    const currentYearForMath = new Date(currentDate.getFullYear(), 0, 1);
    const dayOfTheYear = Math.floor((currentDate - currentYearForMath) / (24 * 60 * 60 * 1000));
    const currentWeek = Math.ceil(dayOfTheYear / 7);
    const currentDayOfTheWeek = currentDate.getDay()
    const todayUrl = currentDayOfTheWeek + "-" + currentWeek + "-" + currentYear

    $goto('./day/' + todayUrl)
</script>

