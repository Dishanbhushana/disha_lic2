# disha_lic2
# the mos differential pair amplifier<br>
 differential amplifier pair amplifier is the circuit that ampifies the difference between two input signal while rejecting the common mode noise.The circuit consists of two MOSFETs that amplify the difference between two input signals while rejecting common-mode noise. Essentially, a differential amplifier combines inverting and non-inverting amplifiers. <br>
this mos has main application in operational amp,analog to digital convertors,sensor interface etc <br>
this amplifier has high input impedence:good for interfacing with other high impedence sources <br>
provides accurate signal amplification <br>
## schematc diagram of mos differential amplifier
![WhatsApp Image 2025-03-07 at 01 52 55_9a3d11fa](https://github.com/user-attachments/assets/02691d27-79b5-48f9-9c83-af2dcf189a47)
### there are 4 types of differential amplifier<br>
### Resistor-Loaded Differential Pair:<br>
*Uses resistors as the drain load.<br>
*Simple design but has low gain due to large requirements.
*Limited common-mode rejection and output swing.
### Current Source-Loaded Differential Pair:<br>
Replaces Rss with Ideal current source.<br>
Improves gain.<br>
### Simple Current Source Differential Pair:<br>
Uses a single MOSFET as a current source.<br>
Gain increases still.<br>
### Active Load Differential Pair (MOSFET as Load):<br>
Both Iss and Rd are replaced with a mosfet .<br>
Gain is too high.<br>
### working principle<br>
the differential amplifier operates in the active region and can function in different modes: common-mode and differential-mode .<br>
the differential amplifier has 2 input terminals that is V1 and V2 (non inverting and inverting)<br>
'the output is determined by difference between 2 inputs <br>
Common-Mode Rejection:
If both input signals are identical (common-mode signals), the ideal differential amplifier cancels them out, giving zero output.
This property is measured by the Common-Mode Rejection Ratio (CMRR).
It receives two input signals and compares them.<br>
It amplifies only the difference between the two inputs.<br>
Any noise or interference present in both inputs is removed.<br>
The output changes based on the difference between the input signals.<br>
Feedback is often used to stabilize gain and improve <br>
### key features
High Common-Mode Rejection Ratio (CMRR): Rejects noise present in both inputs.<br>
Good Stability: Less sensitive to variations in power supply or temperature.<br>
Used in Instrumentation Amplifiers: Provides precise low-noise amplification.<br>
Forms the Basis of Op-Amp Circuits: Essential in signal processing.<br>
## aim of the experiment: design and analyze the mos differntial amplifier circuit for following specifications<br>
VDD=1.8v,P=1.8mW,Vin=0.9v,Vocm=0.9v,Vp=0.2V<br>
### components required:
RSS->stabilizes biasing which further provides negative feedback<br>
RD->this is the drain resistance converts currend into o/p voltage<br>
id->drain current(ensure the transistor is in saturation region)<br>
iss-> tail current( provides stable constant current)<br>
#### note :
the output can be either differential orsingle ended,if the v_1=v_2 then the outpu voltage will be 0V<br>
### calculations of the desing part:
![WhatsApp Image 2025-03-07 at 01 54 23_5b92cc3c](https://github.com/user-attachments/assets/94225a44-7122-4c79-b53c-c2daadfaa823)
### from LT spice we observe that
as the VDD increases ,vout also increases and more is the gain<br>
when width increases curret flowing also increases but vout decreases,gain is more<br>
as RD increases vout also increases gain increases<br>
when RSS increases gain get reduced but common mode rejection is bettered<br>
### case 1(resistor loaded differential pair)
#### DC Analysis :
![WhatsApp Image 2025-03-07 at 01 55 33_256a6ea3](https://github.com/user-attachments/assets/0129697c-959b-4155-a238-ef771357799a)
![WhatsApp Image 2025-03-07 at 01 55 33_3ab71a4e](https://github.com/user-attachments/assets/69e18530-7eb0-4642-a15b-413b53592ecb)
Make the necessary connections as per the circuit daigram .<br>
Set the Rd and Rss values such that the transistors will operate in saturation region .<br>
Vary W/L to get the required Voutcm.<br>
Vary Rd to set exact Voutcm.<br>
Go to "Simulate" > "Edit Simulation Cmd" > "DC op pnt".<br>
ckt1 dc<br>
for the transistor to operate in saturation region Vgs>Vth<br>
Vds>Vov<br>
we observe that the Vgs=0.552V<br>
Vth=0.481V<br>
Vds=0.758V<br>
hence the transistor lies in saturation region<br>
Qpoint(0.759V,0.607mA)<br>
Vincm(min)= Vth + Vp = 0.366 + 0.4 = 0.766V<br>
Vincm(max) = Vdd - (Id*Rd) + Vth = 1.463V<br>
Vout(min) = Vov1 + Vp = (0.55-0.366)+0.4 = 0.584V<br>
Vout(max) = Vdd-(Id*Rd) = 1.1003V<br>
### transient analysis:<br>
 Replace DC input with an AC signal.<br>
Use SINE(dc_offset, Amplitude, Frequency)..<br>
Go to "Simulate" > "Edit Simulation Cmd" > "Transient"..<br>
Set Stop Time: 5ms..<br>
Run the simulation.
![WhatsApp Image 2025-03-07 at 01 55 33_288593b0](https://github.com/user-attachments/assets/7c8fd476-8c19-4869-ba48-a476e4f6f9c6)
frrom the above graph obtaine=d we observe that there is 180 degree phase shift<br>
it has gain of -8.978<br>(voutp-p=1.5211-0.6567,vinp-p=1.5122-0.6567=0.8555<br>
gain =0.8644/0.8555=8.978<br>
### AC analysis:
in the simulation tab select AC analysis<br>
in the AC select type of the sweep as decade<br>
enter the number of points as per decade and frequency range (0.1Hz to 1THz)<br>
![WhatsApp Image 2025-03-07 at 01 55 34_43ee4d17](https://github.com/user-attachments/assets/24cfd24b-a757-40c1-a36c-76074a0ab3aa)
differential gain obtained is=19.563dB<br>
### NOW BY REPLACING RESISTOR WITH CURRENT SOURCS(Iss)<br>
#### DC Analysis<br>
Make the necessary connections as per the circuit daigram .<br>
now replace the resistor with current source and give the value of Iss from the calculations.<br>
Vary W/L to get the required Voutcm.<br>
Vary Rd to set exact Voutcm.<br>
Go to "Simulate" > "Edit Simulation Cmd" > "DC op pnt".<br>
ckt1 dc<br>
![WhatsApp Image 2025-03-07 at 02 00 29_7bfe0a8b](https://github.com/user-attachments/assets/b1e9d7dd-5af7-4b39-8527-74d04aa3a22d)
### transient analysis<br>
Replace DC input with an AC signal.<br>
Use SINE(dc_offset, Amplitude, Frequency)..<br>
Go to "Simulate" > "Edit Simulation Cmd" > "Transient"..<br>
Set Stop Time: 5ms..<br>
Run the simulation.
![WhatsApp Image 2025-03-07 at 02 00 29_2226a8b4](https://github.com/user-attachments/assets/206ce2a7-d14e-4146-bbe5-0e9f3aa0a713)
there is 180 degree phase shift<br>
9.274v/v = gain<br>
20log(av)=20log(9.27<br)=19.3415dB
### AC analysis
![Screenshot_(43) 1](https://github.com/user-attachments/assets/c604658b-a7dd-4209-a5cc-9885cc6d48b2)
## BY REPLACING MOSFET<br>
### DC analysis
![Screenshot (41)](https://github.com/user-attachments/assets/24773ed5-1072-4e8b-ade9-2d81aa4d16d3)
![WhatsApp Image 2025-03-07 at 02 06 11_cd71f1d5](https://github.com/user-attachments/assets/3e86fd7d-f64d-4f66-809e-1c5c0a609fb8)
For the dc analysis very the resistance as per the diagram to achive the given specifications<br>
now keep length as it is n very the width that is 48.131u(M3)<br>
120.29u(M2,M1)<br>
### Transient Analysis<br>
![WhatsApp Image 2025-03-07 at 02 06 52_9d599aca](https://github.com/user-attachments/assets/78c5bc63-526d-4d9c-bc00-36a554155ad1)
there is 180 degree phase shift<br>
gain is 9.7254<br>
20log(av)=20log(9.7254)<br>
=19.758dB
### AC analysis
![WhatsApp Image 2025-03-07 at 02 06 52_0ac6ecc1](https://github.com/user-attachments/assets/ce1c56e5-fd6a-4a16-8ef9-3709eecbb25e)
## BONUS QUESTION
![WhatsApp Image 2025-03-07 at 02 08 01_adc8aee3](https://github.com/user-attachments/assets/261bf472-9735-4974-aafb-62e1fc6798e6)
for the above question width of
### M4,M5=22.445u<br>
### M1,M2=120.29u<br>
### M3=48.131u<br>
### DC operating point<br>
![WhatsApp Image 2025-03-07 at 02 08 01_197c3273](https://github.com/user-attachments/assets/2c623c7a-2a69-42b8-9a13-86633d8bdf92)
### Transient analysis<br>
![WhatsApp Image 2025-03-07 at 02 09 12_15788c32](https://github.com/user-attachments/assets/796491f8-bd2a-4d66-a96a-0895775c4fbb)
### AC analysis<br>
![WhatsApp Image 2025-03-07 at 02 09 13_d70111b9](https://github.com/user-attachments/assets/0aad3b59-e147-4bd8-b600-88e6a482096c)
### Result
<table>
 <tr> 
  <td>parameters</td>
  <td>circuit1</td>
  <td>circuit2</td>
  <td>circuit3</td>
 </tr>
  <tr> 
  <td>gain</td>
  <td>low</td>
  <td>high</td>
  <td>very high</td>
 </tr>
  <tr> 
  <td>o/p swing</td>
  <td>ldue to load resistance it s reduced</td>
  <td>higher that resistor</td>
  <td>highestswing</td>
 </tr>
  <tr> 
  <td>vincm</td>
  <td>limited due to Rd,Rss</td>
  <td>high</td>
  <td>more compared to circuit 2</td>
 </tr>
  <tr> 
  <td>vout role</td>
  <td>has poor role</td>
  <td>better</td>
  <td>best as compared to other 2</td>
 </tr>
 </table>

### INFERENCE
The differential amplifier effectively amplifies differential signals while rejecting noise. The operating points are set as required values, and the CMRR is enhanced using current sources and active loads. MOSFET-based designs offer better power efficiency and high input impedance.Vincm must be within the range that keeps both input transistors ON and in saturation.Since Rss allows variations in current as it doesn't produce constant current we replace resistor with constant current source which provides stable output and gain.n a differential amplifier, the tail resistor is often replaced with a current source to improve circuit performance to make current stable and increase gain.The output common-mode voltage (Vocm) remains around 1.1V, aligning well with the design specification. 
The resistor load (Circuit 01) provides a gain of 8.978 V/V, influenced by The current source load (Circuit 02) achieves a slightly higher gain as an ideal current source has a high output impedance, maximizing gain.The NMOS load (Circuit 03) shows a gain of 9.612 V/V,
