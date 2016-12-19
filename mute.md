#Mute
##Permissions
###Mute
```js
mute = global.mute;
```
###Pmute
```js
pmute = global.pmute;
```
###Unmute
```js
unmute = global.unmute;
```
###Mutetime
```js
mutetime = global.mutetime; //Default
```
##About
Muting is a common task for moderators. Know that guy that always joins the server and keeps spamming like a crazy bones? So. We've got you covered. Muting is one of the things that Salt specializes at, but let's go step-by-step, and also do some troubleshooting at the end.

##Mute and Pmute
Those are the muting commands: `+mute` and `+pmute`. Let's understand them.

`+mute` mutes a given user (mentioned!) for a specific amount of time, provided as a number (for minutes) OR Date String, while `+pmute` mutes permanently. Let's understand Date Strings, as those are common questions.
###Date Strings
Date String is something people get confused at, so here's a **VERY IMPORTANT** note about it. IT MUST BE PUT BETWEEN DOUBLE QUOTES. (Only the case for this command. For the [remind](./remind.md) command, it uses brackets _{}_ instead)

Now, how to use date strings? Let's look at the mute syntax.

`+mute @User#1234 time reason`

Good, a pretty simple syntax. At time, you write a number to use it in minutes, OR a Date String. To use a number, let's give an example:

`+mute @User#1234 15 Spamming`

There, we just muted User for 15 minutes, with reason of "Spamming". But how do we use Date Strings?
Their format is simple (AND THE ORDER MUST BE FOLLOWED): ?w _(for weeks)_, ?d _(days)_, ?h _(hours)_, ?m _(minutes)_ and ?s _(seconds)_.

Unfortunately, you can't write minutes, seconds, etc, you have to write it like that. So, let's say a person did some really bad spam and you want to mute them for 1 day, 7 hours, 2 minutes and 1 second. Syntax:

`+mute @User#1234 "1d 7h 2m 1s" Massive Spam`

Notice the double quotes around it. Yes they are required, even if you are writing just `1d`, for example. And the point of date strings are simple, to not have to use [calculators](./calc.md) to calculate the amount of minutes to mute for! Neat, right?
###Pmute
Pmute is pretty much simple. You do the command, and the user affected is muted ***__permanently__***. Oh, but don't worry. They can be unmuted, like always. Syntax? Simple enough.

`+pmute @User#1234 reason`

Yes, very simple. Simple enough for the eyes...and for your fingers.
###Unmute
Unmute is also as simple as Pmute. It's actually the exact same syntax:

`+unmute @User#1234 reason`

Simple, simple, simple. Simplicity is key here. That's the point of Salt: To ease your lives. ;)
###Mutetime
Mutetime, also in category of moderation, is just to get the time left muted for you or someone else. Writing just `+mutetime` will return your own time left, while writing `+mutetime @User#1234` will return the time left muted for said user, if they are muted, that is.
##Troubleshooting
Common trouble that people have at muting is...

1. **Salt doesn't give the SaltMuted role for some reason.**
For that case, you need to check two things: One if the bot can manage roles, and two if the SaltMuted role is ***UNDER*** Salt's highest role. Believe me or not, but this **IS** a common issue.

2. **Muted people are speaking normally and fluently.** The most common problem that leads to this issue is that people give user permission overwrites at channels. If you're going to give user permission overwrites, **don't** tick the permission _Send Messages_, that makes it bypass SaltMuted always. Another problem is that a role higher than SaltMuted has _Send Messages_ ticked - check for that. And the less common problem here is that they have _Administrator_ permission. So check for those 3 things!