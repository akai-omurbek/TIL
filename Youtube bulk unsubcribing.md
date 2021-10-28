The instructions, idea and means were taken from this [post](https://stackoverflow.com/questions/48874382/how-to-unsubscribe-from-all-the-youtube-channels-at-once/48874466). The necessity was 100% mine.

I've encountered the need to somehow step up my content consumption game. One of the steps included syncing my subscriptions from Youtube with the `newsboat` utility. However, my subscriptions list was too long, and I remember the last time I tried to tidy it up was too exhausting. 

I turned to internet and it helped. So, to get rid of all the subscriptions (to subscribe anew) you need:

1. Go to your [subscriptions page](https://www.youtube.com/feed/channels). 

2. Reach the console. In Qutebrowser this can be achieved by typing: `:devtools`. 

3. Scroll to the botton of the console log and enter the following script:
```  
  var i = 0;

  var myVar = setInterval(myTimer, 3000);

  function myTimer () {

      var els = document.getElementById("grid-container").getElementsByClassName("ytd-expanded-shelf-contents-renderer");

      if (i < els.length) {

          els[i].querySelector("[aria-label^='Unsubscribe from']").click();

          setTimeout(function () {

              var unSubBtn = document.getElementById("confirm-button").click();

          }, 2000);

          setTimeout(function () {

              els[i].parentNode.removeChild(els[i]);

          }, 2000);

      }

      i++;

      console.log(i + " unsubscribed by YOGIE");

      console.log(els.length + " remaining");

  } 
```
4. Wait for the script to finish!
