# Day 2 – Ngspice simulation on cloud for nfet_idvds and nfet_idvgs (Lab)


## nfet_id_vds characteristics 

Inside the design/ directory, 
```
vim day2_nfet_idvds_L015_W039.spice
```
![pic](https://github.com/nilophertaj/CMOS-Circuit-Design-and-Spice-Simulations-using-sky130-on-cloud/blob/052241e586aa696ed418e16d9ae41a3488bea4a5/github/day2/day2%202.png)

```
ngspice day2_nfet_idvds_L015_W039.spice
plot -vdd#branch
```
![pic](https://github.com/nilophertaj/CMOS-Circuit-Design-and-Spice-Simulations-using-sky130-on-cloud/blob/052241e586aa696ed418e16d9ae41a3488bea4a5/github/day2/id%20vds%20plot.png)


## nfet_id_vgs characteristics 

Inside the design/ directory, 
```
vim day2_nfet_idvgs_L015_W039.spice
```
![pic](https://github.com/nilophertaj/CMOS-Circuit-Design-and-Spice-Simulations-using-sky130-on-cloud/blob/052241e586aa696ed418e16d9ae41a3488bea4a5/github/day2/id%20vgs%20plot.png
)

```
ngspice day2_nfet_idvgs_L015_W039.spice
plot -vdd#branch
```
![pic](https://github.com/nilophertaj/CMOS-Circuit-Design-and-Spice-Simulations-using-sky130-on-cloud/blob/052241e586aa696ed418e16d9ae41a3488bea4a5/github/day2/id%20vgs.png)

## To calculate the threshold voltage in Id vs vgs 

```
ngspice day2_nfet_idvds_L015_W039.spice
plot -vdd#branch
```
![pic](https://github.com/nilophertaj/CMOS-Circuit-Design-and-Spice-Simulations-using-sky130-on-cloud/blob/052241e586aa696ed418e16d9ae41a3488bea4a5/github/day2/id%20vgs.png)

- Take the tangent along the linear slope till to the x axis to get the threshold voltage Vth, here in the above plot we got 0.77v as Vth. 

