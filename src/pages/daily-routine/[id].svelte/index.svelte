<script>
    import Back from "../../../components/icons/Back.svelte";
    import Clock from "../../../components/icons/Clock.svelte";
    import Goto from "../../../components/icons/Goto.svelte";
    import Plus from "../../../components/icons/Plus.svelte";

</script>
<a href="/daily-routine/edit" class="add-button"><span><Plus/></span></a>
<div class="top-bar">
    <a href="/daily-routine" ><Back/> </a>
    <div><img src="/yellow.svg"></div>
    <p>Morning Routine</p>
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
<div class="routine-content">
<div class="routine-list">
    <div class="list-wrap">
        <div class="list-header">
            <p>Start up</p>      
            <div class="clock">
            <span>30 mins</span>
            <Clock/>
            </div>  
        </div>
        <div class="list-cards">
            <div class="card-item">
                <div class="check-box"><span></span></div>
                <div class="order-number">1</div>
                <p>Wake up</p>
                <span><Goto/></span>
            </div>
            <div class="card-item">
                <div class="check-box"><span></span></div>
                <div class="order-number">2</div>
                <p>Turn off Alarm</p>
                <span><Goto/></span>
            </div>
            <div class="card-item">
                <div class="check-box"><span></span></div>
                <div class="order-number">3</div>
                <p>Go toilet</p>
                <span><Goto/></span>
            </div>
            <div class="card-item">
                <div class="check-box"><span></span></div>
                <div class="order-number">4</div>
                <p>Drink warm water</p>
                <span><Goto/></span>
            </div>
            <div class="card-item">
                <div class="check-box"><span></span></div>
                <div class="order-number">5</div>
                <p>Be positive</p>
                <span><Goto/></span>
            </div>
        </div>
    </div>
    <div class="list-wrap">
        <div class="list-header">
            <p>Warm up</p>       
            <div class="clock">
            <span>30 mins</span>
            <Clock/>
            </div> 
        </div>
        <div class="list-cards">
            <div class="card-item">
                <div class="check-box"><span></span></div>
                <div class="order-number">1</div>
                <p>Wake up</p>
                <span><Goto/></span>
            </div>
            <div class="card-item">
                <div class="check-box"><span></span></div>
                <div class="order-number">2</div>
                <p>Turn off Alarm</p>
                <span><Goto/></span>
            </div>
            <div class="card-item">
                <div class="check-box"><span></span></div>
                <div class="order-number">3</div>
                <p>Go toilet</p>
                <span><Goto/></span>
            </div>
            <div class="card-item">
                <div class="check-box"><span></span></div>
                <div class="order-number">4</div>
                <p>Drink warm water</p>
                <span><Goto/></span>
            </div>
            <div class="card-item">
                <div class="check-box"><span></span></div>
                <div class="order-number">5</div>
                <p>Be positive</p>
                <span><Goto/></span>
            </div>
        </div>
    </div>
    <div class="list-wrap">
        <div class="list-header">
            <p>Exercise</p>      
            <div class="clock">
            <span>30 mins</span>
            <Clock/>
            </div>  
        </div>
        <div class="list-cards">
            <div class="card-item">
                <div class="check-box"><span></span></div>
                <div class="order-number">1</div>
                <p>Wake up</p>
                <span><Goto/></span>
            </div>
            <div class="card-item">
                <div class="check-box"><span></span></div>
                <div class="order-number">2</div>
                <p>Turn off Alarm</p>
                <span><Goto/></span>
            </div>
            <div class="card-item">
                <div class="check-box"><span></span></div>
                <div class="order-number">3</div>
                <p>Go toilet</p>
                <span><Goto/></span>
            </div>
            <div class="card-item">
                <div class="check-box"><span></span></div>
                <div class="order-number">4</div>
                <p>Drink warm water</p>
                <span><Goto/></span>
            </div>
            <div class="card-item">
                <div class="check-box"><span></span></div>
                <div class="order-number">5</div>
                <p>Be positive</p>
                <span><Goto/></span>
            </div>
        </div>
    </div>
    <div class="list-wrap">
        <div class="list-header">
            <p>Breakfast</p>     
            <div class="clock">
            <span>30 mins</span>
            <Clock/>
            </div>   
        </div>
        <div class="list-cards">
            <div class="card-item">
                <div class="check-box"><span></span></div>
                <div class="order-number">1</div>
                <p>Wake up</p>
                <span><Goto/></span>
            </div>
            <div class="card-item">
                <div class="check-box"><span></span></div>
                <div class="order-number">2</div>
                <p>Turn off Alarm</p>
                <span><Goto/></span>
            </div>
            <div class="card-item">
                <div class="check-box"><span></span></div>
                <div class="order-number">3</div>
                <p>Go toilet</p>
                <span><Goto/></span>
            </div>
            <div class="card-item">
                <div class="check-box"><span></span></div>
                <div class="order-number">4</div>
                <p>Drink warm water</p>
                <span><Goto/></span>
            </div>
            <div class="card-item">
                <div class="check-box"><span></span></div>
                <div class="order-number">5</div>
                <p>Be positive</p>
                <span><Goto/></span>
            </div>
        </div>
    </div>
    <div class="list-wrap">
        <div class="list-header">
            <p>Getting Ready</p> 
            <div class="clock">
            <span>30 mins</span>
            <Clock/>
            </div>       
        </div>
        <div class="list-cards">
            <div class="card-item">
                <div class="check-box"><span></span></div>
                <div class="order-number">1</div>
                <p>Wake up</p>
                <span><Goto/></span>
            </div>
            <div class="card-item">
                <div class="check-box"><span></span></div>
                <div class="order-number">2</div>
                <p>Turn off Alarm</p>
                <span><Goto/></span>
            </div>
            <div class="card-item">
                <div class="check-box"><span></span></div>
                <div class="order-number">3</div>
                <p>Go toilet</p>
                <span><Goto/></span>
            </div>
            <div class="card-item">
                <div class="check-box"><span></span></div>
                <div class="order-number">4</div>
                <p>Drink warm water</p>
                <span><Goto/></span>
            </div>
            <div class="card-item">
                <div class="check-box"><span></span></div>
                <div class="order-number">5</div>
                <p>Be positive</p>
                <span><Goto/></span>
            </div>
        </div>
    </div>
    <div class="list-wrap">
        <div class="list-header">
            <p>Going to Work</p> 
            <div class="clock">
            <span>30 mins</span>
            <Clock/>
            </div>       
        </div>
        <div class="list-cards">
            <div class="card-item">
                <div class="check-box"><span></span></div>
                <div class="order-number">1</div>
                <p>Wake up</p>
                <span><Goto/></span>
            </div>
            <div class="card-item">
                <div class="check-box"><span></span></div>
                <div class="order-number">2</div>
                <p>Turn off Alarm</p>
                <span><Goto/></span>
            </div>
            <div class="card-item">
                <div class="check-box"><span></span></div>
                <div class="order-number">3</div>
                <p>Go toilet</p>
                <span><Goto/></span>
            </div>
            <div class="card-item">
                <div class="check-box"><span></span></div>
                <div class="order-number">4</div>
                <p>Drink warm water</p>
                <span><Goto/></span>
            </div>
            <div class="card-item">
                <div class="check-box"><span></span></div>
                <div class="order-number">5</div>
                <p>Be positive</p>
                <span><Goto/></span>
            </div>
        </div>
    </div>
