# Entry 1
##### 11/6/2023

The tool I chose is [Kaboom](https://kaboomjs.com/) because it's fast and easy to implement. For tinkering I followed some of the tutorials on the website that would help me in my overall freedom project game.

```js
kaboom()

loadSprite("figure", "/sprites/figure.png")

const SPEED = 320
const player = add([
	sprite("figure"),
	pos(center()),
])

onKeyDown("left", () => {
	player.move(-SPEED, 0)
})

onKeyDown("right", () => {
	player.move(SPEED, 0)
})

onKeyDown("up", () => {
	player.move(0, -SPEED)
})

onKeyDown("down", () => {
	player.move(0, SPEED)
})

onClick(() => {
	player.moveTo(mousePos())
})

add([
	text("Press arrow keys", { width: width() / 2 }),
	pos(12, 12),
])
```

This code is for sprite movement.

```js
onKeyPress("p", () => {
		game.paused = !game.paused
		if (curTween) curTween.cancel()
		curTween = tween(
			pauseMenu.pos,
			game.paused ? center() : center().add(0, 700),
			1,
			(p) => pauseMenu.pos = p,
			easings.easeOutElastic,
		)
		if (game.paused) {
			pauseMenu.hidden = false
			pauseMenu.paused = false
		} else {
			curTween.onEnd(() => {
				pauseMenu.hidden = true
				pauseMenu.paused = true
			})
		}
	})
```

This is for a pause menu. The idea for the project is a stick figure fighting game in the vein of "Super Smash Bros" where two players can locally fight. They both have the same move-set and the point is to figure out who is the better fighter. This a [YouTube](https://www.youtube.com/watch?v=iRXI6ThRJvM&list=PLNwtXgWIx3rgk68WwrykC7BIJ50kT6ZpS) video that helped me while tinkering.

I'm in step 2 of EDP, research. I am still researching and tinkering with my tool. A skill is "how to learn" because I had to learn a new tool by using it and researching about it. 

[Next](entry02.md)

[Home](../README.md)