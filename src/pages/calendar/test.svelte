<script>
    import { afterPageLoad } from "@roxi/routify"
    let days
    let week
    let year
    let currentDate
    let day
    let today
    let todaydate = new Date().getDate()

    $afterPageLoad(page => {
        const currentDate2 = new Date("1/12/2023");
        var year2 = currentDate2.getFullYear()
        const year3 = new Date(currentDate2.getFullYear(), 0, 1);
        var days2 = Math.floor((currentDate2 - year3) / (24 * 60 * 60 * 1000));
        var week2 = Math.ceil(( currentDate2.getDay() + 1 + days2) / 7);

        var currentmonth = Math.floor((11 * 24 * 60 * 60 * 1000) * 2023)
        var currentDate5 = Date.now();
        var tri = new Date(1.702944e+12)
        const d = new Date();
let ms = d.getMilliseconds();
        console.log(currentmonth)
        console.log(tri)

        const day2 = currentDate2.getDay()
        const selectDay = document.querySelectorAll("a")
                selectDay.forEach((item) => {
                    const dayId = item.getAttribute("id")
                    item.setAttribute("href", dayId + week2+ year2);

            

                })
        days = days2
        day = day2
        year = year2
        week = week2
        currentDate = currentDate2
        today = day2 + "-" + week2 + "-" + year2
        const todaactive = document.getElementById(day2)
        todaactive.classList.add("today")
        })



</script>
<input type= "date" id= "date">
{days}<br>
{year}
<br>
{week}<br>
{currentDate}
<br>
{day}

<a id="1" href="">mon</a>
<a id="2" href="">tue</a>
<a id="3" href="">wed</a>
<a id="4" href="">thu</a>
<a id="5" href="">fri</a>
<a id="6" href="">sat</a>
<a id="7" href="">sun</a>
<h1>today url: </h1>{today}
<h1>today date: </h1>{todaydate}
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
