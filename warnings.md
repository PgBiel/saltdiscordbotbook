#Warnings
Warnings are a simple yet useful way of punishing. A light punishment, to get ready for a higher one in case of continuous rule break. See the article ["Setting up Moderation"](./setting-up-moderation.md) to set up warns.

##Permissions
```js
warn: global.warn,
clearwarns: global.clearwarns
```
##About
Warnings are, as I said above, a light punishment, to make the person aware of their rule break. I recommend you set it up with the command [`+setwarns`](./setwarns.md) (See in-depth explanation at ["Setting up Moderation"](./setting-up-moderation.md)), so you can set an automatic punishment for reaching a certain number of warnings.

##Syntax
Very easy to use...Indeed.

`+warn @User#1234 reason`

Yup. It's that simple.

##Clearing Warns
When you warn someone, please keep in mind that if you didn't set up warns with `+setwarns`, the warns will **not** be stored, because, in a general way, there's no need for that. When you setup the limit, it ***needs*** to be stored to know if they reached the limit or not. So, `+clearwarns` will not do anything if it is not set up.

Now, here comes the utility of `+clearwarns`. Let's say you warned someone. Nice. But, then, suddenly, a moderator was already rushing to warn and they warn for the same reason, accidentally, while you already had warned. No problem! `+clearwarns @User#1234` will solve it. Then you warn again and it will only had counted as one warning. Neat!