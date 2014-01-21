Chrome Security Issue
---------------------

Google Chrome will prevent our 3D games from running when the files are stored on our computer instead of on a web server. To get around this issue make sure Chrome is completely closed. Open a command prompt and enter the command:

```
open -a Google\ Chrome --args --disable-web-security
```

Recognize Key Presses
---------------------

Every key on your keyboard has a numeric code that represents it. We can have our program let us know when a key has been pressed. Our program can let us know when a key is pressed down, which is called the 'keydown' event. Our program can also let us know when the key is no longer pressed, which is called the 'keyup' event. Add the below code to your program and it will pop up an alert box when a key is pressed down. Experiment with this to find the numeric key codes for the arrow keys (up, down, left, and right). 

```
document.addEventListener('keydown', function(event) {
    alert(event.keyCode);
});
```

Move Avatar With Arrow Keys
---------------------------

Now that we have the key codes for the arrow keys, let's make the avatar move while we are pressing the keys. Instead of the code above that pops up an alert, use the below code instead. You will need to replace <arrow code> with the apprepriate number for each arrow key. If all goes well we should now be able to move the avatar left, right, forwards, and backwards.

```
document.addEventListener('keydown', function(event) {
    var code = event.keyCode;

    if (code == <left arrow code>)
        avatar.position.x = avatar.position.x - 5; // left

    if (code == <up arrow code>)
        avatar.position.z = avatar.position.z - 5; // up

    if (code == <right arrow code>)
        avatar.position.x = avatar.position.x + 5; // right

    if (code == <down arrow code>)
        avatar.position.z = avatar.position.z + 5; // down
});
```

Bonus: Make The Avatar Cartwheel and Flip
----------------------------------

The code to make the avatar cartwheel and flip is already in place. There are two variables on the page called isCartwheeling and isFlipping. Look in the animate() function. When those variables are set to true the avatar will cartwheel or flip. If the variables are set to false, then the avatar will stop doing what it was doing. What you need to do is add to the code that detects key presses. In addition to the arrow keys use the C key to start and stop the avatar doing cartwheels. Use the F key to start and stop the avatar doing flips.