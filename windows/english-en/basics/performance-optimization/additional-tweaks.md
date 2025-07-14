---
icon: screwdriver
cover: ../../.gitbook/assets/6 (1).png
coverY: 0
layout:
  width: default
  cover:
    visible: true
    size: full
  title:
    visible: false
  description:
    visible: false
  tableOfContents:
    visible: true
  outline:
    visible: true
  pagination:
    visible: true
---

# Additional Tweaks



{% stepper %}
{% step %}
### Turn off memory integrity   <a href="#id0edf" id="id0edf"></a>

1. Select Start , enter ‘Core Isolation’ in the taskbar, and select Core Isolation from the list of results to open the Windows security app.
2.  On the Core isolation page, turn off the toggle for Memory integrity. \
    You might need to restart your device.

    <div align="left"><figure><img src="https://support.microsoft.com/images/en-us/014089ec-5a4a-4573-95a9-61900e2d93ad" alt=""><figcaption></figcaption></figure></div>


{% endstep %}

{% step %}
### Turn off Virtual Machine Platform (VMP)  <a href="#id0edd" id="id0edd"></a>

1. Select Start , enter ‘Windows features’ in the search box, and select Turn Windows features on or off from the list of results.
2. In the Windows Features window that just opened, find and unselect Virtual Machine Platform.\
   \
   ![Windows Features window with Virtual Machine Platform folder shown](https://support.microsoft.com/images/en-us/cbbf67fd-9ace-45fd-a72f-10ff3f9b5e02)
3. Select OK. You might need to restart your device.


{% endstep %}
{% endstepper %}
