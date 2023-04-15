<script>
        import { afterPageLoad } from "@roxi/routify"  
/**
 * Returns the week number for this date.  dowOffset is the day of week the week
 * "starts" on for your locale - it can be from 0 to 6. If dowOffset is 1 (Monday),
 * the week returned is the ISO 8601 week number.
 * @param int dowOffset
 * @return int
 */
 

          
   
$afterPageLoad(page => {

    Date.prototype.getWeek = function (dowOffset) {
/*getWeek() was developed by Nick Baicoianu at MeanFreePath: http://www.meanfreepath.com */

    dowOffset = typeof(dowOffset) == 'number' ? dowOffset : 0; //default dowOffset to zero
    var newYear = new Date(this.getFullYear(),0,1);
    var day = newYear.getDay() - dowOffset; //the day of week the year begins on
    day = (day >= 0 ? day : day + 7);
    var daynum = Math.floor((this.getTime() - newYear.getTime() - 
    (this.getTimezoneOffset()-newYear.getTimezoneOffset())*60000)/86400000) + 1;
    var weeknum;
    //if the year starts before the middle of a week
    if(day < 4) {
        weeknum = Math.floor((daynum+day-1)/7) + 1;
        if(weeknum > 52) {
            nYear = new Date(this.getFullYear() + 1,0,1);
            nday = nYear.getDay() - dowOffset;
            nday = nday >= 0 ? nday : nday + 7;
            /*if the next year starts before the middle of
              the week, it is week #1 of that year*/
            weeknum = nday < 4 ? 1 : 53;
        }
    }
    else {
        weeknum = Math.floor((daynum+day-1)/7);
    }
    return weeknum;
};

        let monthEle = document.querySelector('.month');
let yearEle = document.querySelector('.year');
let btnNext = document.querySelector('.btn-next');
let btnPrev = document.querySelector('.btn-prev');
let dateEle = document.querySelector('.date-container');

let currentMonth = new Date().getMonth();



let currentYear = new Date().getFullYear();

function displayInfo() {
    // Hiển thị tên tháng
    let currentMonthName = new Date(
        currentYear,
        currentMonth
    ).toLocaleString('en-us', { month: 'long' });

    monthEle.innerText = currentMonthName;

    // Hiển thị năm
    yearEle.innerText = currentYear;
    
    // Hiển thị ngày trong tháng
    renderDate();
}

// Lấy số ngày của 1 tháng
function getDaysInMonth() {
    return new Date(currentYear, currentMonth + 1, 0).getDate();
}

// Lấy ngày bắt đầu của tháng
function getStartDayInMonth() {
    return new Date(currentYear, currentMonth, 1).getDay();
}

// Active current day
function activeCurrentDay(day) {
    let day1 = new Date().toDateString();
    let day2 = new Date(currentYear, currentMonth, day).toDateString();
    return day1 == day2 ? 'active' : '';
}

// Hiển thị ngày trong tháng lên trên giao diện
function renderDate() {
    let daysInMonth = getDaysInMonth();
    let startDay = getStartDayInMonth();

    dateEle.innerHTML = '';

    for (let i = 0; i < startDay; i++) {
        dateEle.innerHTML += `
            <a href="" class="day"></a>
        `;
    }

    for (let i = 0; i < daysInMonth; i++) {
        const monthName = currentMonth + 1
        let e = monthName + "-" + (i + 1) + "-" + currentYear
        const myDate = new Date(e);  
        const weekNumber = myDate.getWeek()
        const currentDayOfWeek = myDate.getDay()
        

       
        dateEle.innerHTML += `
            <a href="./day/${currentDayOfWeek + "-" + weekNumber + "-" + currentYear}" class="day ${activeCurrentDay(i + 1)}">${i + 1}</a>
        `;
    }
}

// Xử lý khi ấn vào nút next month
btnNext.addEventListener('click', function () {
    if (currentMonth == 11) {
        currentMonth = 0;
        currentYear++;
    } else {
        currentMonth++;
    }
    displayInfo();
});

// Xử lý khi ấn vào nút previous month
btnPrev.addEventListener('click', function () {
    if (currentMonth == 0) {
        currentMonth = 11;
        currentYear--;
    } else {
        currentMonth--;
    }
    displayInfo();
});

displayInfo();


    });

</script>

<div class="container">
    <button class="btn btn-prev">
        <span><i class="fa fa-chevron-left" aria-hidden="true"></i></span>
    </button>
    <div class="calendar">
        <h1>Calendar</h1>
        <div class="info">
            <p class="month">September</p>
            <p class="year">2020</p>
        </div>
        <div class="date">            
            <div class="day-name">Sun</div>
            <div class="day-name">Mon</div>
            <div class="day-name">Tue</div>
            <div class="day-name">Wen</div>
            <div class="day-name">Thu</div>
            <div class="day-name">Fri</div>
            <div class="day-name">Sat</div>            
        </div>
        <div class="date date-container">              
        </div>
    </div>
    <button class="btn btn-next">
        <span><i class="fa fa-chevron-right" aria-hidden="true"></i></span>
    </button>
</div>

<style>
    *,
*::after,
*::before {
    padding: 0;
    margin: 0;
    box-sizing: border-box;
}
    .container {
    display: flex;
    justify-content: center;
    align-items: center;

    background-image: linear-gradient(120deg, #e0c3fc 0%, #8ec5fc 100%);
    height: 100vh;
    overflow: hidden;
}

.calendar {
    width: 626px;
    background-color: #fff;
    padding: 2rem;
    border-radius: 4px;
}

.calendar h1 {
    text-transform: uppercase;
    margin-bottom: 2rem;
    text-align: center;
}

.info {
    display: flex;
    justify-content: space-between;
    margin-bottom: 1rem;
}

.info p {
    font-size: 1.5rem;
    font-weight: 600;
}

.date {
    border: 1px solid #ccc;

    display: flex;
    flex-wrap: wrap;
}

:global(.day,.day-name) {
    width: 80px;
    height: 80px;
    border: 1px solid #ccc;

    font-size: 1.5rem;
    text-align: center;
    line-height: 80px;
    color:#000!important
}

.btn {
    display: inline-block;
    padding: 1rem;
    font-size: 1.5rem;
    border: none;
    outline: none;
    cursor: pointer;
    border-radius: 4px;
    transition: all 0.5s ease-in;
}

.btn {
    background-image: linear-gradient(to right,
            #aa076b 0%,
            #61045f 51%,
            #aa076b 100%);
}

.btn {
    background-size: 200% auto;
    color: #fff;
    box-shadow: 0 0 20px #eee;
}

.btn:hover {
    background-position: right center;
    color: #fff;
    text-decoration: none;
}

.btn-next {
    margin-left: 1rem;
}

.btn-prev {
    margin-right: 1rem;
}

:global(.day.active ){
    background-image: linear-gradient(to right,
            #aa076b 0%,
            #61045f 51%,
            #aa076b 100%);
    color: #fff;
}

</style>