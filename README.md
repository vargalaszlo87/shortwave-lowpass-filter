# 🚀 shortwave-lowpass-filter

This repository is about Passive LPF filter with inverse Chebyshev LC Ladder.

![image](https://github.com/user-attachments/assets/7469ecea-41ce-4f7f-92a0-cdfe3a36505f)

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

This case is the simplest way to understand the passband, the cut-off frequency and the stop-band. The Bode-chart (without phase-chart) can be interpreted as follows:

- the passband is the frequency that the filter passes through (0dB dashed line here and the blue line)
- there is also a dashed line of -3dB, which is the maximum attenuation of the passband
- the cut-off frequency is  where the blue line meets the dashed line of -3dB
- the transition area where the attenuation increases
- and the stopband where the attenuation is maximal

🚀 **what to do if you see a similar amplitude diagram, where is the cuttoff frequency?**

1. find the maximum amplitued in passband (for example 0dB)
2. draw a line at level of -3dB
3. the point where the level -3dB meets the amplitude line  

![image](https://github.com/user-attachments/assets/ee6d97a7-94b1-468e-8bb0-fc62cddbb811)

### Second case

The second variant is more difficult. For example, if you have a higher order Chebyshev or Ellipcit filter, the former method will not work. Look at the following diagram:

**💥These types ripple in both the bandwidth and the stopband.** So, we have many questions:

- where can we measure the maximal amplitude in passband?
- wath is the attenuation in stopband?
- where exactly is the cutoff point?
- etc.

**📢 Some axioms**

- the delta $$δ$$ value is the allowed swing in the bandpass
- there isn't -3dB point on curve, the cutoff frequency is at the intersection of $$1 - δ_1$$ and $$f_p$$ lines
- the start of the stopband starts at the intersection of $$δ_2$$ and $$f_s$$ lines
- the maximal attenuation of the filter is the highest amplitude after the point of $$f_s$$
- the slope can be measured in the $$Δf$$ band

![image](https://github.com/user-attachments/assets/cb843c5b-5cad-4c23-b555-52f4ee05c9c7)

## 🚀 Let's start!

**Where is the point of -3dB?**

1. Find the max amplitude in the passband. The value is ~ -6.02dB here.
2. Find the ~ -9dB level
3. The -3db point is at the intersection of amplitude and -9dB lines
4. The cut-off frequency is at the intersection of the x-axis and the -3dB point line cursor.

![inv_cheb_lpf_plot_01](https://github.com/user-attachments/assets/dde0978a-1ab8-452f-ab36-6a1421550b66)

**What is the maximal attenuation of the filter?**

1. Find the largest magnitude in stopband and draw a line to that level.
2. Calc the different between the -3dB level and previous level.

![inv_cheb_lpf_plot_02](https://github.com/user-attachments/assets/d6d5e86d-3b7d-40d2-a62c-d88037b82f31)

**How wide is the transition band?**

1. Set the first cursor to the -3dB level
2. Set the horizontal line of the second cursor to the maximum value in the stopband.
3. The width of transition band is betwen the two horizontal lines of the cursors.

![inv_cheb_lpf_plot_03](https://github.com/user-attachments/assets/390e4685-b35d-4ccd-9f23-6b97dd3b8d3d)

**How steep is the slope?**

1. Find a quasi linear section on the slope or linearize the function in transition band.
2. Measure the reduction in magnitude between a decade.

*In this case:*

1. You can use the -3dB point as a first point of the slope.
2. The second point is the point at 10 times the frequency.

![inv_cheb_lpf_plot_04](https://github.com/user-attachments/assets/bd4aec98-ab35-4c94-a99d-91f8505fb93f)

**What happens to the phase?**

![image](https://github.com/user-attachments/assets/2df596ce-e1bf-4ee7-a7b7-4b90e96366ed)

# 👾 The results of this filter

## Cutoff frequency = 31.23MHz
## Passband gain = -6.02dB
## Ripple in passband = < 1dB
## roll-off slope = -30.01dB / decade
## Stopband attenuation = -36.46dB


