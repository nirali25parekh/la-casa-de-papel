#include <graphics.h>
#include <conio.h>
int xmid, ymid;



//center//
void centerstruct()
{
	int poly[8];
	rectangle(xmid-95,ymid-70,xmid+95,ymid-20);// bada wala rect
	rectangle(xmid-90,ymid-80,xmid+90,ymid-70);//  upper rect
	line(xmid-115,ymid-65,xmid-115,ymid-20);//beech ka line
	line(xmid+115,ymid-65,xmid+115,ymid-20);//   beech ka line
	delay(200);
	rectangle(xmid-20,ymid-50,xmid+20,ymid-30);// center gray rect
	setfillstyle(7,LIGHTGRAY);
	delay(200);
	floodfill(xmid-10,ymid-35,WHITE);
	rectangle(xmid-125,ymid-20,xmid+125,ymid-15); //   base rect ke neeche
	rectangle(xmid-115,ymid-15,xmid+115,ymid);  //     pillar ke upar
	rectangle(xmid-60,ymid+105,xmid+60,ymid+140);   //door
	poly[0]=xmid-60;
	poly[1]=ymid+105;
	poly[2]=xmid+60;
	poly[3]=ymid+105;
	poly[4]=xmid+60;
	poly[5]=ymid+140;
	poly[6]=xmid-60;
	poly[7]=ymid+140;
	setfillstyle(2,DARKGRAY);
	fillpoly(4,poly);
}

//pillars//
void pillars()
{
	int i=0,j=0;
	int poly1[8],poly2[8];
	rectangle(xmid-95,ymid+82,xmid+96,ymid+87);  //hori incenter
	delay(200);
	setfillstyle(1,DARKGRAY);
		poly1[0]=xmid-95;
		poly1[1]=ymid+82;
		poly1[2]=xmid+96;
		poly1[3]=ymid+82;
		poly1[4]=xmid+96;
		poly1[5]=ymid+87;
		poly1[6]=xmid-95;
		poly1[7]=ymid+87;
		fillpoly(4,poly1);

	for(j=0;j<4;j++)                     //cascading pillars
	{
		rectangle(xmid-110+i,ymid,xmid-95+i,ymid+140);
		rectangle(xmid-90+i,ymid,xmid-75+i,ymid+140);
		setfillstyle(6,WHITE);
		poly1[0]=xmid-110+i;
		poly1[1]=ymid;
		poly1[2]=xmid-95+i;
		poly1[3]=ymid;
		poly1[4]=xmid-95+i;
		poly1[5]=ymid+140;
		poly1[6]=xmid-110+i;
		poly1[7]=ymid+140;
		fillpoly(4,poly1);
		poly2[0]=xmid-90+i;
		poly2[1]=ymid;
		poly2[2]=xmid-75+i;
		poly2[3]=ymid;
		poly2[4]=xmid-75+i;
		poly2[5]=ymid+140;
		poly2[6]=xmid-90+i;
		poly2[7]=ymid+140;
		fillpoly(4,poly2);
		i=i+62;
		delay(200);
	}
	rectangle(xmid-112,ymid+140,xmid-93,ymid+150);  //left pillar base
	rectangle(xmid+94,ymid+140,xmid+113,ymid+150);  //right pillar base
}

//staircase//
void stairs()
{       int j=0,i=0,k=0;
	rectangle(xmid-93,ymid+140,xmid+94,ymid+146);     //upper platform
	rectangle(xmid-93,ymid+146,xmid+94,ymid+148);  // stair1
	rectangle(xmid-93,ymid+148,xmid+94,ymid+150); //stair 2
	for(j=0;j<12;j++)                              //cascading stairs
	{
		rectangle(xmid-122-i,ymid+150+k,xmid+123+i,ymid+152+k);
		i=i+5;
		k=k+2;
		delay(200);
	}
}

