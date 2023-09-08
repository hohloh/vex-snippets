// Vex random rotation for each point 


//axis
vector axis = set(0,0,0);
int randaxis = floor(rand(@ptnum+237.23*293)*3);
setcomp(axis,1,randaxis);

//angle
//float spinseed = rand(@ptnum+38.43*8723.74);
float spinseed = rand(@id+38.43*8723.74*chf("seed_offset"));
float rate = fit01(spinseed, chf("min_speed"), chf("max_speed"));
float angle = (@Time * $PI * 2) * rate;

//spin quaternion
vector4 spin = quaternion(angle, axis);

@orient = qmultiply(@orient, spin);
