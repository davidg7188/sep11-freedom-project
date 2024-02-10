# Entry 3
##### 2/10/24

To further learn [Kaboom](https://kaboomjs.com/) I went into [Replit](https://replit.com/~) and created a new repl with the kaboom template. The plan was to follow [this](https://www.youtube.com/watch?v=4OaHB0JbJDI&t=2s) video, which is a game development tutorial using kaboom. I followed exactly what she did but what worked for her didn't work in my repl, I always had to tweak something in the code for it to actually function. The video might have been outdated so I decided to scrap the original plan and just figure out kaboom by tinkering and using the kaboom website.

```js
loadPedit("person", "sprites/person.pedit")

add([
  sprite("person"),
  pos(20, 5),
  scale(9.0),
  area(),
  body(),
])
```

But one thing I did take away from the video was that in replit you can create your own sprite right on the website. What the video didn't say though was that you had to use `loadPedit` and `.pedit` for it to work, the video used `loadSprite` and `.sprite` but it somehow worked for them and not for me.

Another thing the video showed was making a floor entirely out of a sprite you made using levels. I tried it and was unsuccessful, but with the help of a classmate, Thomas, we made it work.

```js
loadPedit("ground", "sprites/ground.pedit")

add([
  sprite("ground"),
  "ground".width = 500,
    pos(0, height() - 48),
    outline(4),
    area(),
    body({ isStatic: true })
])

add([
  sprite("ground"),
  "ground".width = 500,
    pos(40, height() - 48),
    outline(4),
    area(),
    body({ isStatic: true })
])
add([
  sprite("ground"),
  "ground".width = 500,
    pos(80, height() - 48),
    outline(4),
    area(),
    body({ isStatic: true })
])
add([
  sprite("ground"),
  "ground".width = 500,
    pos(120, height() - 48),
    outline(4),
    area(),
    body({ isStatic: true })
])
add([
  sprite("ground"),
  "ground".width = 500,
    pos(160, height() - 48),
    outline(4),
    area(),
    body({ isStatic: true })
])
  add([
  sprite("ground"),
  "ground".width = 500,
    pos(200, height() - 48),
    outline(4),
    area(),
    body({ isStatic: true })
])
add([
  sprite("ground"),
  "ground".width = 500,
    pos(240, height() - 48),
    outline(4),
    area(),
    body({ isStatic: true })
])
add([
  sprite("ground"),
  "ground".width = 500,
    pos(280, height() - 48),
    outline(4),
    area(),
    body({ isStatic: true })
])
add([
  sprite("ground"),
  "ground".width = 500,
    pos(240, height() - 48),
    outline(4),
    area(),
    body({ isStatic: true })
])
add([
  sprite("ground"),
  "ground".width = 500,
    pos(320, height() - 48),
    outline(4),
    area(),
    body({ isStatic: true })
])
add([
  sprite("ground"),
  "ground".width = 500,
    pos(360, height() - 48),
    outline(4),
    area(),
    body({ isStatic: true })
])
add([
  sprite("ground"),
  "ground".width = 500,
    pos(400, height() - 48),
    outline(4),
    area(),
    body({ isStatic: true })
])
add([
  sprite("ground"),
  "ground".width = 500,
    pos(440, height() - 48),
    outline(4),
    area(),
    body({ isStatic: true })
])
add([
  sprite("ground"),
  "ground".width = 500,
    pos(480, height() - 48),
    outline(4),
    area(),
    body({ isStatic: true })
])
add([
  sprite("ground"),
  "ground".width = 500,
    pos(520, height() - 48),
    outline(4),
    area(),
    body({ isStatic: true })
])
add([
  sprite("ground"),
  "ground".width = 500,
    pos(560, height() - 48),
    outline(4),
    area(),
    body({ isStatic: true })
])
add([
  sprite("ground"),
  "ground".width = 500,
    pos(600, height() - 48),
    outline(4),
    area(),
    body({ isStatic: true })
])
add([
  sprite("ground"),
  "ground".width = 500,
    pos(640, height() - 48),
    outline(4),
    area(),
    body({ isStatic: true })
])
add([
  sprite("ground"),
  "ground".width = 500,
    pos(680, height() - 48),
    outline(4),
    area(),
    body({ isStatic: true })
])
add([
  sprite("ground"),
  "ground".width = 500,
    pos(720, height() - 48),
    outline(4),
    area(),
    body({ isStatic: true })
])
add([
  sprite("ground"),
  "ground".width = 500,
    pos(760, height() - 48),
    outline(4),
    area(),
    body({ isStatic: true })
])
```

With that code the ground was made out of a sprite. But surely there is a more efficient way of achieving this, unfortunately the time in class ran out to find out. Other than that I added gravity so the sprite could land on the ground.

The plan moving forward is to create a new repl and use what I learned on this test repl to further expand on the game idea. What I want to learn next about Kaboom is creating healthbars and movement for the sprites, after that I want to create a combat system so for every hit they take their healthbar goes down.

Right now I'm in steps 5 and 6 of the Engineering Design Process, creating and testing. I'm using kaboom to create and test parts of the game. Skills I used were embracing failure and communication. The video led me to a lot of wasted time and failed code but it's fine. And I communicated with a classmate to help me with my code.


[Previous](entry02.md) | [Next](entry04.md)

[Home](../README.md)