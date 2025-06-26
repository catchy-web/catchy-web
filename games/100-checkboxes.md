# 100 checkboxes

Do you know [One Million Checkboxes](https://onemillioncheckboxes.com/)?

This is just 100.

## The board

<div id="board">
    <input type="checkbox">
    <input type="checkbox">
    <input type="checkbox">
    <input type="checkbox">
    <input type="checkbox">
    <input type="checkbox">
    <input type="checkbox">
    <input type="checkbox">
    <input type="checkbox">
    <input type="checkbox">
    <br>
    <input type="checkbox">
    <input type="checkbox">
    <input type="checkbox">
    <input type="checkbox">
    <input type="checkbox">
    <input type="checkbox">
    <input type="checkbox">
    <input type="checkbox">
    <input type="checkbox">
    <input type="checkbox">
    <br>
    <input type="checkbox">
    <input type="checkbox">
    <input type="checkbox">
    <input type="checkbox">
    <input type="checkbox">
    <input type="checkbox">
    <input type="checkbox">
    <input type="checkbox">
    <input type="checkbox">
    <input type="checkbox">
    <br>
    <input type="checkbox">
    <input type="checkbox">
    <input type="checkbox">
    <input type="checkbox">
    <input type="checkbox">
    <input type="checkbox">
    <input type="checkbox">
    <input type="checkbox">
    <input type="checkbox">
    <input type="checkbox">
    <br>
    <input type="checkbox">
    <input type="checkbox">
    <input type="checkbox">
    <input type="checkbox">
    <input type="checkbox">
    <input type="checkbox">
    <input type="checkbox">
    <input type="checkbox">
    <input type="checkbox">
    <input type="checkbox">
    <br>
    <input type="checkbox">
    <input type="checkbox">
    <input type="checkbox">
    <input type="checkbox">
    <input type="checkbox">
    <input type="checkbox">
    <input type="checkbox">
    <input type="checkbox">
    <input type="checkbox">
    <input type="checkbox">
    <br>
    <input type="checkbox">
    <input type="checkbox">
    <input type="checkbox">
    <input type="checkbox">
    <input type="checkbox">
    <input type="checkbox">
    <input type="checkbox">
    <input type="checkbox">
    <input type="checkbox">
    <input type="checkbox">
    <br>
    <input type="checkbox">
    <input type="checkbox">
    <input type="checkbox">
    <input type="checkbox">
    <input type="checkbox">
    <input type="checkbox">
    <input type="checkbox">
    <input type="checkbox">
    <input type="checkbox">
    <input type="checkbox">
    <br>
    <input type="checkbox">
    <input type="checkbox">
    <input type="checkbox">
    <input type="checkbox">
    <input type="checkbox">
    <input type="checkbox">
    <input type="checkbox">
    <input type="checkbox">
    <input type="checkbox">
    <input type="checkbox">
    <br>
    <input type="checkbox">
    <input type="checkbox">
    <input type="checkbox">
    <input type="checkbox">
    <input type="checkbox">
    <input type="checkbox">
    <input type="checkbox">
    <input type="checkbox">
    <input type="checkbox">
    <input type="checkbox">
</div>

<script defer>
    let checkboxes = board.getElementsByTagName("input");

    for(const box of checkboxes) {
        if(Math.floor(Math.random() * 100) > 50) {
            box.checked = !box.checked;
        }
    }

    var randomTime1 = Math.floor(Math.random() * 10) + 5;
    setInterval(() => {
        let randomBoxIndex = Math.floor(Math.random() * checkboxes.length);
        checkboxes[randomBoxIndex].checked = !checkboxes[randomBoxIndex].checked;

        randomTime1 = Math.floor(Math.random() * 10) + 5;
    }, randomTime1 * 100);

    var randomTime2 = Math.floor(Math.random() * 30) + 5;
    setInterval(() => {
        let randomBoxIndex = Math.floor(Math.random() * checkboxes.length);
        checkboxes[randomBoxIndex].checked = !checkboxes[randomBoxIndex].checked;

        randomTime2 = Math.floor(Math.random() * 30) + 5;
    }, randomTime2 * 100);

    var randomTime3 = Math.floor(Math.random() * 60) + 5;
    setInterval(() => {
        let randomBoxIndex = Math.floor(Math.random() * checkboxes.length);
        checkboxes[randomBoxIndex].checked = !checkboxes[randomBoxIndex].checked;

        randomTime3 = Math.floor(Math.random() * 60) + 5;
    }, randomTime3 * 100);
</script>

## The rules

Commit your change, so others can see it!
