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
### Disable CPU Boost

This helps battery life as it doesn't boost anymore and less power is drawn.&#x20;

{% hint style="info" %}
Do not disable if you rely on intensive CPU bound applications. Try testing and see if you have a significant performance hit and if it's worth the drop.

Most games get very little FPS benefit for a massive thermal increase. (eg: 1/2FPS for 20C inc)
{% endhint %}
{% endstep %}

{% step %}
### Consider undervolting your CPU/GPU

Undervolting your CPU/GPU reduces power consumption and heat output without sacrificing performance.&#x20;

By lowering voltage while maintaining stability, your system runs more efficiently, leading to extended battery life & lower temperatures.

{% hint style="warning" %}
Check if your CPU supports undervolting, not all models are supported
{% endhint %}

{% hint style="info" %}
BSODs or crashes are normal. Don't worry. If you need additional help or can't figure it out, post on the subreddit or ask in our discord below.

[https://discord.com/invite/g6exUXvWge](https://discord.com/invite/g6exUXvWge)
{% endhint %}
{% endstep %}
{% endstepper %}
