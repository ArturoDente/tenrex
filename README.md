TENREX PUR80 C64 BASIC GAME - By Arturo Dente

*HISTORY*
"You are offline" tells Chrome, and what can you do? you can play TENREX!

*THE CODE EXPLANATION*
Line 0 and 9 Code: 	0v=53248:pOv+21,1:pO2040,192:fOt=12288tot+25:pOt,0:nE:pOv+39,0:n=t:b=-1:hs=0:gO9
			9y=191:p=0:g=0:s$(0)="D":s$(1)="E":reS:?"{clear}tenrex{return}hs:"hs:gEa$:on2+(a$=" ")gO1,9

Comment: only inits, like sprite. There is a goto 9 that is the title screen 

Line 1 Code:		1d$="":d$(1)="{down}":fOt=nton+36:d$=d$+d$(2+(t>12324)):rEs:pOt,s:nE:pOv,155:s=0:u=5

Comment: other inits, just to mention that the string d$(1) is build with a lot of "down" chars, but not too lot in order to avoid memory errors. So the condition 
(t>12324) that causes to get d$(0) to sum (that is void)

Line 2 Code:		2a$="":?"{clear}":pOv+32,4:pOv+33,1:pOv+23,1:pOv+29,1:?"{home}"sP29)"{reverse on} {cm y}{cm u}{reverse off}{cm p}":p$="{cm +}{cm +}{cm +}{cm +}"

Comment: we are still in init phase, and we print the phone-signal in top-right of the phon... ehm, screen.

Line 3 Code:		3pOt-2,aB(255-pE(t-2)):pOt-5,aB(255-pE(t-5)):ifs=0tHo$=leF(p$,1+rN(.)*4):b=nOb

Comment: we are in the first line of main cycle. pOt-2,aB(255-pE(t-2)):pOt-5,aB(255-pE(t-5)) makes the sprite animation (t is the number used to iterate between sprite bytes during initialization).
ifs=0tHo$=leF(p$,1+rN(.)*4):b=nOb makes happen the change of obstacle's shape. It's regulated by "s", that is incremented untill 40. It's also the position of obstacle, as we will see

Line 4 Code: 		4?"{home}"leF(d$,22)sP39-s)leF(o$,s)+" {down}{left}"s$(rN(.)*2);:gEa$:ifp=0aNa$=" "tHp=-1:g=g+1

Comment: we print the floor and we get the space key depressed. If it's depressed, starts jumping phase (p=-1), and g=g+1,that's the score


Line 5 Code:		5pOv+1,y:on2+(g>3aNb)goS8:ify<171tHp=1:dA126,0,0,223,0,0,255,7,0,240,3,195,252

Comment: we update sprite y positionm then if we have made more than 3 jumps (and if "b", that is once on, once off), we will add some difficulty by printing a ball over the obstacles (it's in line 8). Then, we test if the sprites has reached 171 y position and if so we put p=1, in order to tell the program that we are about to start the landing phase.

Line 6 Code:		6on(2-pE(v+31))gO9:y=y+2.5*p:ify>190tHp=0:dA3,231,224,1,255,224,0,255,248,0,255

Comment: if there's a sprite vs char collision, then goto start screen. We the upgrade y value, note that we use the variable p to controll it. We then test if y has gone too high (so sprite has reached floor) , and in case we put p=0 in order to say that we are in the "idle" state of jumping.

Line 7 Code:		s=(-s-1)*(s<39):hs=-hs*(hs>=g)-g*(hs<g):gO3:dA200,0,127,128

Comment: if s<39 then s=s+1,else s=0. We update the highscore, then we go to first line of loop.

Line 8 Code:		8u=(-u-1)*(u<39):pO1910-u,81:pO1911-u,32:pO1871,32:reT:dA0,56,0,0,16,0,0,24,0 
Comment: this is where we put the ball over obstacles, it's only some screen ram pokes.


That's all, folks!
