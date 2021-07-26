# djs-akairo-example

follow https://github.com/TymanWasTaken/akairo-typescript-template until you are finished


once you are done, make the bot <a:trollformation:865717171539542016>

­

jkjk, make `src/inhibitors` and `src/listeners`

inhibitors are not important, just put make a file in `src/inhibitors` called `blacklist.ts`, and put the following in it

```ts
import { BotInhibitor } from '../extensions/BotInhibitor';

module.exports = class BlacklistInhibitor extends BotInhibitor {
	constructor() {
		super('blacklist', {
			reason: 'blacklist'
		});
	}

	async exec(message) {
		const blacklist = []
		return blacklist.includes(message.author.id)
	}
}
```
I'm assuming you know basic TS, if you don't then go learn that. I can't really explain inhibitors as much as I can explain listeners and commands, because I've never found them to be that useful.

All they do is take a message, and return a boolean. If it's true, then the message never gets passed through to the command handler, essentially making them really good for blacklists. If you want to use this inhibitor for actually blacklisting someone, just add their ID to `const blacklist = []`

```ts
const blacklist = ['322862723090219008', '496409778822709251']
```

For listeners, read https://github.com/Zordlan/djs-akairo-example/blob/main/listeners.md