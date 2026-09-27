# Investigation Methodology

This investigation was conducted through a structured analysis of Linux authentication artifacts and network traffic to identify attacker activity, reconstruct sessions, investigate persistence, and analyze post-compromise actions.

---

## 1. Authentication Log Analysis

The `auth.log` artifact was examined to identify authentication-related activity on the Linux system.

The analysis focused on:

- Repeated failed SSH authentication attempts
- Source IP addresses associated with failed attempts
- Usernames targeted during the attack
- Successful authentication events
- Privileged account access
- Session creation and closure events
- Commands executed using elevated privileges

Repeated authentication failures from the same source IP were used to identify evidence of SSH brute-force activity.

Successful authentication records were then examined to determine whether the brute-force activity resulted in account compromise.

---

## 2. Attacker IP Identification

The authentication log was reviewed for repeated SSH login attempts originating from the same IP address.

The repeated failures against multiple usernames provided evidence of brute-force behavior.

The identified attacker IP was then used as a reference point during subsequent analysis of session and authentication artifacts.

---

## 3. Session Reconstruction Using `wtmp`

The `wtmp` artifact was analyzed to identify actual login sessions associated with the attacker.

The provided `utmp.py` parser was used to convert the binary `wtmp` data into a readable format.

Example command:

```bash
python3 utmp.py wtmp > output.tsv