# Entry 2
##### 12/12/2023

I followed a lot of [Youtube](https://www.youtube.com/) tutorials on [Kaboom](https://kaboomjs.com/) to continue learning the tool:

* [Lets Build an Action Game Using JavaScript with Kaboom.js 💥 (from scratch)](https://www.youtube.com/watch?v=XjnvEw-iFDA)
* [https://www.youtube.com/watch?v=2nucjefSr6I](https://www.youtube.com/watch?v=2nucjefSr6I)
* [#1 INTRODUCTION | KABOOM JS TUTORIAL + PROJECTS COMPLETE COURSE](https://www.youtube.com/watch?v=hbD8_GXGIiE&list=PLu9YVdNl8Gec9Tn_YWS9XMEy7UCdOi-FQ)

I tinkered with the tool more, learning the components I need that best suits the game.

```js
loadSprite("guy", "/sprites/guy.png")

setGravity(800)

const player = add([
	sprite("guy"),
	pos(center()),
	area(),
	body(),
])

onKeyPress("space", () => {
	if (player.isGrounded()) {
		player.jump()
	}
})

player.onGround(() => {
	debug.log("ow")
})
```

This code is to establish gravity in a game. This is needed so the characters stick to the fighting grounds. The number in `setGravity(800)` can be set differently to change the force of the gravity. This is great becasuse it can be adjusted to better fit the pace of the game. This code can also be paired up with the code to jump optimal mechanics.

```js
add([
	rect(width(), 48),
	outline(4),
	area(),
	pos(0, height() - 48),
	body({ isStatic: true }),
])
```

This is code add a simple platform for the sprites to stand on. This can probably be designed to look better but it works as it is right now.

I'm in step 2 and 3 of EDP, research and brainstorming. Step 2 becasue I am still discovering videos and tutorials on kaboom.js, and step 3 because I'm brainstorming on how the game will come together. My Freedom Project goal for winter break is to tinker with more code and combine them to get a better feel of kaboom.js. 

[Previous](entry01.md) | [Next](entry03.md)

[Home](../README.md)