//top floor
void f4()
{
	rectangle(xmid-310,ymid-75,xmid-90,ymid-70);  //topmost outline l
	rectangle(xmid+310,ymid-75,xmid+90,ymid-70);     //topmost outline r
	rectangle(xmid-315,ymid-70,xmid-95,ymid-65); //top inline l
	rectangle(xmid+315,ymid-70,xmid+95,ymid-65); //top inline r
	line(xmid-310,ymid-65,xmid-310,ymid-18);    //vert l out
	line(xmid+310,ymid-65,xmid+310,ymid-18);    //vert r out
	line(xmid-305,ymid-65,xmid-305,ymid-18);    //vert l in
	line(xmid+305,ymid-65,xmid+305,ymid-18);    //vert r in
}

//windowtopfloor
void winf4()
{       int i=0,j=0;
	for(j=0;j<5;j++)
	{
		rectangle(xmid-275+i,ymid-50,xmid-255+i,ymid-30);
		rectangle(xmid-272+i,ymid-47,xmid-258+i,ymid-33);
		line(xmid-265+i,ymid-47,xmid-265+i,ymid-33);
		i=i+30;
	}
	i=0;
	for(j=0;j<5;j++)
	{
		rectangle(xmid+275-i,ymid-50,xmid+255-i,ymid-30);
		rectangle(xmid+272-i,ymid-47,xmid+258-i,ymid-33);
		line(xmid+265-i,ymid-47,xmid+265-i,ymid-33);
		i=i+30;
	}
}

//big floor
void f3()
{
	line(xmid-315,ymid-18,xmid-125,ymid-18); //top hori l
	line(xmid-315,ymid-13,xmid-115,ymid-13); //bottom hori l
	line(xmid-315,ymid-18,xmid-315,ymid-13);   //vert l
	line(xmid+315,ymid-18,xmid+125,ymid-18);    //top h r
	line(xmid+315,ymid-13,xmid+115,ymid-13);    //bottom h r
	line(xmid+315,ymid-18,xmid+315,ymid-13);    // vert r
	line(xmid-310,ymid-13,xmid-310,ymid+80); //vert l out
	line(xmid+310,ymid-13,xmid+310,ymid+80); //vert r out
	line(xmid-305,ymid-13,xmid-305,ymid+80); // vert l in
	line(xmid+305,ymid-13,xmid+305,ymid+80); //vert r in
}

//window big floor
void winf3()
{	int i=0,j=0;
	for(j=0;j<4;j++)
	{
		rectangle(xmid-280+i,ymid,xmid-250+i,ymid+65);
		rectangle(xmid-277+i,ymid+3,xmid-253+i,ymid+62);
		line(xmid-265+i,ymid+3,xmid-265+i,ymid+62);
		i=i+40;
	}
	i=0;
	for(j=0;j<4;j++)
	{
		rectangle(xmid+280-i,ymid,xmid+250-i,ymid+65);
		rectangle(xmid+277-i,ymid+3,xmid+253-i,ymid+62);
		line(xmid+265-i,ymid+3,xmid+265-i,ymid+62);
		i=i+40;
	}
}

//first floor
void f2()
{
      rectangle(xmid-315,ymid+80,xmid-110,ymid+85);  //hori r
      rectangle(xmid+315,ymid+80,xmid+111,ymid+85);  //hori l
      rectangle(xmid-310,ymid+85,xmid-305,ymid+140);  //vert l
      rectangle(xmid+310,ymid+85,xmid+305,ymid+140);  //vert r

}

//window first floor
void winf2()
{       int i=0,j=0;
	for(j=0;j<5;j++)
	{
		rectangle(xmid-275+i,ymid+100,xmid-255+i,ymid+126);
		rectangle(xmid-272+i,ymid+103,xmid-258+i,ymid+123);
		line(xmid-265+i,ymid+103,xmid-265+i,ymid+123);
		i=i+30;
	}
	i=0;
	for(j=0;j<5;j++)
	{
		rectangle(xmid+275-i,ymid+100,xmid+255-i,ymid+126);
		rectangle(xmid+272-i,ymid+103,xmid+258-i,ymid+123);
		line(xmid+265-i,ymid+103,xmid+265-i,ymid+123);
		i=i+30;
	}

}

