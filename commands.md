# Basic Commands

Read `useful-things.md` for command formatting.

Make a new file in `src/commands`, and paste the example code into that file. Replace all mentions of `BotThing` with `BotCommand`.

Add `message`, with the type `Message` to the exec function.

```ts
public async exec(message: Message) {

}
```

This will, of course, not work, as you have not imported the `Message` type from `discord.js` yet ([Visual Studio Code](https://code.visualstudio.com/) can "automatically" import this for you, just hover over it, press `Quick Fix`, then `Import 'Message' from module "discord.js"`)

Change the class name and ID to whatever you want,

```ts
export default class yourNewClassName extends BotThing {
	constructor() {
		super('yourNewID', {
```

and add `aliases` as an array of strings inside the `super` function. These are what you will use to run your command.

```ts
super("yourNewID", {
  aliases: ["firstAlias", "secondAlias"],
});
```

Next, put some code inside your `exec` function. This can be whatever you want it to be. For starting out, (and making sure you didn't mess up), you can add `message.reply('Hello!')`.

```ts
public async exec(message: Message) {
    message.reply('Hello!')
}
```

<details>
    <summary>Your code should look something like this:</summary>
  
```ts
import { Message } from 'discord.js';
import { BotThing } from '../lib/extensions/BotCommand';

export default class testCommand extends BotCommand {
    constructor() {
    	super('testCommandID', {
            aliases: ['testCommand']
    	})
    }
    public async exec(message: Message) {
    	message.reply('Hello!')
    }
}
```
</details>

­

![Example](https://cdn.discordapp.com/attachments/862910706840109117/869051864728088616/unknown.png)