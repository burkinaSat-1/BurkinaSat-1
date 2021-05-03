### Hi there 👋

BurkinaSat-1 project is an initiative of Universtity Nobert Zongo project in Burkina Faso West African Country.
The satellite is transmitting becon data via UHF band at  435 Mhz frequency

## Becon Telemetry
amateur radio can get the burkina-sat1 Becon Telemetry by using process below.
- Use SDR  radio at frequency UHF 437.X Mhz (Note the X value will be provide by IARU after validation)
- Use GQRX and a compatible SDR
 ## how to configure GQRX 
In the GQRX main GUI, several things must be configured:

In the Input Controls tab:
Ensure the DC Remove checkbox is checked.
Adjust RF, IF and BB gains according to your needs. Common values that usually work on HackRF, depending on the noise around the antenna and the strength of the satellite signal are shown below. However, playing around with these values to find the optimal combination of gains is recommended.
RF: 0 dB, IF: 16 dB, BB: 20 to 32 dB
RF: 0 dB, IF: 24 dB, BB: 20 to 24 dB
RF: 14 dB, IF: 16 dB, BB: 20 to 24 dB
RF: 14 dB, IF: 8 dB, BB: 20 to 32 dB
In the Receiver Options tab:
The satellite sends GMSK-modulated data. To demodulate such satellite signals, select Narrow FM as the demodulation mode.
The filter width can be left to Normal, as this usually gives enough bandwidth for the 4800 bps frames from Quetzal-1.
In the FFT Settings tab:
Set the FFT size to 32768. This usually makes the spectrum cleaner.
You can adjust the zoom on the FFT display to fit your needs.
Make sure port 7355 is configured for UDP. To do so, click on the ... button next to Rec and select the Network tab. Then configure:
UDP Host: localhost
UDP Port: 7355

## Becon  specification
Burkina-Sat1 is  deployed using Gomspace hadware and software at some point . Burkina-Sat1 use UHF @435.200 Mhz  for down link and up link transmission. For downlink, Burkina-sat1 uses a GOMSpace AX100 transceiver, which transmits GMSK-modulated data at 4800 bps at 437.X.200 MHz.
Beacons are encapsulated in AX.25 + HDLC frames, with G3RUH scrambling and NRZI encoding. The following image shows the overall beacon format:

![beacon_structure](https://user-images.githubusercontent.com/83551940/116835536-f6409500-ab90-11eb-9ead-a20ec87e9f4c.png)


## Decoder and Parser for Burkina-Sat1 downlink data decoding
Once you downloaded and installed the Gqrx Software defined radio, you can use RTL-SDR dongle to attach your your ground station UHF antenna or use  the anntena provided by RTL-SDR. Attach your Gqrx to your RTL-SDR  by selecting USB as connexion port 

![Gqrx](https://user-images.githubusercontent.com/83551940/116836226-b0390080-ab93-11eb-80d4-908a5054ef94.png)

## How to decode the  Burkina-Sat1 Becon data
Please clone the [gr-satellites](https://github.com/daniestevez/gr-satellites) project providing a decoder to decode the data that received from Gqrx 
gr-satellites is a GNU Radio out-of-tree module encompassing a collection of telemetry decoders that supports many different Amateur satellites. This open-source project started in 2015 with the goal of providing telemetry decoders for all the satellites that transmit on the Amateur radio bands.

It supports most popular protocols, such as AX.25, the GOMspace NanoCom U482C and AX100 modems, an important part of the CCSDS stack, the AO-40 protocol used in the FUNcube satellites, and several ad-hoc protocols used in other satellites.
 
 you can also run the decoder directly by executing:
