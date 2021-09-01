# Useful Things

This is where I'll put several useful formatting things that you'll probably want to use eventually.


Formatting for commands, listeners, inhibitors, and tasks
```ts
import { BotThing } from '../lib/extensions/BotThing';

export default class className extends BotThing {
	constructor() {
		super('id', {
			
		})
	}

	public async exec() {
		console.log('Hello!')
	}
}
```
Of course, you'll replace all mentions of `BotThing` with `BotCommand`, `BotListener`, `BotInhibitor`, or `BotTask`.