</div>
</div>
<style>
    :root {
      --dark: #032330ff;
      --green: #2EDE7Fff;     
      --light: #EEF4F5;
      
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
.top-bar div{
    width:32px;
    margin-right:12px;
    display: flex;
    align-items: center;
}
.date-picker {
    display: flex;    
    justify-content: space-between;
    background-color: #E3F3F0;
    position: fixed;
    top:90px;
    padding-top:8px;
    padding-bottom:8px;
    left: 0;
    right: 0;
    max-width: 360px;
    margin: auto;
    display: none;
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
.routine-content {
    background-color: #E3F3F0;
    min-height: 100vh;
    padding-top: 124px;
}
.card-item {
    display: flex;
    border-bottom: 2px solid #E3F3F0;
    align-items: center;
    background-color: #fff;
}
.card-item p {
    flex: 1;
}
.check-box {
    padding-left: 12px;
    padding-right: 12px;
}
.order-number {
    padding-right:12px ;
}
.check-box span {
width: 32px;
height: 32px;
border: 2px solid #E3F3F0;
border-radius: 12px!important;
display: block;
}
@media only screen and (max-width: 600px) {
.date-picker {
    top:54px!important;
    max-width: 440px;
}

}
.card-item span {
    width: 36px;
    height: 36px;
    background: #fff;
    border-radius: 50px;
    display: flex;
    align-items: center;
    justify-content: center;
    margin-right: 12px;
}
.list-header p {
    font-weight: 700;
    padding-left: 12px;
    padding-right: 12px;
}
.list-header {
    display: flex;
    align-items: center;
    justify-content: space-between;
}
.clock span {
    padding-right:12px;
    font-size: 11px;
    font-weight: 600;
    color: red;
}
.clock {padding-right: 12px;
display: flex;
align-items: center;
}
</style>