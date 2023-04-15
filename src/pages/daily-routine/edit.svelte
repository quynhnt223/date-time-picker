<script>

    import Close from "../../components/icons/Close.svelte";

</script>

<div class="top-bar">
    <a href="/daily-routine" ><Close/> </a>
    <p>Create Routine</p>
</div>
<div class="create-routine">
    <form>
        <label>Routine Name</label>
        <input class="text-box" type="text">
        <label>Time</label>
        <input class="text-box" type="text">        
        <label>Choose color</label>
        <div class="colors">
            <span style="background:hsl(50, 98%, 50%)" class="color-active"></span>
            <span style="background:hsl(105, 69%, 30%)"></span>
            <span style="background:hsl(230, 55%, 40%)"></span>
            <span style="background:hsl(180, 69%, 30%)"></span>
            <span style="background:hsl(70, 69%, 50%)"></span>
            <span style="background:hsl(265, 100%, 81%)"></span>
            <span style="background:hsl(30, 100%, 40%)"></span>
            <span style="background:hsl(10, 75%, 40%)"></span>
            <span style="background:hsl(44, 100%, 80%)"></span>
            <span style="background:hsl(351, 100%, 67%)"></span>
            <span style="background:hsl(70, 69%, 50%)"></span>
            <span style="background:hsl(70, 69%, 50%)"></span>
            <span style="background:hsl(70, 69%, 50%)"></span>
            <span style="background:hsl(70, 69%, 50%)"></span>
            <span style="background:hsl(70, 69%, 50%)"></span>
        </div>
        <br>
        <input class="submit-button" type="submit" value="Create Routine">
    </form>
</div>
<style>
.create-routine {
    padding: 20px;
    padding-top: 68px;    
    
}

.create-routine label {
    font-weight: 600;
    font-size: 12px;
}
input {
    width: 100%;
}
.colors {  
    overflow: auto;
  white-space: nowrap;
}
.colors span {
width:32px;
height: 32px;
background: green;
border-radius: 50px;
margin-right: 12px;
display: inline-block;
}
/* width */
::-webkit-scrollbar {
height: 6px;
 
}

/* Track */
::-webkit-scrollbar-track {
  background: #ffffff; 
}
 
/* Handle */
::-webkit-scrollbar-thumb {
  background: #2ede7f; 
  border-radius: 50px;
}

/* Handle on hover */
::-webkit-scrollbar-thumb:hover {
  background: #410d85; 
}
.submit-button {
    border: none;
    background: #2ede7f;
    border-radius: 2px;
    font-weight: 600;
    color: var(--dark);
    padding-top: 9px;
    padding-bottom: 9px;
}
.text-box {
    border: none;
    border-bottom: 2px solid #2ede7f;
}
.text-box:focus {
    outline: none;
}
.color-active {
    border: 6px solid black;
}
</style>