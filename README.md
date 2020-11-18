float x; 
float y; 
float t;
float g = 9.82; 
float v0; 
float x0; 
float y0; 
float u0;
float E; 
float A; 
float m = 1; 
float L = 1; 
float alpha = PI/4; 
float startpunkt = 500; 
float xPixel; 
float yPixel; 

void setup(){
  size(700,700);
  textSize(24);
  frameRate(10);
  
 
}


void draw(){

  tidModel();

}

void mousePressed(){
fill(145,123,54);
  clear();  
  tidModel();

ellipse(x,yPixel,10,10);
yPixel = yPixel - y;
text("x =" + x + "   y =" + yPixel, 50,75);
 
}



void tidModel(){
  fill(145,123,54);
 /* x = u0 * t;
   y = -0.5*g*t*t+v0*t+y0;*/
   x = v0*cos(alpha)*t+x0;
   y = -0.5*g*t*t+v0*sin(alpha)*t+y0;
   
  u0 = sqrt((2*E)/m*(1+A*A));
  v0 = A * sqrt((2*E)/m*(1+A*A));
  E = 50 * L*L;
  A = sin(alpha);
  t = t + 0.2;
  
  //println(x,y);//
}
