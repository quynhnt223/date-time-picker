<script>
    import Back from "../../components/icons/Back.svelte";
    import Clock from "../../components/icons/Clock.svelte";
    import Goto from "../../components/icons/Goto.svelte";
    import Plus from "../../components/icons/Plus.svelte";

</script>
<a href="/daily-routine/edit" class="add-button"><span><Plus/></span></a>
<div class="top-bar">
<a href="/app" ><Back/> </a>
<p>My Daily Routine</p>
</div>

<div class="date-picker">
    <div class="item active"><span>24</span><p>Mon</p></div>
    <div class="item"><span>24</span><p>Tue</p></div>
    <div class="item"><span>25</span><p>Wed</p></div>
    <div class="item"><span>26</span><p>Thu</p></div>
    <div class="item"><span>27</span><p>Fri</p></div>
    <div class="item"><span>28</span><p>Sat</p></div>
    <div class="item"><span>29</span><p>Sun</p></div>
</div>

<div class="daily-routine">
    <a href="/daily-routine/routine-1" class="card">
        <div class="col-1">
            <div><img src="/yellow.svg"></div>    
        </div>
        <div class="col-2">
            <span class="title">Morning Routine</span>
            <div class="time"><Clock/><span>30 mins</span></div>   
        </div>
        <div class="col-3">
            <div><Goto/></div>
        </div>
    
    </a>
    <a href="/daily-routine/routine-2" class="card">
        <div class="col-1">
            <div><img src="/dark-green.svg"></div>    
        </div>
        <div class="col-2">
            <span class="title">Working Routine</span>
            <div class="time"><Clock/><span>12 hours</span></div>   
        </div>
        <div class="col-3">
            <div><Goto/></div>
        </div>
    
    </a>
    <a href="/daily-routine/routine-3" class="card">
        <div class="col-1">
            <div><img src="/dark-blue.svg"></div>    
        </div>
        <div class="col-2">
            <span class="title">After Work Routine</span>
            <div class="time"><Clock/><span>90 mins</span></div>   
        </div>
        <div class="col-3">
            <div><Goto/></div>
        </div>
    
    </a>
    <a href="/daily-routine/routine-4" class="card">
        <div class="col-1">
            <div><img src="/pink.svg"></div>    
        </div>
        <div class="col-2">
            <span class="title">Everning Routine</span>
            <div class="time"><Clock/><span>4 hours</span></div>   
        </div>
        <div class="col-3">
            <div><Goto/></div>
        </div>
    
    </a>
    <a href="/daily-routine/routine-5" class="card">
        <div class="col-1">
            <div><img src="/dark-purple.svg"></div>    
        </div>
        <div class="col-2">
            <span class="title">Before Bed Routine</span>
            <div class="time"><Clock/><span>30 mins</span></div>   
        </div>
        <div class="col-3">
            <div><Goto/></div>
        </div>
    
    </a>
    <a href="/daily-routine/routine-6" class="card">
        <div class="col-1">
            <div><img src="/navy.svg"></div>    
        </div>
        <div class="col-2">
            <span class="title">Bedtime Routine</span>
            <div class="time"><Clock/><span>30 mins</span></div>   
        </div>
        <div class="col-3">
            <div><Goto/></div>
        </div>
    
    </a>
    <a href="/daily-routine/routine-7" class="card">
        <div class="col-1">
            <div><img src="/light-green.svg"></div>    
        </div>
        <div class="col-2">
            <span class="title">Weekend Routine</span>
            <div class="time"><Clock/><span>30 mins</span></div>   
        </div>
        <div class="col-3">
            <div><Goto/></div>
        </div>
    
    </a>
    <a href="/daily-routine/routine-8" class="card">
        <div class="col-1">
            <div><img src="/yellow-green.svg"></div>    
        </div>
        <div class="col-2">
            <span class="title">Holiday Routine</span>
            <div class="time"><Clock/><span>30 mins</span></div>   
        </div>
        <div class="col-3">
            <div><Goto/></div>
        </div>
    
    </a>

</div>
<style>

:root {
      --dark: #032330ff;
      --green: #2EDE7Fff;     
      --light: #EEF4F5;
      
  }




.date-picker {
    display: flex;
    padding-top: 68px;
    justify-content: space-between;
    background-color: #E3F3F0;
}
.date-picker .item {
    border-radius: 8px;
    background-color: #fff;
    display: flex;
    justify-content: center;
    align-items: center;
    flex-direction: column;    
    width: calc(14.2857% - 6px);
    padding-bottom: 6px;
    padding-top: 6px;
}
.item p {
    margin: 0;
    font-size: 11px;
    font-weight: 600;
    color: #2C6052;
}
.item span {
    color: #9CBAB4;
    font-weight: 500;
}
.active {
    background-color: var(--green)!important;
    
}
.active span {color: var(--dark)!important;font-weight: 700!important;}
.active p {color: var(--dark)!important;font-weight: 700!important;}
.daily-routine {
    padding: 20px;
    padding-bottom: 86px;
    background-color: #E3F3F0;

}
.card {
    border-radius: 18px;
    padding:8px;
    background-color: #fff;
    display: flex;
    align-items: center;
    margin-bottom: 4px;
    padding-left: 12px;
    box-shadow: rgba(0, 0, 0, 0.12) 0px 1px 3px, rgba(0, 0, 0, 0.24) 0px 1px 2px;
}
.col-1 div{
border-radius: 8px;
width:32px;
height: 32px;
margin-right: 16px;
}
.col-2 {
    width: 100%;
}
.col-2 .title{
    font-size: 15px;
    font-weight: 600;
    color: #2C6052;
}
.col-2 .time{
    display: flex;
    align-items: center;
    font-size: 11px;
    color: #64B68E;
    font-weight: 500;
}
.time span {
    padding-left: 8px;
}

.col-3 div {
    width: 32px;
    height: 32px;
    align-items: center;
    background: #E3F3F0;
    display: flex;
    justify-content: center;
    border-radius: 50px;
}
.add-button {
    max-width: 360px;
    bottom:104px;
    left: 0;
    right: 0;
    margin: auto;
    padding-bottom: 12px;
    padding-right: 12px;
    position: fixed;
}
.add-button span {    
    width: 42px;
    height: 42px;
    background: var(--green);
    border-radius: 12px;
    box-shadow: rgba(0, 0, 0, 0.16) 0px 3px 6px, rgba(0, 0, 0, 0.23) 0px 3px 6px;
    display: flex;
    align-items: center;
    justify-content: center;
    float: right;

}
</style>