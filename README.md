### Hi there 👋

BurkinaSat-1 project is an initiative of Universtity Nobert Zongo project in Burkina Faso West African Country.
The satellite is transmitting becon data via UHF band at  435 Mhz frequency

## Becon Telemetry
amateur radio can get the burkina-sat1 Becon Telemetry by using process below.
- Use SDR  radio at frequency UHF 453 mhz
- Use GQRX and a compatible SDR

## Becon  specification
Burkina-Sat1 is  deployed using Gomspace hadware and software at some point . Burkina-Sat1 use UHF @435.200 Mhz  for down link and up link transmission. For downlink, Burkina-sat1 uses a GOMSpace AX100 transceiver, which transmits GMSK-modulated data at 4800 bps at 435.200 MHz.
Beacons are encapsulated in AX.25 + HDLC frames, with G3RUH scrambling and NRZI encoding. The following image shows the overall beacon format:

![beacon_structure](https://user-images.githubusercontent.com/83551940/116835536-f6409500-ab90-11eb-9ead-a20ec87e9f4c.png)


## Downlink Decoder and Parser
Once you downloaded and installed the Gqrx Software defined radio, you can use RTL-SDR dongle to attach your your ground station UHF antenna or use  the anntena provided by RTL-SDR. Attach your Gqrx to your RTL-SDR  by selecting USB as connexion port 

![Gqrx](https://user-images.githubusercontent.com/83551940/116836226-b0390080-ab93-11eb-80d4-908a5054ef94.png)
