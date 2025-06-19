---
icon: temperature-list
coverY: 0
layout:
  cover:
    visible: false
    size: full
  title:
    visible: true
  description:
    visible: true
  tableOfContents:
    visible: true
  outline:
    visible: false
  pagination:
    visible: true
---

# Thermal Management

Proper thermal management is essential for maintaining performance, stability, and hardware longevity

This section covers key cooling solutions, recommended settings, and best practices to maintain stable temperatures and prevent overheating.

<details>

<summary><mark style="color:blue;">New? Click here for frequently asked questions</mark></summary>

_<mark style="color:orange;">**Are there any good custom fan curves? Should I use my own?**</mark>_ \
\- No, you don't need to change the fan curves; the defaults are perfectly fine.

_<mark style="color:orange;">**Are there any good GHelper/Armory Crate presets?**</mark>_ \
\- No, you don't need add any "presets"; the defaults are perfectly fine.

</details>

<details>

<summary><mark style="color:red;">Overheating? Click here</mark></summary>

_-_ As long as the it doesn't hit Max Temps (below), it's perfectly fine; the chips are designed to run at these temps. Check the table below.

| Component | Idle Temp   | Usual Load Temp | Max Temp Range ⚠️ |
| --------- | ----------- | --------------- | ----------------- |
| **CPU**   | 40°C - 60°C | 80°C - 90°C     | 95-100°C          |
| **GPU**   | 30°C - 50°C | 70°C - 80°C     | 85-90°C           |

\
There are safety mechanisms in place, and it will automatically throttle if it reaches dangerous temps. Refer to [#the-essentials](thermal-management.md#the-essentials "mention") & [#additional-steps](thermal-management.md#additional-steps "mention") below to lower temps further.

</details>

## ⚠️ The Essentials

{% stepper %}
{% step %}
### Elevate the back of your laptop

Use a laptop stand/book or even your charging brick to keep the laptop slightly elevated from the back. For even better cooling, try using a cooling pad

This is to ensure proper ventilation and for proper cooling. Try not to block any vents
{% endstep %}

{% step %}
### Don't use it on cloth surfaces

The cloth/soft surface may clog up the vents and "choke" the laptop ventilation. Use it on hard surfaces like wood or plastic.
{% endstep %}

{% step %}
### Don't use it with the lid closed

The laptop also dissipates heat from the keyboard. Closing it while using the laptop may trap the heat inside, causing damage to certain components.&#x20;
{% endstep %}

{% step %}
### Regular Maintenance

Dust buildup can impact cooling. Clean the vents and fans **every 6–12 months.**

It's also recommended to change the thermal paste **after 2-3 years of use.**&#x20;
{% endstep %}
{% endstepper %}

## ✅ Additional Steps

{% stepper %}
{% step %}
### Use a cooling pad

Some recommendations:&#x20;

1. IETS GT500
2. LLANO v10/v12
{% endstep %}

{% step %}
### Disable CPU Boost

This helps lower temps BY A LOT. There are two ways to do this. Easiest way is via GHelper.

{% hint style="info" %}
Do not disable if you rely on intensive CPU bound applications. Test and see if you have a significant hit or if it's worth the drop.

Usually games get very little FPS benefit for a massive thermal increase. (eg: 1/2FPS for 20C inc)
{% endhint %}

{% tabs %}
{% tab title="With GHelper" %}
Open 'Fans+Power' and select 'CPU Boost' to 'Disabled'. That's it

<div align="left"><figure><img src="../.gitbook/assets/image (18).png" alt="" width="308"><figcaption></figcaption></figure></div>
{% endtab %}

{% tab title="Without GHelper" %}
1.  Open search and type 'Edit Power Plan' and open.

    <div align="left"><figure><img src="../.gitbook/assets/image (26).png" alt="" width="375"><figcaption></figcaption></figure></div>
2.  Navigate to 'Change advanced power settings' and then scroll down to 'Processor Power Management'

    <div align="left"><figure><img src="../.gitbook/assets/image (15).png" alt="" width="374"><figcaption></figcaption></figure></div>
3.  Scroll down again to 'Processor Performance Boost Mode' and select both options to 'Disabled'. That's it

    <div align="left"><figure><img src="../.gitbook/assets/image (17).png" alt="" width="231"><figcaption></figcaption></figure></div>

{% hint style="warning" %}
Make sure you do this for all performance modes!
{% endhint %}
{% endtab %}
{% endtabs %}
{% endstep %}

{% step %}
### Consider undervolting your CPU and GPU

Undervolting your CPU/GPU reduces power consumption and heat output without sacrificing performance.&#x20;

By lowering voltage while maintaining stability, your system runs more efficiently, leading to extended battery life & lower temperatures.

[Click here for a guide to undervolt you **GPU**](gpu-performance-optimization.md)

{% hint style="warning" %}
Check if your CPU supports undervolting, not all models are supported
{% endhint %}
{% endstep %}
{% endstepper %}
