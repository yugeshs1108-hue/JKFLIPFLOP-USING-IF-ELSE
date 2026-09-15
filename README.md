# JKFLIPFLOP-USING-IF-ELSE

**AIM:** 

To implement  JK flipflop using verilog and validating their functionality using their functional tables

**SOFTWARE REQUIRED:**

Quartus prime

**THEORY**

**JK Flip-Flop**

JK flip-flop is the modified version of SR flip-flop. It operates with only positive clock transitions or negative clock transitions. The circuit diagram of JK flip-flop is shown in the following figure.

![image](https://github.com/naavaneetha/JKFLIPFLOP-USING-IF-ELSE/assets/154305477/a649c30b-232b-4558-b188-fd6c09845180)


This circuit has two inputs J & K and two outputs Qtt & Qtt’. The operation of JK flip-flop is similar to SR flip-flop. Here, we considered the inputs of SR flip-flop as S = J Qtt’ and R = KQtt in order to utilize the modified SR flip-flop for 4 combinations of inputs. The following table shows the state table of JK flip-flop.

![image](https://github.com/naavaneetha/JKFLIPFLOP-USING-IF-ELSE/assets/154305477/c4360742-e8a8-4937-b089-c46c0433f9a3)

 
Here, Qtt & Qt+1t+1 are present state & next state respectively. So, JK flip-flop can be used for one of these four functions such as Hold, Reset, Set & Complement of present state based on the input conditions, when positive transition of clock signal is applied. The following table shows the characteristic table of JK flip-flop. Present Inputs Present State Next State
 
![image](https://github.com/naavaneetha/JKFLIPFLOP-USING-IF-ELSE/assets/154305477/6c275261-a6d5-4c37-a3a7-1e88ca11c4cd)

By using three variable K-Map, we can get the simplified expression for next state, Qt+1t+1. Three variable K-Map for next state, Qt+1t+1 is shown in the following figure.
 
![image](https://github.com/naavaneetha/JKFLIPFLOP-USING-IF-ELSE/assets/154305477/5174f41b-0ce0-4329-a372-6d1943ea6673)

The maximum possible groupings of adjacent ones are already shown in the figure. Therefore, the simplified expression for next state Qt+1t+1 is Q(t+1)=JQ(t)′+K′Q(t)Q(t+1)=JQ(t)′+K′Q(t)

**Procedure**

/* write all the steps invloved */

**PROGRAM**
```
module jkflipflop(q,qb,j,k,clock,reset);
	input j,k,clock,reset;
	output reg q,qb;
always @ (posedge(clock))
	begin
		if(!reset)
			begin
				q<=q;
				qb<=qb;
			end 
		else
			begin
				if(j==0 && k==0)
					begin
					q<=q;
					qb<=qb;
					end
				else if(j!=k)
					begin
					q<=j;
					qb<=k;
					end
				else if(j==1 && k==1)
					begin
					q<=~q;
					qb<=~qb;
					end
			end
		end 
endmodule
```
/* Program for flipflops and verify its truth table in quartus using Verilog programming
```
Developed by: yugeshwaran S
RegisterNumber:21222504052

```

**RTL LOGIC FOR FLIPFLOPS**
<img width="1917" height="1075" alt="646251509-499f3cb9-c036-4901-9050-b14da4871024" src="https://github.com/user-attachments/assets/23d73e38-7b10-4ea7-a8c4-112cec592d15" />

**TIMING DIGRAMS FOR FLIP FLOPS**

<img width="1386" height="768" alt="646948491-a5e65ee5-fb43-4adb-82ca-2b071b87dd7c" src="https://github.com/user-attachments/assets/3c77c5db-f43a-4daa-bfde-f290fd723dd1" />


**RESULTS**
