# disha_lic2
# the mos differential pair amplifier<br>
 differential amplifier pair amplifier is the circuit that ampifies the difference between two input signal while rejecting the common mode noise.The circuit consists of two MOSFETs that amplify the difference between two input signals while rejecting common-mode noise. Essentially, a differential amplifier combines inverting and non-inverting amplifiers. <br>
this mos has main application in operational amp,analog to digital convertors,sensor interface etc <br>
this amplifier has high input impedence:good for interfacing with other high impedence sources <br>
provides accurate signal amplification <br>
## schematc diagram of mos differential amplifier
![WhatsApp Image 2025-03-06 at 21 26 00_1677bb05](https://github.com/user-attachments/assets/7ea38691-d5c5-49b8-aec6-06cf116519cf)
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
![WhatsApp Image 2025-03-06 at 21 39 47_8eb292e7](https://github.com/user-attachments/assets/78fd50ee-66c8-4cd1-8e5b-a85296bbd164)
### from LT spice we observe that
as the VDD increases ,vout also increases and more is the gain<br>
when width increases curret flowing also increases but vout decreases,gain is more<br>
as RD increases vout also increases gain increases<br>
when RSS increases gain get reduced but common mode rejection is bettered<br>
### case 1(resistor loaded differential pair)

#### DC Analysis :
![WhatsApp Image 2025-03-06 at 21 35 15_388a7491](https://github.com/user-attachments/assets/15491dd8-3468-4d76-895a-574ca4f32c51)

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
![WhatsApp Image 2025-03-06  21 35 51_c344a928](https://github.com/user-attachments/assets/8ec5d46f-37e0-4619-8f70-c541038a2b46)9
frrom the above graph obtaine=d we observe that there is 180 degree phase shift<br>
it has gain of -8.978<br>(voutp-p=1.5211-0.6567,vinp-p=1.5122-0.6567=0.8555<br>
gain =0.8644/0.8555=8.978<br>
### AC analysis:
in the simulation tab select AC analysis<br>
in the AC select type of the sweep as decade<br>
enter the number of points as per decade and frequency range (0.1Hz to 1THz)<br>
![WhatsApp Image 2025-03-06 at 21 36 32_d067629e](https://github.com/user-attachments/assets/36896d5c-77cd-49a2-98de-85623d376beb)
differential gain obtained is=19.563dB<br>
### NOW BY REPLACING RESISTOR WITH CURRENT SOURCS(Iss)<br>
#### DC Analysis<br>
Make the necessary connections as per the circuit daigram .<br>
now replace the resistor with current source and give the value of Iss from the calculations.<br>
Vary W/L to get the required Voutcm.<br>
Vary Rd to set exact Voutcm.<br>
Go to "Simulate" > "Edit Simulation Cmd" > "DC op pnt".<br>
ckt1 dc<br>
![WhatsApp Image 2025-03-06 at 23 23 29_f932408a](https://github.com/user-attachments/assets/e2b78ae1-c233-43ce-8cd5-54f19d1854e4)
### transient analysis<br>
Replace DC input with an AC signal.<br>
Use SINE(dc_offset, Amplitude, Frequency)..<br>
Go to "Simulate" > "Edit Simulation Cmd" > "Transient"..<br>
Set Stop Time: 5ms..<br>
Run the simulation.
![WhatsApp Image 2025-03-06 at 22 15 38_8bc956cf](https://github.com/user-attachments/assets/aaa5a0d4-8473-492b-ab05-9d34f29d7c4f)
there is 180 degree phase shift<br>
9.274v/v = gain<br>
20log(av)=20log(9.27<br)=19.3415dB
### AC analysis
![Screenshot_(43) 1](https://github.com/user-attachments/assets/d4bdb438-d7a1-454a-b371-acec48ad5d39)
## BY REPLACING MOSFET<br>
![WhatsApp Image 2025-03-06 at 23 57 01_c5f0479c](https://github.com/user-attachments/assets/fc8c604b-1e1e-41b2-b9fc-58502bb07aad)
### DC analysis<br>
For the dc analysis very the resistance as per the diagram to achive the given specifications<br>
now keep length as it is n very the width that is 48.131u(M3)<br>
120.29u(M2,M1)<br>
![WhatsApp Image 2025-03-06 at 23 56 11_9706d173](https://github.com/user-attachments/assets/fdd61eb0-d133-4c7e-8369-c27721d1dd97)
### Transient Analysis<br>
![WhatsApp Image 2025-03-06 at 23 58 53_22a1a5b4](https://github.com/user-attachments/assets/95dec01b-bec8-4968-a872-acf4994499cf)
there is 180 degree phase shift<br>
gain is 9.7254<br>
20log(av)=20log(9.7254)<br>
=19.758dB
### AC analysis
![WhatsApp Image 2025-03-06 at 23 59 02_d2a824eb](https://github.com/user-attachments/assets/125f1311-69fa-4849-8669-bc611772bccd)
## BONUS QUESTION
![WhatsApp Image 2025-03-07 at 00 52 42_0ee1a913](https://github.com/user-attachments/assets/3fe3b5da-3c27-4abf-a216-eb3ecf792144)
### DC operating point<br>
![WhatsApp Image 2025-03-07 at 00 56 20_1ffbda4e](https://github.com/user-attachments/assets/f96cf29b-6ea8-4b40-9607-786c4d0f20bd)
### Transient analysis<br>
![WhatsApp Image 2025-03-07 at 00 46 09_13725223](https://github.com/user-attachments/assets/cab85991-30bc-4741-9d66-787227566fc3)
### AC analysis<br>
![WhatsApp Image 2025-03-07 at 00 46 31_3c53c44c](https://github.com/user-attachments/assets/0461b4f1-968b-4d1f-8cc8-627ecffe9dfe)
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
