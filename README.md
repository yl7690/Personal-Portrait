function setup() {
  createCanvas(400, 400);
}

function draw() {
  background(255);
 
  let hair = color(254,223,159);
  let skin = color(255,239,214);
  let skinEdge = color(166,102,77);
  let shadow = color(240,191,151);
  
//Blue curve on the background
  stroke(160,202,240);//baby blue
  strokeWeight(225);
  bezier(-50,75,200,0,200,400,450,325);
  
  
//Hair  
  fill(hair);
  noStroke();
  
  beginShape();
  curveVertex(50,400);
  curveVertex(50,400);
  curveVertex(90,300);
  curveVertex(120,125);
  curveVertex(150,70);
  curveVertex(200,50);
  curveVertex(250,70);
  curveVertex(280,125);
  curveVertex(310,300);
  curveVertex(350,400);
  curveVertex(350,400);
  endShape();
  
  
//face and body
  stroke(skinEdge);
  strokeWeight(2);
  fill(skin);
  
  //body
  beginShape();
  curveVertex(70,400);
  curveVertex(70,400);
  curveVertex(90,330);
  curveVertex(165,300);
  curveVertex(180,245);
  curveVertex(220,245);
  curveVertex(235,300);
  curveVertex(310,330);
  curveVertex(330,400);
  curveVertex(330,400);
  endShape();
  
  //neck shadow
  fill(shadow);
  noStroke();
  
  beginShape();
  curveVertex(173,289);
  curveVertex(175.5,276);
  vertex(179,251);
  curveVertex(198,256);
  curveVertex(202,256);
  vertex(221,251);
  curveVertex(225,276);
  curveVertex(224.5,289);
  curveVertex(200,298);
  endShape(CLOSE); 
  
  //face
  fill(skin);
  stroke(skinEdge);
  ellipse(200,170,130,170);
  
  
//bang
  noStroke();
  fill(hair);
  arc(237,73,100,120,QUARTER_PI,PI,CHORD);
  arc(160,75,95,105,0,HALF_PI+QUARTER_PI,CHORD);
  
  //bang shadow
  noStroke();
  fill(shadow);
  
  beginShape();
  vertex(170,127);
  vertex(170,127);
  curveVertex(185,118);
  curveVertex(195,109);
  curveVertex(200,114);
  vertex(205,119);
  curveVertex(196,115);
  curveVertex(196,109);
  endShape();

  
//top
  //main part
  noStroke();
  fill(0);
  
  beginShape();
  curveVertex(112,400);
  curveVertex(112,400);
  curveVertex(117,370);
  curveVertex(200,380);
  curveVertex(283,370);
  curveVertex(288,400);
  curveVertex(288,400);
  endShape();

  //shoulder straps
  stroke(0);
  strokeWeight(5);
  line(120,318,117,370);
  line(280,318,283,370);
  bow(120,318);
  bow(280,318);
  
  
//ears
  stroke(skinEdge);
  strokeWeight(2);
  fill(skin);
  arc(140,175,38,37,HALF_PI,PI+HALF_PI,OPEN);
  arc(260,175,38,37,HALF_PI+PI,HALF_PI,OPEN);
  
  //earrings
    noStroke();
    earring(130,189);
    earring(270,189);
  
  
//eyes
  eyeWhite(170,160);
  eyeWhite(230,160);
  stroke(0);
  strokeWeight(2);
  arc(169,160,35,20,PI,0,OPEN);
  arc(231,160,35,20,PI,0,OPEN);
  
  //eyeballs
  eyeBall(170,160);
  eyeBall(230,160);

  
//eyebrows
  let eyebrow = color(233,204,144);
  fill(eyebrow);
  
  //left
  noStroke();
  quad(186,143,184,138,163,135,165,140);
  stroke(eyebrow);
  strokeWeight(5);
  arc(163,140,23,5,PI,PI+HALF_PI,OPEN);
  
  //right
  noStroke();
  quad(235,140,237,135,216,138,214,143);
  stroke(eyebrow);
  strokeWeight(5);
  arc(235,140,27,5,-QUARTER_PI,0,OPEN);
  
  
//mouth
  fill(216,59,48);//lips
  noStroke();
  arc(200,220,35,15,0,PI,CHORD);
  triangle(183,220,210,220,193,214);
  triangle(217,220,190,220,207,214);

  
//nose
  noFill();
  stroke(shadow);
  strokeWeight(1.7);
  arc(193,195,3,8,HALF_PI,PI+HALF_PI,OPEN);
  arc(207,195,3,8,PI+HALF_PI,HALF_PI,OPEN);
  
  beginShape();
  curveVertex(194,196);
  curveVertex(194,196);
  curveVertex(198,199);
  curveVertex(202,199);
  curveVertex(206,196);
  curveVertex(206,196);
  endShape();
  
//necklace
  stroke(0);
  strokeWeight(4);
  noFill(0);
  arc(200,300,75,15,0,PI,OPEN);
  
  fill(0);
  triangle(190,319,210,319,200,336);
  triangle(200,314,190,330,210,330);
  stroke(255);
  strokeWeight(8);
  point(200,308);
 
  
//collarbones
  stroke(shadow);
  strokeWeight(7);
  curve(175,321,175,321,162,316,146,317);
  curve(225,321,225,321,238,316,254,317);
  strokeWeight(6);
  curve(175,321,162,316,146,317,146,317);
  curve(225,321,238,316,254,317,254,317);
}

function eyeWhite(x,y){
  fill(255);
  noStroke();
  ellipse(x,y,35,20);
}

function eyeBall(x,y){
  noStroke();
  fill(46,33,3);
  circle(x,y,17);
  fill(255);
  circle(x+2,y,6);
}

function earring(x,y) {
  fill(0);
  circle(x,y,7);
  circle(x,y+7,7);
  circle(x,y+14,7);
  circle(x,y+21,7);
}

function bow(x,y) {
  stroke(0);
  strokeWeight(5);
  line(x,y,x-10,y+10);
  line(x,y,x+10,y+10);
    
  noFill();
  strokeWeight(5);
  square(x-13,y-10,10,15,20,0,20);
  square(x+1,y-10,10,15,20,20,0);
}
