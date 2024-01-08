# Tool Learning Log

Tool: **Kaboom**

Project: **Fighting game**

---

11/20/2023:
* How to loop:
```js
loop(1, () => {
    // add tree
    add([
        rect(48, 64),
        area(),
        outline(4),
        pos(width(), height() - 48),
        anchor("botleft"),
        color(255, 180, 255),
        move(LEFT, 240),
        "tree",
    ]);
});
```

* https://www.youtube.com/watch?v=4OaHB0JbJDI (video on kaboom)

* https://www.gamedesigning.org/learn/kaboom-js/ (article on kaboom)

* collision:
```js
 kaboom({
	scale: 2,
})

// Load assets
loadSprite("bean", "/sprites/bean.png")
loadSprite("ghosty", "/sprites/ghosty.png")
loadSprite("grass", "/sprites/grass.png")
loadSprite("steel", "/sprites/steel.png")

// Define player movement speed
const SPEED = 320

// Add player game object
const player = add([
	sprite("bean"),
	pos(80, 40),
	color(),
	rotate(0),
	// area() component gives the object a collider, which enables collision checking
	area(),
	// area({ shape: new Polygon([vec2(0), vec2(100), vec2(-100, 100)]) }),
	// area({ shape: new Rect(vec2(0), 12, 120) }),
	// area({ scale: 0.5 }),
	// body() component makes an object respond to physics
	body(),
])

// Register input handlers & movement
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

onKeyDown("q", () => {
	player.angle -= SPEED * dt()
})

onKeyDown("e", () => {
	player.angle += SPEED * dt()
})

// Add enemies
for (let i = 0; i < 3; i++) {

	const x = rand(0, width())
	const y = rand(0, height())

	add([
		sprite("ghosty"),
		pos(x, y),
		// Both objects must have area() component to enable collision detection between
		area(),
		"enemy",
	])

}

add([
	sprite("grass"),
	pos(center()),
	area(),
	// This game object also has isStatic, so our player won't be able to move pass this
	body({ isStatic: true }),
	"grass",
])

add([
	sprite("steel"),
	pos(100, 200),
	area(),
	// This will not be static, but have a big mass that's hard to push over
	body({ mass: 10 }),
])

// .onCollide() is provided by area() component, it registers an event that runs when an objects collides with another object with certain tag
// In this case we destroy (remove from game) the enemy when player hits one
player.onCollide("enemy", (enemy) => {
	destroy(enemy)
})

// .onCollideUpdate() runs every frame when an object collides with another object
player.onCollideUpdate("enemy", () => {
})

// .onCollideEnd() runs once when an object stopped colliding with another object
player.onCollideEnd("grass", (a) => {
	debug.log("leave grass")
})

// .clicks() is provided by area() component, it registers an event that runs when the object is clicked
player.onClick(() => {
	debug.log("what up")
})

player.onUpdate(() => {
	// .isHovering() is provided by area() component, which returns a boolean of if the object is currently being hovered on
	if (player.isHovering()) {
		player.color = rgb(0, 0, 255)
	} else {
		player.color = rgb()
	}
})

debug.inspect = true
```


11/27/2023:
* How to adjust sprite size:
```js
kaboom({
	// without specifying "width" and "height", kaboom will size to the container (document.body by default)
	width: 200,
	height: 100,
	// "stretch" stretches the defined width and height to fullscreen
	// stretch: true,
	// "letterbox" makes stretching keeps aspect ratio (leaves black bars on empty spaces), have no effect without "stretch"
	letterbox: true,
})

loadBean()

add([
	sprite("bean"),
])

onClick(() => addKaboom(mousePos()))
```

* How to add gravity:
```js
kaboom()

// Load assets
loadSprite("bean", "/sprites/bean.png")

// Set the gravity acceleration (pixels per second)
setGravity(1600)

// Add player game object
const player = add([
	sprite("bean"),
	pos(center()),
	area(),
	// body() component gives the ability to respond to gravity
	body(),
])

onKeyPress("space", () => {
	// .isGrounded() is provided by body()
	if (player.isGrounded()) {
		// .jump() is provided by body()
		player.jump()
	}
})

// .onGround() is provided by body(). It registers an event that runs whenever player hits the ground.
player.onGround(() => {
	debug.log("ouch")
})

// Add a platform to hold the player
add([
	rect(width(), 48),
	outline(4),
	area(),
	pos(0, height() - 48),
	// Give objects a body() component if you don't want other solid objects pass through
	body({ isStatic: true }),
])

add([
	text("Press space key", { width: width() / 2 }),
	pos(12, 12),
])
```

12/4/2023:
* https://www.youtube.com/watch?v=XjnvEw-iFDA (step by step tutorial about guy making an action game using kaboom.js)

* How to initialize kaboom (put this in .html file):
```html
<script type="module">

import kaboom from "https://unpkg.com/kaboom@3000.0.1/dist/kaboom.mjs";

kaboom();

add([
    text("hello"),
    pos(120, 80),
]);

</script>
```

1/8/2024:
* Article covering the basics followed with a video on how to make Super Mario, Zelda, and Space Invaders with Kaboom.js:
https://www.freecodecamp.org/news/how-to-build-mario-zelda-and-space-invaders-with-kaboom-js/ 

<!--
* Links you used today (websites, videos, etc)
* Things you tried, progress you made, etc
* Challenges, a-ha moments, etc
* Questions you still have
* What you're going to try next
-->
