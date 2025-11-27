# Stability-Analysis-using-Polar-Plot

## Aim:
To analyse the stability of the system having open loop transfer function, G(S)=10/(S(1+0.5S)(1+0.2S)) using polar plot and verify it using MATLAB. 

## Apparatus Required:
Computer with MATLAB software

## Theory:
<img width="505" height="827" alt="image" src="https://github.com/user-attachments/assets/e8ea5949-6bc4-4465-9b7a-68e2ed05c4db" />
<img width="559" height="680" alt="image" src="https://github.com/user-attachments/assets/411807d2-1f43-43c3-b5bc-13d16e7081d9" />

<img width="636" height="838" alt="image" src="https://github.com/user-attachments/assets/b2042ca7-7569-492b-a917-fc0a5c6a60aa" />

## Procedure:
	Open MATLAB software
	Open a new script file.
	Type the program.
	Save and Execute the program.
	Determine the gain crossover frequency, phase cross over frequency, gain margin and phase margin.
	Also determine the stability.

## Program: 

```
num=[10]
den=[0.1 0.7 1 0]
sys=tf(num,den)
[mag,phase,W]=bode(sys)
mag=squeeze(mag)
phase=squeeze(phase)
phase1=deg2rad(phase)
polarplot(phase1,mag,'linewidth',1.5)
grid on
[Gm Pm Wpc Wgc]=margin(sys)
if(Wpc>Wgc)
    disp('stable')
elseif(Wpc == Wgc)
    disp('marginally stable')
else
    disp('unstable')
end
```

## Output:

<img width="713" height="640" alt="image" src="https://github.com/user-attachments/assets/4711b265-6492-408c-8d8f-c70d45e66a71" />

## Result:
Thus the polar plot for the given transfer function was drawn and verified using MATLAB. <br>
Gain margin = 0.7 <br>
Phase Margin = -8.8865 <br>
Gain crossover frequency = 3.7565 <br>
Phase crossover frequency = 3.1623 <br>
The system is unstable.
