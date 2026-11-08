# T0887 - Wireless Sniffing

[ICS](../../../README.md) / [Discovery](../README.md)

Adversaries may seek to capture radio frequency (RF) communication used for remote control and reporting in distributed environments. RF communication frequencies vary between 3 kHz to 300 GHz, although are commonly between 300 MHz to 6 GHz. (Citation: Candell, R., Hany, M., Lee, K. B., Liu,Y., Quimby, J., Remley, K. April 2018)  The wavelength and frequency of the signal affect how the signal propagates through open air, obstacles (e.g. walls and trees) and the type of radio required to capture them. These characteristics are often standardized in the protocol and hardware and may have an effect on how the signal is captured. Some examples of wireless protocols that may be found in cyber-physical environments are: WirelessHART, Zigbee, WIA-FA, and 700 MHz Public Safety Spectrum. 

Adversaries may capture RF communications by using specialized hardware, such as software defined radio (SDR), handheld radio, or a computer with radio demodulator tuned to the communication frequency. (Citation: Bastille April 2017) Information transmitted over a wireless medium may be captured in-transit whether the sniffing device is the intended destination or not. This technique may be particularly useful to an adversary when the communications are not encrypted. (Citation: Gallagher, S. April 2017) 

In the 2017 Dallas Siren incident, it is suspected that adversaries likely captured wireless command message broadcasts on a 700 MHz frequency during a regular test of the system. These messages were later replayed to trigger the alarm systems. (Citation: Gallagher, S. April 2017)

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T0887)

**Tactics**  [Discovery](../README.md), [Collection](../../08%20TA0100%20-%20Collection/README.md)

**Platforms**  [Embedded](../../../Platforms/Embedded.md), [Windows](../../../Platforms/Windows.md), [Linux](../../../Platforms/Linux.md)

## Targeted assets

- [A0013 - Field I/O](../../../Defenses/Assets/A0013%20-%20Field%20I%20-%20O.md)
- [A0001 - Workstation](../../../Defenses/Assets/A0001%20-%20Workstation.md)

## Mitigations

- [M0808 - Encrypt Network Traffic](../../../Defenses/Mitigations/M0808%20-%20Encrypt%20Network%20Traffic.md) — Utilize strong cryptographic techniques and protocols to prevent eavesdropping on network communications. (Citation: Bastille April 2017) [Bastille April 2017](https://www.bastille.net/blogs/2017/4/17/dallas-siren-attack)
- [M0806 - Minimize Wireless Signal Propagation](../../../Defenses/Mitigations/M0806%20-%20Minimize%20Wireless%20Signal%20Propagation.md) — Reduce the range of RF communications to their intended operating range when possible. Propagation reduction methods may include (i) reducing transmission power on wireless signals, (ii) adjusting antenna gain to prevent extensions beyond organizational boundaries, and (iii) employing RF shielding techniques to block excessive signal propagation. (Citation: DHS National Urban Security Technology Laboratory April 2019) [DHS  National Urban Security Technology Laboratory April 2019](https://www.dhs.gov/sites/default/files/saver-msr-rf-detection_cod-508_10july2019.pdf)

## Detection strategies

- [DET0743 - Detection of Wireless Sniffing](../../../Defenses/Detection%20Strategies/DET0743%20-%20Detection%20of%20Wireless%20Sniffing.md)

## Sources

- [Bastille April 2017](https://www.bastille.net/blogs/2017/4/17/dallas-siren-attack)
- [Candell, R., Hany, M., Lee, K. B., Liu,Y., Quimby, J., Remley, K. April 2018](https://nvlpubs.nist.gov/nistpubs/ams/NIST.AMS.300-4.pdf)
- [Gallagher, S. April 2017](https://arstechnica.com/information-technology/2017/04/dallas-siren-hack-used-radio-signals-to-spoof-alarm-says-city-manager/)