//bottom floor
void f1()
{
      rectangle(xmid-315,ymid+140,xmid-112,ymid+145);  //hori r
      rectangle(xmid+315,ymid+140,xmid+113,ymid+145);  //hori l
      rectangle(xmid-310,ymid+145,xmid-305,ymid+170);  //vert l
      rectangle(xmid+310,ymid+145,xmid+305,ymid+170);  //vert r
      line(0,ymid+170,xmid*2,ymid+170); //bottom line
}

//colour fill
void fillfloor()
{
	setfillstyle(1,DARKGRAY);
	floodfill(xmid-300,ymid-60,WHITE);  //top l
	floodfill(xmid+300,ymid-60,WHITE);  //top r
	floodfill(xmid-300,ymid+150,WHITE);                 //bottom l
	floodfill(xmid+300,ymid+150,WHITE);                 // bottom r
	floodfill(xmid-300,ymid,WHITE);                 //big l
	floodfill(xmid+300,ymid,WHITE);                 // big r
	floodfill(xmid-300,ymid+90,WHITE);    //first l
	floodfill(xmid+300,ymid+90,WHITE);  //first r
	floodfill(xmid-250,ymid-73,WHITE); //terrace l
	floodfill(xmid+250,ymid-73,WHITE); //terrace r

}

void fillcenter()
{
	setfillstyle(1,LIGHTGRAY);
	floodfill(xmid-100,ymid-60,WHITE);       //l
	floodfill(xmid,ymid-60,WHITE);       //c
	floodfill(xmid+100,ymid-60,WHITE);       //r
	floodfill(xmid,ymid-10,WHITE); //pillar ke upar wala
	floodfill(xmid,ymid+143,WHITE);  //stairs ke upar platform
	floodfill(xmid,ymid-75,WHITE);	//sabse top
	floodfill(xmid-100,ymid+145,WHITE);  // left pillar base
	floodfill(xmid+100,ymid+145,WHITE);   // right pillar base
}
int main(void)
{
    /* request auto detection */
   int gdriver = DETECT, gmode, errorcode;
   char driver[] = " ";
   /* initialize graphics and local
   variables */
   initgraph(&gdriver, &gmode, driver);

   /* read result of initialization */
   errorcode = graphresult();
   /* an error occurred */
   if (errorcode != grOk)
   {
      printf("Graphics error: %s\n", grapherrormsg(errorcode));
      printf("Press any key to halt:");
      getch();

      exit(1);    /* terminate with an error code */
   }

   xmid=getmaxx()/2;
   ymid=getmaxy()/2;


   centerstruct();
   delay(200);
   pillars();
   delay(200);
   f4();
   delay(200);
   f3();
   delay(200);
   f2();
   delay(200);
   f1();
   delay(200);
   winf4();
   delay(200);
   winf3();
   delay(200);
   winf2();
   delay(200);
   stairs();
   delay(200);
   fillcenter();
   delay(200);
   fillfloor();
   delay(200);
   settextstyle(8,0,5);
   setcolor(RED);
   outtextxy(110,40,"LA CASA DE PAPEL");
   getch();
   cleardevice();


setcolor(13);
rectangle(1,1,639,479);
rectangle(15,15,624,464);
setfillstyle(6,11);

floodfill(2,2,13);
settextstyle(7,0,3);
setcolor(CYAN);

outtextxy(150,100,"COMPUTER GRAPHICS PROJECT");
outtextxy(150,200,"MADE BY :KUNAL AND SHREEJA") ;
outtextxy(175,300,"CLASS: D7B \t\t BATCH:B");
outtextxy(175,400,"ROLL NO: 32 & 39");



   /* clean up */
   getch();
   closegraph();
   return 0;
}
