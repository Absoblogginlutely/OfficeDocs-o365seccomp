---
title: "Office 365 Core Principles of Defense Against Denial-of-Service Attacks"
ms.author: robmazz
author: robmazz
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomplocalization_priority: None
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-security-compliance
description: "How Microsoft utilizes the core principles of absorption, detection, and mitigation in its defense against denial-of-service (DoS) attacks."
---

# Core Principles of Defense Against Denial-of-Service Attacks

The three core principles when defending against network-based DoS attacks are Absorption, Detection, and Mitigation.
Absorption happens before detection, and detection happens before mitigation. Absorption is the best defense against a DoS attacks. If the attack can't be detected, it can't be mitigated. But if even the smallest DoS attack can't be absorbed, then services aren't going to survive long enough for the attack to be detected.

Of course, it is generally not economically feasible for most organizations to purchase the excess capacity necessary to absorb DoS attacks, as this requires a considerable investment in technology and technical skills. This highlights one of the security benefits of using Microsoft cloud services; the sheer scale of our services enables us to provide strong network protection to our cloud customers in a cost-effective manner. But even at our scale, though, there must still be a balance between absorption, detection, and mitigation. To find that balance, we study an attack's growth rate to estimate how much we need to absorb.

Detection is a cat-and-mouse game. You must constantly look for the new ways people are attacking you or trying to defeat your systems. Detect -> Mitigate -> Detect -> Mitigate, etc., is a perpetual, persistent state that will continue indefinitely.

## Defending Against DoS Attacks

To successfully defend against a DoS attack, early detection is essential. By detecting an attack before the system is overwhelmed, defenders can execute a response plan.

The following formula will help approximate the time to impact of a DoS attack:

   **Maximum Capacity (in bytes/sec) / Growth Rate (in bytes/sec) = Time to Impact (in bytes/sec)**

If the time-to-detection occurs after time-to-impact, then it is likely the DoS attack will be successful. If the time-to-detection occurs before time-to-impact, then the services being attacked should remain online and accessible, if mitigation strategies are used. Thus, there are only two things that can be done to defend against DoS attacks:
- Increase capacity to raise the ceiling of maximum capacity (which in turn provides more time to detect an attack); or
- Decrease the time to detect.

Increasing capacity has a direct fiscal impact. Microsoft recommends that customers develop at least basic absorption capacity, to ensure that they can survive some level of DoS attack. The actual absorption capacity will vary from customer to customer, as each customer has their own thresholds for exposure, risk, and financial outlay. Ultimately, for economic reasons, investments of research and time in ways to decrease time-to-detection are usually the most cost-effective defense.
