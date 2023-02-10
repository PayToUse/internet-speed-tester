# Internet Speed Tester
A tool that allows you to test your internet's real speed and see the results of the test

# Scripts Used
This tool uses `JavaScript` which contains functions that makes the result show up.

# Script Build
1. To make the script for your project, simply copy this code and paste it to your `JavaScript` or `.js` file:
```
        function runSpeedTest() {
            var startTime,
            endTime;
            var download = new Image();
            download.onload = function () {
                endTime = (new Date()).getTime();
                showResults();
            }
            startTime = (new Date()).getTime();
            var cacheBuster = "?nnn=" + startTime;
            download.src = "https://www.randomimage.com/images/cat.jpg" + cacheBuster;
            function showResults() {
                var duration = (endTime - startTime) / 1000;
                var bitsLoaded = 524288 * 8;
                var speedBps = (bitsLoaded / duration).toFixed(2);
                var speedKbps = (speedBps / 1024).toFixed(2);
                var speedMbps = (speedKbps / 1024).toFixed(2);
                document.getElementById("speed-test-results").innerHTML = speedMbps + " Mbps";
            }
        }
```

2. Once you made the script, simply put a `script` tag to your `.html` file and locate for the path to your script you have made:
```
src="(the path to your script)"
```

3. After that, make a `button` and put this code on it:
```
onclick="runSpeedTest()"
```

4. Once you put it, test it to see if it's working properly, and if it's working, it means you followed the instructions, but if it's not, *it means you had put a mistake on something*

# Note
When the button is pressed, the tool will use your internet to download the target file, so it will take some time until the test is done, so that the results will come and show up to the page.
