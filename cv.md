# Junior Frontend Developer

## 1. Name
Aleksandra Ivanenko

---

## 2. Contact Info
- Email: ksandra.ivanenko@gmail.com
- Telegram: [@ksandra_indiel](https://t.me/ksandra_indiel)
- Tel: +380968604472

---

## 3. Summary
> I have been fond of programming for a long time. For pleasure and of interest studied Java, Android programming and finally web development. I am very interested in training and expanding my skills because I want work and develop in the field of web development.
> I have experience in work HTML-coder. And although this experience is small, I am ready to work a lot, diligently and constantly learn new things.

---

## 4. Skills
- HTML
- CSS
- Sass / Less
- BEM
- JavaScript
- JSON
- Gulp
- Webpack
- Git
- Photoshop / Figma

---

## 5. Code examples
```javascript
var game = {
  width: 640,
  height: 360,
  ctx: undefined,
  platform: undefined,
  ball: undefined,

  block: function(x, y) {
    this.ctx.beginPath();
    this.ctx.rect(x, y, 64, 32);
    this.ctx.fillStyle = "lightblue";
    this.ctx.fill();
    this.ctx.closePath();
  },
  blocks: [],
  rows: 4,
  cols: 8,

  sprites: {
    background: undefined,
    platform: undefined,
    ball: undefined
  },
  init: function() {
    var canvas = document.getElementById('canvas');
    this.ctx = canvas.getContext("2d");
    window.addEventListener("keydown", function(evt) {
      if(evt.keyCode == 37) {
        game.platform.dx = -game.platform.speed; 
      } else if(evt.keyCode == 39) {
        game.platform.dx = game.platform.speed; 
      } else if(evt.keyCode == 32) {
        game.platform.releaseBall();
      }
    });
    window.addEventListener("keyup", function() {
      game.platform.stop();
    });
  },
  load: function() {
    for(let key in this.sprites) {
      this.sprites[key] = new Image();
      this.sprites[key].src = "./dist/img/" + key + ".png";
    }
  },
  create: function() {
    for (let row = 0; row < this.rows; row++) {
      for (let col = 0; col < this.cols; col++) {
        this.blocks.push({
          x: 68 * col + 50,
          y: 38 * row + 35,
          width: 64,
          height: 32
        });
      }
    }     
  },
  start: function(){
    this.init();
    this.load();
    this.create();
    this.run();
  },
  render: function() {
    this.ctx.clearRect(0, 0, this.width, this.height);
    this.ctx.drawImage(this.sprites.background, 0, 0);
    this.ctx.drawImage(this.sprites.platform, this.platform.x, this.platform.y);
    this.ctx.drawImage(this.sprites.ball, this.ball.x, this.ball.y);
    this.blocks.forEach(function(elem) {
      this.block(elem.x, elem.y);
    }, this);
  },
  update: function() {
    if(this.platform.dx) {
      this.platform.move();
    }
    if(this.ball.dx || this.ball.dy) {
      this.ball.move();
    }
    this.blocks.forEach(function(elem) {
      if(this.ball.collide(elem)) {
        this.ball.bumpBlock(elem);
      }
    }, this);
  },
  run: function() {
    this.update();
    this.render();
    window.requestAnimationFrame(function() {
      game.run();
    });
  }
};
```

---

## 6. Experience
### Viral Digital Agency
Period | 10.2018 – 04.2019
Responsibility | Adaptive and cross-browser layout of sites according to the layout. Revitalizing pages using JavaScript.
Technologies | HTML5, CSS3, JavaScript, jQuery, JSON, WordPress, Twig

### HTMLAcademy Projects
Gllacy | https://github.com/Indiel/Gllacy
Barbershop | https://github.com/Indiel/Barbershop
Kekstagram | https://github.com/Indiel/613417-kekstagram
Keksobooking | https://github.com/Indiel/613417-keksobooking

---

## 7. Education
- HTMLAcademy - Professional JavaScript, Level 1 (01.2018 – 03.2018)
- V. N. Karazin Kharkiv National University (09.2014 - 07.2018)

---

## 8. English
Pre-Intermediate (A2)