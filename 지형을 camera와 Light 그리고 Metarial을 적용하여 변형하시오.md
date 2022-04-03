var cols, rows;
var scl = 20;
var w = 1400;
var h = 1000;
var flying = 0;
var terrain = [];

let sliderGroup = [];
let X;
let Y;
let Z;
let centerX;
let centerY;
let centerZ;
let c = 20;
let cam;

function setup() {
  createCanvas(600, 600, WEBGL);
  cols = w / scl;
  rows = h / scl;

  for (var x = 0; x < cols; x++) {
    terrain[x] = [];
    for (var y = 0; y < rows; y++) {
      terrain[x][y] = 0; //specify a default value for now
    }
  }
  noStroke();
  
  cam = createCamera();
  // create sliders
  for (var i = 0; i < 6; i++) {
    if (i === 2) {
      sliderGroup[i] = createSlider(10, 400, 200);
    } else {
      sliderGroup[i] = createSlider(-400, 400, 0);
    }
    c = map(i, 0, 6, 5, 85);
    sliderGroup[i].position(10, height + c);
    sliderGroup[i].style('width', '80px');
  }
  sliderGroup[6] = createSlider(-100, 100, 0);
  sliderGroup[7] = createSlider(10, 300, 100);
  sliderGroup[6].position(100, height+5);
  sliderGroup[6].style('width', '80px');
  sliderGroup[7].position(100, height+17);
  sliderGroup[7].style('width', '80px');
}

function draw() {
  flying -= 0.01;
  var yoff = flying;
  for (var y = 0; y < rows; y++) {
    var xoff = 0;
    for (var x = 0; x < cols; x++) {
      terrain[x][y] = map(noise(xoff, yoff), 0, 1, -100, 100);
      xoff += 0.1;
    }
    yoff += 0.1;
  }
  
  
  X = sliderGroup[0].value();
  Y = sliderGroup[1].value();
  Z = sliderGroup[2].value();
  centerX = sliderGroup[3].value();
  centerY = sliderGroup[4].value();
  centerZ = sliderGroup[5].value();
  let dirX = sliderGroup[6].value();
  let dirY = sliderGroup[7].value();
  cam.camera(X, Y, Z, centerX, centerY, centerZ, 0, 1, 0);
  background("#B8F8FB");
  translate(0, 50);
  rotateX(PI / 3);
  directionalLight(255, 255, 255, dirX, dirY, 0);
  ambientMaterial(255, 0, 0);
  
  sphere(40);
 
  translate(-w / 2, -h / 2);
  for (var y = 0; y < rows - 1; y++) {
    beginShape(TRIANGLE_STRIP);
    for (var x = 0; x < cols; x++) {
      let v=map(terrain[x][y],-100,100,0,150);
      directionalLight(255, 255, 255, dirX, dirY, 0);
      ambientMaterial(0,0,v);
      vertex(x * scl, y * scl, terrain[x][y]);
      vertex(x * scl, (y + 1) * scl, terrain[x][y + 1]);
    }
    endShape();
  }

}

왼쪽스위치는  카메라 코드를 이용해 구현 오른쪽 스위치는 빛코드를 이용해 구현 
