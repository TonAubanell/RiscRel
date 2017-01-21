# RiscRel

# This algorithm takes a 2x2 matrix [[a,b], [c,d]] and returns the Relative Risck and a Confidenc interval of 95%. 

def RiscRelatiu(x):

    import numpy as np
	
    x = np.array(x)
	
    if x.shape != (2, 2):
	
        print("Must be a 2x2 data frame")
		
    else:
	
        a = x[0,0]
		
        ab = sum(x[0])
		
        c = x[1,0]
		
        cd = sum(x[1])
		
        rr = (a*cd)/(c*ab)
		
        lnRR = np.log(rr)
		
        SE = np.sqrt(1/a + 1/c-(1/ab)-(1/cd))
		
        down = (np.exp(lnRR - 1.96*SE))
		
        upper = (np.exp(lnRR + 1.96*SE))
		
        print (rr, down, upper)
