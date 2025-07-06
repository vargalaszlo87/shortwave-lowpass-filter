# 🚀 shortwave-lowpass-filter

This repository is about Passive LPF filter with inverse Chebyshev LC Ladder.

![image](https://github.com/user-attachments/assets/b24af1f2-ff0a-46d7-90f8-5f7df9ca6cb9)

## ⭐ First approach

**What makes a filter?** The filters are used to separate one band of frequency from another.

**How many types of filter are there?** There are four types:
- Low pass filter
- High pass filter
- Band pass filter
- Notch filter

👽**more precisely:** There are only two basic type: Low-pass filter and the High-pass filter. The other two types are a combination of a low-pass or high-pass filter. 

Check the types out:

![image](https://github.com/user-attachments/assets/158b46d6-7e97-45b8-aa44-4a9f9ca06438)

**Is there another grouping aspect?** We can sort by active or passiv filters.

- **Passiv filter** This type has only passive parts: capacitance, inductance, resistance (or crystal, but the crystel work as a RLC circuit) therefore this type reduces the amplitude. 

- **Active filter** This type contains least one active compoment, such as a transistor.

🚷 **There are still many grouping aspect (analog/digital, time domain behaviour etc.)**, but we are talking about analog RF (Radio Frequency) or AF (Audio Frequency) filters. 

## ⭐ Second approach

Very important things in this topic, like frequency response, phase diagram and order of the filter. 

**The order of filter:**

- **First order** filter: 20dB / decade
- **Second order** filter: 40dB  / decade
- **Third order** filter: 60dB / decade
- etc.

🚀 **Decade:** represents a tenfold change in frequency. 

**Phase response:** shows how the filter phase shifts components of different frequencies.

Understanding the phase response is important because it affects signal integrity, timing, and system stability. This description will not cover this in detail, but if you want to know more about it, start here: https://www.analog.com/en/resources/analog-dialogue/articles/band-pass-response-in-active-filters.html

# 👾 LPF filter in this REPO is an inverse Chebyshev filter

How can we design an excellent filter easily? Choose the type of filter for your project and understand how it works. This description is about Low Pass Filter.

**This diagram shows the amplitude attenuation character of an inverse Chebyshev filter:**

![image](https://github.com/user-attachments/assets/3bd39761-d9c2-464b-852c-3a6ebd58392c)

## 👹How much info does this graph give me? a lot!

We need to look at two cases.

### First case

This case is the simplest way to understand the passband, the cut-off frequency and the stop-band.

![image](https://github.com/user-attachments/assets/ee6d97a7-94b1-468e-8bb0-fc62cddbb811)



