# Setting up Moderation
Moderation generally works fine without setting up anything, but it's better that you read the contents of this article to make moderation good for your server! Now, you ready?

## I'm ready!
Good. So, to start, mute, kick and ban are commands that work perfectly without any setup, you should check them out at the articles below this one at this category.

Now, [warnings](./warnings.md) are the big deal. Sure, they sound pretty simple. But they require Moderator Role (see [saltrole](/saltrole.md)) to be used OR permission node `global.warn`.

Once Moderator and Administrator roles are set up, or people have `global.warn`, then we can get started. The true warning configuration. It's the command [`+setwarns`](./setwarns.md). It's pretty much simple: You can set a limit, and a punishment for reaching the limit. With no configuration of warns, any warnings aren't stored internally and therefore the command [`+clearwarns`](./warnings.md) does nothing. If you set a limit, however, they will be stored, and you can clear their warns with that command.

### How to use `+setwarns`?
It's pretty simple. Let me provide you with examples.

`+setwarns limit 5` <- By doing this, you are setting the limit of warnings to 5: After 5 warnings, they receive a bigger punishment set below.

`+setwarns punishment kick` <- This sets the punishment of reaching the limit of warnings to Kick: The member gets kicked from the server.

`+setwarns punishment mute 10` <- This sets the punishment of reaching the limit of warnings to a 10-minute mute.
Warning: This does not have the special mute syntax of weeks, days, hours, minutes, seconds (see [mute](./mute.md)). It only accepts a number which is the amount of minutes (You can always use [calc](./calc.md) to calculate the amount of minutes!) that the member gets muted for.

### How about Action Logs?
A common mistake that people make, is to think that, in Salt, action logs and _(advanced)_ logs are the same thing. They're not. Action logs log moderation commands done with Salt ([`+mute`](/mute.md), [`+kick`](./kick.md), [`+ban`](./ban.md) and [`+warn`](./warn.md)), while _(advanced)_ logs log **EVERYTHING**. Yup, ***EVERYTHING*** that happens in the server gets logged, in advanced logs: Messages deleted, messages edited, and more. Check out the [`+logs`](./logs.md) and [`+actionlogs`](./actionlogs.md) commands for more information!

###And this is it?
Yup! Congrats! You've set up moderation. ;)