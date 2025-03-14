//Comandos
spd= 5
 
hor=keyboard_check(ord("D"))-keyboard_check(ord("A"))
ver=keyboard_check(ord("S"))-keyboard_check(ord("W"))
 
 
var h = hor*spd
var v = ver*spd
 
 
//colisão horizontal
if(place_meeting(x+h,y,Oparede)){
        while(!place_meeting(x+sign(h),y,Oparede)){
                x+=sign(h)
        }
        h=0
}
 
 
//colisão vertical
if(place_meeting(x,y+v,Oparede)){
        while(!place_meeting(x,y+sign(v),Oparede)){
                y+=sign(v)
        }
        v=0
}
 
 
x+=h
y+=v

//personagem seguindo o mouse
var _dire = point_direction(x, y, mouse_x, mouse_y)

var _intervalo = _dire == clamp (_dire, 90, 270)

if(_intervalo)
{
	image_xscale=-1
}
else
{
	image_xscale=1
}



