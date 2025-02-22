let minCycleDuration = 2000; // Minimum duration for a full cycle (2 seconds)
let maxCycleDuration = 6000; // Maximum duration for a full cycle (6 seconds)

function setup() {
  createCanvas(windowWidth, windowHeight);
  colorMode(HSB, 360, 100, 100);
  noStroke();
}

function draw() {
  background(0);

  let cols = ceil(width / 80);
  let rows = ceil(height / 80);
  let tileW = width / cols;
  let tileH = height / rows;

  let maxShapeSize = min(tileW, tileH) * 0.7;

  let centerX = width / 2;
  let centerY = height / 2;

  for (let j = -1; j <= rows; j++) {
    for (let i = -1; i <= cols; i++) {
      let x = i * tileW;
      let y = j * tileH;

      // Distance from the center to create a central-to-boundary wave
      let distanceFromCenter = dist(x, y, centerX, centerY);
      let maxDistance = dist(0, 0, centerX, centerY);
      let normalizedDistance = distanceFromCenter / maxDistance;

      // Noise-based offset for jittery position
      let noiseOffsetX = noise(i * 0.3, j * 0.3, millis() * 0.0005) * tileW * 0.5;
      let noiseOffsetY = noise(j * 0.3, i * 0.3, millis() * 0.0005) * tileH * 0.5;

      x += noiseOffsetX - tileW * 0.25;
      y += noiseOffsetY - tileH * 0.25;

      // Cycle duration and scaling based on radial distance
      let cycleDuration = lerp(minCycleDuration, maxCycleDuration, normalizedDistance);
      let elapsedTime = (millis() + normalizedDistance * 5000) % cycleDuration;
      let scaleFactor = (sin(TWO_PI * elapsedTime / cycleDuration - HALF_PI) + 1) / 2;

      // Randomized hue, saturation, and brightness with noise
      let hue = (noise(i * 0.1, j * 0.1, millis() * 0.001) * 360) % 360;
      let brightness = 60 + 40 * noise((i + j) * 0.05, millis() * 0.001);
      let saturation = 50 + 50 * noise(i * 0.1, j * 0.1, millis() * 0.002);

      fill(hue, saturation, brightness);

      // Size and scaling with central-to-boundary propagation
      let sizeNoise = noise(i * 0.5, j * 0.5, millis() * 0.0008);
      let shapeSize = maxShapeSize * map(sizeNoise, 0, 1, 0.5, 1.5) * scaleFactor;

      // Sides of the shape morphing from center to boundary
      let sides = floor(map(scaleFactor, 0, 1, 3, 20));

      push();
      translate(x + tileW / 2, y + tileH / 2);

      // Rotation influenced by distance from the center
      rotate(normalizedDistance * TWO_PI * frameCount * 0.001);

      drawPolygon(0, 0, shapeSize, sides);
      pop();
    }
  }
}

// Function to draw a polygon with a given number of sides
function drawPolygon(x, y, radius, sides) {
  beginShape();
  for (let i = 0; i < sides; i++) {
    let angle = map(i, 0, sides, 0, TWO_PI);
    
    // Add irregularity to the shape using noise
    let radiusNoise = noise(cos(angle) * 0.8, sin(angle) * 0.8, millis() * 0.002);
    let noisyRadius = radius * map(radiusNoise, 0, 1, 0.6, 1.4);

    let px = x + cos(angle) * noisyRadius;
    let py = y + sin(angle) * noisyRadius;
    vertex(px, py);
  }
  endShape(CLOSE);
}

function windowResized() {
  resizeCanvas(windowWidth, windowHeight);
}
