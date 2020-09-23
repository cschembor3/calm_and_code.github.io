---
layout: post 
title: About
permalink: /about/
---

This is a personal blog for things related to software engineering, and otherwise.

<h4 id="title">Years of experience</h4>
<div id="devExp">
    <div id="devExpBar"></div>
</div>

<div id="one-year">
    <div class="divider" id="one-year"></div>
    <div class="year" id="one-year">
        <p>1</p>
    </div>
</div>
<div id="two-years">
    <div class="divider" id="two-years"></div>
    <div class="year" id="two-years">
        <p>2</p>
    </div>
</div>
<div id="three-years">
    <div class="divider" id="three-years"></div>
    <div class="year" id="three-years">
        <p>3</p>
    </div>
</div>
<div id="four-years">
    <div class="divider" id="four-years"></div>
    <div class="year" id="four-years">
        <p>4</p>
    </div>
</div>

<style>
#devExp {
    border: 3px solid red;
    border-radius: 8px;
    position: absolute;
    bottom: 250px;
    right: 25%;
    left: 25%;
    z-index: -1;
}

#devExpBar {
    height:  35px;
    background-color: green;
    position: relative;
    z-index: -1;
}

.divider {
    border-left: 5px solid grey;
    height: 60px;
    position: absolute;
    bottom: 240px;
    z-index: 100;
    opacity: 0.5;
    border-radius: 4px;
}

.year {
    bottom: 200px;
    position: absolute;
}


#one-year {
    left: 35%;
}

#two-years {
    left: 45%;
}

#three-years {
    left: 55%;
}

#four-years {
    left: 65%;
}

#title {
    left: 25%;
    bottom: 280px;
    position: fixed;
}

</style>

<script>
    function calculateExperience() {
        let startDate = new Date(2018, 7, 2)
        let currDate = Date.now()
        let experience = currDate - startDate.getTime()
        return experience
    }

    function animateProgressBar() {
        let progBar = document.getElementById("devExpBar")
        let intervalId = setInterval(inc, 20)
        let percentageToFill = getExpBarPercentage()
        var percentageFilled = 0
        function inc() {
            if (percentageFilled > percentageToFill) return
            progBar.style.width = percentageFilled + "%"
            percentageFilled++
        }
    }

    function getExpBarPercentage() {
        // 5 years of exp - max of the percentage bar
        let fullExp = 5 * 365 * 24 * 60 * 60 * 1000
        console.log("Full exp: " + fullExp)
        let currExp = calculateExperience()
        console.log("Curr exp: " + currExp)
        console.log(currExp / fullExp)
        let expBarPercentage = 100 * (currExp / fullExp)
        console.log(expBarPercentage)
        return expBarPercentage
    }

    animateProgressBar()
    //getExpBarPercentage()
</script>
