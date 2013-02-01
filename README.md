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
