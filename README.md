# Hack for typeracer.com
A browser based hack for typeracer.com. With this cheat you can achieve your dream type speed and win every freaking match. You can choose your own speed for your purpose.

### Clarifications
It has been made purely for educational purposes. Author will not be responsible for any damages. 😁


## Direction of use

1. Enter the game.
2. Open developer tools. In windows with Firefox or Chrome browser you can press Ctrl + Shift + I.
3. With console tab selected, paste the following code.

```
let text = "";

function loadTexts() {
    let divs = document.querySelectorAll("td > div > div > span");

    let maxLength = 0;

    for (let i=0; i<divs.length; i++) {
        // console.log("i: " + i + " msg:" + divs[i].textContent.trim());
        let txt = divs[i].textContent.trim();
        if (txt.includes(":")) // eg,  1:20 is a time string
            continue;
        if (txt.split(" ").length > 1)
            txt = " " + txt;
        text += txt;
    }

    console.log("\n" + text);
}


loadTexts();


const inpt = document.getElementsByClassName("txtInput")[0];
let offset = 0;


document.addEventListener("keydown", function(e) {
    if (e.keyCode === 13) {
        // enter key clears the text
        text = "";
        offset = 0;
        return;
    }
    if (e.keyCode === 8) {
        // backspace
        if (inpt.value.length > 0) {
            inpt.value = inpt.value.substring(0, inpt.value.length-2);
            offset--;
        }
        return;
    }
    inpt.value += text[offset++];
});
```
4. Do not clik on the input area. Wait for the timer.
5. Press any key. Move mouse over the input area. 
6. If something went wrong then refresh the page and try again.
7. For vido demonstration visit: https://www.youtube.com/watch?v=2294vvGtQ9c


### Some tips
From developer console you can open an inspect tab and just copy the text to by typed. You can then just paste the text. But to get the desired speed and not to ring an alraming bell just go with the above mentioned method.
