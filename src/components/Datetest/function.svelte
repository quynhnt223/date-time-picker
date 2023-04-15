<script context="module">

// Get Week number of the year from url
export function weekToDate(year, week, weekDay) {			
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

// test
export function alertme() {
	console.log("haha")
}

// Scroll To current Week
export function ScrollToCurrentWeek() {
	const viewContainer = document.getElementById("date-bar")
    const dayItem = document.querySelector(".current-date")

    viewContainer.scrollTo(dayItem.offsetLeft, 0)
    

}


   
// Get Data for Date List
export function DateList(getUrl) {
	const dates = [
		{name: getUrl},
		{},
		{},
		{},
		{},
		{},
		{},
		{},
		{class: "current-date"},
		{},
		{},
		{},
		{},
		{},
		{},
		{},
		{},
	]
return dates
}

</script>