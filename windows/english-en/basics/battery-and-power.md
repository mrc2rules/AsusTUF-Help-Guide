---
icon: battery-bolt
layout:
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

# Battery & Power

Managing your battery effectively helps extend its lifespan and maintain reliable performance.

This section covers optimization settings, best practices, and troubleshooting steps to ensure reliable battery performance and longevity.

## ⚠️ The Essentials

{% stepper %}
{% step %}
### Enable Smart Charging

Available in MyAsus or G-Helper. ([What is smart charging and how does it help?](https://support.microsoft.com/en-us/windows/use-smart-charging-in-windows-2ac1b4ba-6027-410a-b80e-f6767d867002))

* 80% limit if you mostly use the laptop plugged in but occasionally unplug it.
* 60% limit if it's almost always plugged in.

{% tabs %}
{% tab title="GHelper" %}
<figure><img src="../.gitbook/assets/image (24).png" alt="" width="252"><figcaption></figcaption></figure>
{% endtab %}

{% tab title="MyAsus" %}
<figure><img src="../.gitbook/assets/image (23).png" alt="" width="563"><figcaption></figcaption></figure>

Enable "**Battery Care Mode**"
{% endtab %}
{% endtabs %}
{% endstep %}

{% step %}
### Play games/run demanding applications while plugged in ONLY

Running demanding games or heavy GPU/CPU applications on battery can degrade performance and is not recommended at all.&#x20;

It causes extreme wear due to high power draw and reduces battery lifespan.

_Normal word processing or browsing is fine_
{% endstep %}
{% endstepper %}

## &#x20;💖 Improving Battery Life

{% stepper %}
{% step %}
### Switch modes

1. Switch to **Silent fan mode**
2. Switch to **Optimised GPU mode (automatically switches to "Eco" \[iGPU] on battery)**
3. Switch to **"Auto" screen mode (automatically switches to 60Hz on battery)**
4. Keep display brightness **half or less than half**
5. **Disable keyboard backlight** or set it to minimum

That's it!
{% endstep %}

{% step %}
### Uninstall Asus apps

Uninstall both **MyAsus** & **Armoury Crate.** They run in the background at all times, consuming power even when not in active use, leading to increased battery drain.

This is completely safe and won't hamper your computer, GHelper completely replaces all the processes.&#x20;

Additionally, stop all Asus services via GHelper (Extra > Other > Stop)

<figure><img src="../.gitbook/assets/image (13).png" alt=""><figcaption></figcaption></figure>
{% endstep %}

{% step %}
### Disable CPU Boost

This helps battery life as it doesn't boost anymore and less power is drawn. There are two ways to do this. Easiest way is via GHelper.

{% hint style="info" %}
Do not disable if you rely on intensive CPU bound applications. Try testing and see if you have a significant performance hit and if it's worth the drop.

Most games get very little FPS benefit for a massive thermal increase. (eg: 1/2FPS for 20C inc)
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
### Consider undervolting your CPU/GPU

Undervolting your CPU/GPU reduces power consumption and heat output without sacrificing performance.&#x20;

By lowering voltage while maintaining stability, your system runs more efficiently, leading to extended battery life & lower temperatures.

[Here is a YouTube tutorial on how to undervolt your **GPU**](https://youtu.be/KPR06CxysMw?si=nXEXcK0YHovzhRMY)

{% hint style="warning" %}
Check if your CPU supports undervolting, not all models are supported
{% endhint %}

{% hint style="info" %}
BSODs or crashes are normal. Don't worry. If you need additional help or can't figure it out, post on the subreddit or ask in our discord below.

[https://discord.com/invite/g6exUXvWge](https://discord.com/invite/g6exUXvWge)
{% endhint %}
{% endstep %}
{% endstepper %}
