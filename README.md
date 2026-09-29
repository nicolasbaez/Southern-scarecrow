# Southern-scarecrow
There is nothing more contagious than an idea.

![buh](https://github.com/nicolasbaez/Southern-scarecrow/blob/main/xp082.gif)
```javascript
setup = (_) => createCanvas((w = 500), w, WEBGL);
r = 9;
draw = (_) => {
  n = noise(r * 0.01);
  rotateX(n * 2);
  rotateY(n / 2);
  for (i = 0; i < 2 * PI; i += 0.6) {
    for (j = 0; j <= PI; j += 0.6) {
      stroke(0, 255, 255, 4);
      strokeWeight(noise(i * 0.01, j * 0.01, r * 0.01) * 18);
      point(r * sin(i) * cos(j), r * sin(i) * sin(j), r * cos(i));
    }
  }
  if (r == 9) saveGif("xp082.gif", 1000, { delay: 0, units: "frames" });
  r += 0.3;
};
