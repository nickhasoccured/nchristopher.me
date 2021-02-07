---
title: "Your CPU has a Backdoor"
date: 2021-02-07T01:45:00-08:00
draft: false
---

It's well known that closed-source operating systems (like [Windows](https://en.wikipedia.org/wiki/Microsoft_Windows) and [macOS](https://en.wikipedia.org/wiki/MacOS)) aren't exactly good for privacy & security. There's essentially _no way_ for a closed-source system's code to be verified.

Which is why people concerned about their privacy & security should use Libre operating systems, such as [Linux](https://en.wikipedia.org/wiki/Linux). But that's _not_ where it ends.

### The Intel Management Engine

Intel's **M**anagement **E**ngine (**ME** for short, which is what I'll be calling it) is a _seperate_ computing enviornment present on _every_ Intel chip since mid 2006. The ME has it's own storage, memory, cache, along with **direct access** to the computer's RAM and **network access**. The ME is signed by Intel, and the computer wont boot _unless_ the signature is valid.

The ME contains a web server allowing _remote_ users to manage the computer - **even while the PC is turned off** (as long as the motherboard has power). While traffic _is_ encrypted using SSL/TLS, pretty much every version of SSL/TLS has had [major vulnerabilities](https://en.wikipedia.org/wiki/Transport_Layer_Security#Attacks_against_TLS/SSL).

And this issue isn't even intel-specific - AMD has a similar product called "Platform Security Processor", though it's implementation is quite different.

#### TLDR

The Intel Management Engine can be (and likely _is_) used as a backdoor, with complete access to the system _over the internet_. And it **cannot be disabled** on modern Intel chips.

### References

For further reading, I'd recommend checking out my sources:

-   [Libreboot's FAQ on the Intel Management Engine](https://libreboot.org/faq.html#intelme)
-   [Libreboot's FAQ on AMD](https://libreboot.org/faq.htm)
-   [Intel Management Engine on Wikipedia](https://en.wikipedia.org/wiki/Intel_Management_Engine)
-   [Attacks against TLS/SSL on Wikipedia](https://en.wikipedia.org/wiki/Transport_Layer_Security#Attacks_against_TLS/SSL)

I thought this was a pretty important issue that a lot of people didn't know about, which is why I wrote a post on it. Just goes to show that you _can't_ trust hardware either.
