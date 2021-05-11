# Wallhack

CS:GO wallhack achieved by patching one byte of game memory. Written in Python 3.

This does the same as r_drawothermodels 2 command but without touching the cvar, so it's VAC - safe.

# How it works

This program patches assembly code produced by compiling the following line of the game code:

int extraFlags = 0;

if ( r_drawothermodels.GetInt() == 2 )
{	
    
    extraFlags |= STUDIO_WIREFRAME;	
}

The r_drawothermodels check is modified to make the if expression evaluate to true when r_drawothermodels cvar is set to default value (1).

![image](https://user-images.githubusercontent.com/56160262/117774422-1c33fc80-b257-11eb-9f5e-bb8f31f965e0.png)

