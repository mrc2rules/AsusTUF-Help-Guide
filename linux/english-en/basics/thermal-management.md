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

<summary>Click Here For Frequently Asked Questions</summary>

1. _<mark style="color:orange;">**My CPU is at 95C! My GPU is at 82C! It's overheating!**</mark>_\
   _-_ These temps are perfectly fine; the chips are designed to run at these temps \
   \[CPU < 98/99C || GPU < 84/85C]\
   \
   There are safety mechanisms in place, and it will automatically throttle if it reaches dangerous temps. Refer to [#the-essentials](thermal-management.md#the-essentials "mention") & [#additional-steps](thermal-management.md#additional-steps "mention") below to lower temps further.
2. _<mark style="color:orange;">**Are there any good custom fan curves? Should I use my own?**</mark>_ \
   \- No, you shouldn't need to change the fan curves; the defaults are perfectly fine.

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
{% endstep %}

{% step %}
### Consider undervolting your CPU and GPU

Undervolting your CPU/GPU reduces power consumption and heat output without sacrificing performance.&#x20;

By lowering voltage while maintaining stability, your system runs more efficiently, leading to extended battery life & lower temperatures.

{% hint style="warning" %}
Check if your CPU supports undervolting, not all models are supported
{% endhint %}
{% endstep %}
{% endstepper %}
