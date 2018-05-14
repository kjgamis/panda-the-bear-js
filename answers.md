## Part 1: Hacking Panda the Bear's Resume

1. Select the element that contains the profile image (hint: look for the class). Change the `src` attribute so it points to a picture of your choosing instead.

``` Javascript
var image = document.querySelector('img');
image.src = 'https://placebear.com/200/300';
```

PROTIP: use the inspector to learn the dimensions of the current profile image and use a placeholder image service such as Place Bear to get an image of the same size.

1. Use the same approach to select the element that contains the photo of the sky and change the src attribute to another picture URL of your choosing.

``` Javascript
var clouds = document.querySelector('.photography');
clouds.src = 'https://picsum.photos/200/300/?random';
```

2. Select the heading that says "Panda the Bear" and change it to your own name.

``` Javascript
document.querySelector('.bio-info-value').innerText = 'Karen'
```

3. Select the heading that says "Employment" and change it to something else. (hint: use a descendant selector)

``` Javascript
document.querySelector('#employment .info-title').innerText = 'Unemployment'
```

4. Change the colour of the body.

``` Javascript
document.body.style.backgroundColor = "red";
document.querySelector('body').style.backgroundColor = 'blue'
```

5. Change the colour of each element using the highlight class. Use a for loop to do this.

``` Javascript
highlight.forEach ( function(element) {
    element.style.color = 'blue' });
```

6. Change the font family of the h1 to 'monospace'.

``` Javascript
document.querySelectorAll('h1').forEach( function(mono) { mono.style.fontFamily = 'monospace'});
```

7. Find a way to select the round icons in the sidebar and then change their colour.

``` Javascript
document.querySelectorAll('.action-icon-bg').forEach( function(icon) { icon.style.backgroundColor = 'red'});
```

8. Scroll down to the contact form. Change the placeholder attribute of the name field to "identify yourself".

``` Javascript
document.querySelector('#name').placeholder = 'Identify Yourself';
```

9. Change the placeholder attribute of the message field to "state your business".

``` Javascript
document.querySelector('#message').placeholder = 'State your Business';
```

10. Give the name field a "value" attribute of "your nemesis".

``` Javascript
document.querySelector('#name').value = 'your nemesis';
```

11. Change the value attribute of the email field to "koalathebear@gmail.com".

``` Javascript
document.querySelector('#email').value = "koalathebear@gmail.com";
```

12. Change the value of the submit button on the contact form to "En garde!".

``` Javascript
document.querySelector('#submit').value = "En garde!";
```

13. We should stop Koala from sending an email to Panda that they might regret! Find a way to disable the submit button (hint: familiarize yourself with the disabled attribute).

``` Javascript
document.querySelector('#submit').disabled = true;
```

14. We should help Panda protect their privacy by erasing their personal details from the sidebar.

``` Javascript
var element = document.querySelector('ul');
element.parentNode.removeChild(element);
```

## Part 2:  
### Removing Elements from the DOM

1. Panda the Bear is lying about their skills! Take the "time travel" skill off the page to satisfy your personal sense of justice. Use your googling and docs-skimming skillz to find a jQuery function that will allow you to remove elements from the DOM. (hint: there are multiple ways of doing this, but the parent() function might be useful when it comes to selecting the right element)

``` Javascript
var timeTravel = document.querySelector('#time-travel');
timeTravel.parentNode.remove();
```

### Adding Elements to the DOM
1. That drawing of Pikachu is really cute. Let’s duplicate it using cloneNode() and insert it at the bottom of the `.portfolio-container` using insertAdjacentHTML() or appendChild().

``` Javascript
var pikachu = document.getElementById('right-image').querySelector('img');
var clone = pikachu.cloneNode();
document.querySelector('.portfolio-container').appendChild(clone);
```

2. Wow, that was so satisfying I think we should do it 10 more times. Use a `for` loop to help you do this.

```Javascript
for (p =0; p < 11 ; p++){ var pikachu = document.getElementById('right-image');
var clone = pikachu.cloneNode(true); document.querySelector('.portfolio-container').appendChild(clone) }
```

3. Let’s add a message about when the page was last updated. We'll do this by appending a new `<li>` element to the `<ul>` in the sidebar (you might need to refresh the page to bring back the list items that we emptied out earlier).

``` Javascript
var listItem = document.createElement('li');
var leftSpan = document.createElement('span');
var lastUpdated = document.createTextNode('Page last updated on');
leftSpan.appendChild(lastUpdated);
listItem.appendChild(leftSpan);
```
