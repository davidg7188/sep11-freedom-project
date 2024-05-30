# Entry 4
##### 3/14/2024

I followed the plan from my last blog entry and created a new repl for the game. For the floor, instead of using a sprite and copy pasting it until it ran through the whole screen, I used the [kaboom website](https://kaboomjs.com/) for a more efficient way on created a solid ground:

```js
add([
  rect(width(), 48),
  outline(4),
  area(),
  pos(0, height() - 48),
  body({ isStatic: true }),
])
```

For movement and jumping I followed through with using mostly tinkering and using the website again, which was a great help and worked perfectly:

```js
onKeyPress("space", () => {
  if (player.isGrounded()) {
    player.jump()
  }
})

onKeyDown("left", () => {
  player.move(-SPEED, 0)
  player.flipX = true
    if (player.isGrounded() && player.curAnim() !== "run") {
      player.play("run")
    }
  })

onKeyDown("right", () => {
  player.move(SPEED, 0)
})
```

With the movement down I wanted to try a simple running animation, so I created some animation frames on the `.pedit` and wrote some code to activate the animation following a tutorial on the kaboom website:

```js
loadPedit("kratos", "sprites/kratos.pedit", {
              sliceX: 3,
        anims: {
              "run": {
                from: 0,
                to: 3,
                speed: 10,
                loop: true,
              },
            },
          })
```

This was a real challenge, every time I ran the code an error would appear and I couldn´t figure out why. Making the animation run successfully is the main thing I want to fix in the next freedom project class. Moving forward I want to keep with the original plan of greating healthbars and simple attacks.

I am in steps 5,6, and 7 of EDP(Engineering Design Process). I am still creating and testing, but I´m also improving on previous code, like finding a better way to create a floor. Two skills I used were debugging and creativity. The animation code required debugging and although I couldn´t completely fix it, I still tried and am close to solving the issue. And creativity was used in drawing the animation frames.

[Previous](entry03.md) | [Next](entry05.md)

[Home](../README.md)