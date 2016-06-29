# jQuery-clickClock

**jQuery** plugin that force an input (type text) to reicive a TIME value **HH:MM** (hours : minutes). Nothing else. Easy to use, and user-friendly. Simply click on a virtual clock OR fill the form with the num keypad. Please consider the following html :

    <input type="text" value="00:00" id="foo">

To force theses inputs to receive a HH:MM value, just insert :

    <script type="text/javascript" src="script-clickclock.js"></script>
    <script type="text/javascript">
        var clickClok1 = $("#foo").clickClock();
        // or (with all options)
        var clickClok2 = $("#foo").clickClock({
                dimClock	: 300,
                thickClock	: 10,
                stepHour	: 1,
                stepMinut	: 5
        });
    </script>
for a quick explaination,
    dimClock   : size of the clock (100 <= x <= 800)
    thickClock : size of the border of the clock (0 <= x <= 50)
    stepHour   : step between the hours (1 <= x <= 12), better keep 1.
    stepMinute : step between the minutes (1 <= x <= 60), better keep 5/10/15

once the plugin is launched, at any moment you can access to this : methods

    clickClok1.focus();	// put the focus on $("#foo1") & prepare/show the clock
    clickClok1.close();	// close the current clock of $("#foo1") if opened
    clickClok1.closeAll();	// close all the opened clocks from the current document. note that you can call this function on any clickclock.

When you call the plugin on a input, you can personalise few values. The rest are considered as defaults values, that can be edited on the beginnig of the JS file :

    var	sizeDefaultBox = 200;				// dimensions of the box containing the clock, in pixels. Have to be between 100 and 800 px.
    var	thickDefaultClock = 5;				// thickness of the edge of the clock. Have to be between 0 and 50 px.
    var	hourDefaultStep = 1;				// the step between the displayed hours of the clock. Have to be between 1 and 12.
    var	minuteDefaultStep = 5;				// the step between the displayed minutes of the clock. Have to be between 1 and 60.
    var	linkCSS = "clickclock.css";             	// link of the attached CSS file
    var	am = "morning";					// text to display for AM / morning
    var	pm = "afternoon";				// text to display for PM / afternoon
    var	closeMessage = "close";				// text to display for the X (close) button
    var	questionMessage = "";				// text to display for the ? button
    var	formatAMPM = true;				// format 24h (=true) vs. 12h (=false)
    var	isAnim = true;					// when closing the clock, put a brief animation (=true), or not (=false)

The plugun is dealing with the text of the input. You cant write letters. Only two pairs of numbers.


### Ideas of upgrade :

 - add methods like clickClok1.setTime("14:50");
 - this clock is made to be with the 24-hours format. I started to write a 12-hours versions, but ... I will finish it if someone really needs ;)
 - the clock don't dissapear if we click elsewhere else, or if any non-clickclock input is selected.


Any comments or suggestions are welcome !
Cheers
