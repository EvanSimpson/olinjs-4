olinjs-4
========

lecture #4: style and grace

## Notes from the last homework

### Mongoose models
Alright, so now that you've got multiple models you might want to split them up into different files in your `/models` folder. This will introduce you to several fun new things

`mongoose.connect` can only be called once. You only establish one connection to your database. You want to put it in `app.configure`

```js
app.configure(function(){
  app.set('port', process.env.PORT || 3000);
  ...
  mongoose.connect(process.env.MONGOLAB_URI || 'mongodb://localhost/burgers');
});
```

But say you only have one `models.js` file that holds all your models. You should still put your `mongoose.connect` in your `app.configure`. It was my fault that I didn't put it in there as an example in the first place. I would have failed my own code review.

BUT now that you have only one `models.js` file and a bunch of models, you're going to need to export all of the different models. You need to explicitly state what is the name of each thing you're exporting

```js
module.exports.Ingredient = Ingredient;
module.exports.Order = Order;
```

### Semappphooores
Sorry, we messed up on this one. 

## Recapping what we've done
![recap](https://raw.github.com/olinjs/olinjs-4/master/images/recap.png?login=jiahuang&token=72662cb7a920eb602a67d2fc0f7b0625)

## CSS

CSS is what makes websites look pretty.  It's the difference between this:

![style](https://github.com/olinjs/olinjs-4/blob/master/twitter_tyle.png?raw=true)

and this:

![no_style](https://github.com/olinjs/olinjs-4/blob/master/twitter_no_style.png?raw=true)

For these two websites the html is the same, the Javascript running on the browser is the same, everything which went on on the server side to render this page is the same. The only difference is that one is completely lacking css styling.

So far we've been making webpages without styling, so they look alot like ugly twitter shown above. Now we're gonna start learning how to pretty them up. Take the site which you made for HW3.

![hw3 not style](https://github.com/olinjs/olinjs-4/blob/master/Screen%20Shot%202013-01-31%20at%204.58.23%20PM.png?raw=true)

Lets add some style to it!

So open up the new_ingredient.html file in this repo, and we'll just change some css attibrutes, for a few elements. To do this we'll use the chrome inspector.

1. font-size: 32px
2. text-align: center
3. font-family: Lucida Sans Unicode, Lucida Grande, sans-serif	
4. border: 4px solid black
5. border-radius: 10px
6. border: 2px solid green 
7. border: 2px solid red
8. border: none
9. padding-bottom: 12px
10. background-image: url(http://maxim061156.files.wordpress.com/2012/09/santaclaus15.jpg)

And voila! look at our beatiful website!

So this is all great and all, but refresh the page, and what happens?  All of our hard work is gone. So how do we make permanent css styles? Using a stylesheet. Fork this repo, pull it, the open up a text editor and lets make one.





