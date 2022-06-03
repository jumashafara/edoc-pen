# Edoc Pen
* In this project, we step by step, create a simple codepen-like code editor that allows us to write html and do some styling to it. 
* Thats not all it renders the changes to your html or css immediately(liveserver 😀).

* You can test it out [here](https://jumashafara.github.io/edoc-pen/)

## Step 1
We begin begin by creating a basic index.html file.

```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Edoc Pen</title>
</head>
<body>
    
</body>
</html> 
```

## Step 2 
* Inside our body, we need to create two textareas, one where the HTML code code will be written, and the other for CSS.
* We also need a div with class= "output" where our output will be rendered.

```
<textarea name="" id="html-text-area" cols="30" rows="10"></textarea>
   <textarea name="" id="css-text-area" cols="30" rows="10"></textarea>
   <div class="output"></div>
```

* Let's add an empty style tag inside the head tag, this is where our styles from the CSS text area will be send

```
<style></style>
```
Our full html code should look like this now

```
    <!DOCTYPE html>
    <html lang="en">
    <head>
        <meta charset="UTF-8">
        <meta http-equiv="X-UA-Compatible" content="IE=edge">
        <meta name="viewport" content="width=device-width, initial-scale=1.0">
        <title>Edoc Pen</title>
        <style></style>
    </head>
    <body>
        <textarea name="" id="html-text-area" cols="30" rows="10"></textarea>
        <textarea name="" id="css-text-area" cols="30" rows="10"></textarea>
        <div class="output"></div>
    </body>
    </html>
```
If we open our html file in a browser, we should have two text areasl. 

![visible text areas](/images/output1.jpg)

## Step 3
Now we need to connect the text areas to the style tag and output div so that we can have something functioning. We will do this with a few lines of javascript put in a script tag just above the closing body tag, simply explained below

```
    <script>
        // Each variable in the first array will be assigned the 
        // corresponding value in the second array
        const [html_text_area, css_text_area, style, output] = 
                    [
                        document.querySelector('#html-text-area'),
                        document.querySelector('#css-text-area'),
                        document.querySelector('#output'),
                        document.querySelector('style')
                    ]
        
        html_text_area.addEventListener('keyup', e => {
            // lets first stop all natural outcomes related to this event
            e.preventDefault()

            // pass the value from the html text area to output div 
            output.innerHTML = html_text_area.value
        })

        css_text_area.addEventListener('keyup', e => {
            // lets first stop all natural outcomes related to this event
            e.preventDefault()

            // pass the value from the css text area to style tag
            style.innerHTML = css_text_area.value
        })
    </script>
```

With that, should now be having a working Edoc Pen 

The full code is as below

```
    <!DOCTYPE html>
    <html lang="en">
    <head>
        <meta charset="UTF-8">
        <meta http-equiv="X-UA-Compatible" content="IE=edge">
        <meta name="viewport" content="width=device-width, initial-scale=1.0">
        <title>Edoc Pen</title>
        <style></style>
    </head>
    <body>
        <textarea name="" id="css-text-area" cols="30" rows="10"></textarea>  
        <textarea name="" id="html-text-area" cols="30" rows="10"></textarea>
        <div id="output"></div>

        <script>
            // Each variable in the first array will be assigned the 
            // corresponding value in the second array
            const [html_text_area, css_text_area, style, output] = 
                        [
                            document.querySelector('#html-text-area'),
                            document.querySelector('#css-text-area'),
                            document.querySelector('#output'),
                            document.querySelector('style')
                        ]
            
            html_text_area.addEventListener('keyup', e => {
                // lets first stop all natural outcomes related to this event
                e.preventDefault()

                // pass the value from the html text area to output div 
                output.innerHTML = html_text_area.value
            })

            css_text_area.addEventListener('keyup', e => {
                // lets first stop all natural outcomes related to this event
                e.preventDefault()

                // pass the value from the css text area to style tag
                style.innerHTML = css_text_area.value
            })
        </script>
    </body>
    </html>
```

As simple as that, now we can write our codepens at our leisure time 😀.
Next steps would include designing our text areas so that they look more code-like, you could add a font consolas and a darker background
I choose not to do that as i want this article shorter, thanks if you read up to here.

Follow me if you like this so that you don't miss out on the next exciting stuff

