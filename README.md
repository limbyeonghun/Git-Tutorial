# 20160699 임병훈
2.스케치 작성
아두이노 코드
arduino
void setup() {
 Serial.begin(9600);
 pinMode(13, OUTPUT);
 }
int a;
void loop() {
  int a = analogRead(A0);
  Serial.println(a); //a=a+1;
  delay(500);
  if (a>600) digitalWrite(13,LOW);
  else       digitalWrite(13,HIGH);
}
프로세싱 코드
processing
 import processing.serial.*;
 Serial p;
 void setup(){
   size(300,300);
   p=new Serial(this,"COM5",9600);
 }
 void draw(){
   if(p.available()>0){
     String m=p.readString();
     int a = int(m.trim());
     println(a);
     if(a>250) fill(0,255,0);
     else fill(255,0,0);
     ellipse(150,150,200,200);
   }
 }
 소감 : 수업시간이 끝난뒤 교수님께 찾아가서 물어보았는데 친절하게 잘 설명 해주셔서 감사했다. 왜냐하면 익숙하지않은 코드들이 너무나 많아서 
 과제를 감당하기 힘들었기 때문이다. 수업시간에 이해해도 막상 혼자 하면 잘 기억이 나지않고 어렵다. 하지만 모르는게 있으면 가르쳐주시는 교수님
 덕분에 과제를 겨우 힘들게 끝낼수 있었다. 앞으로도 열심히 해야곘다는 생각을 하였다.
