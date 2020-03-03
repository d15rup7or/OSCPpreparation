# OS Command Injection
The general term OSCI relates to a broad class of critical vulnerabilities, in which the un-encoded, untrusted additional input
 is inserted into a command, due to a lack of sufficient validation & sanitization mechanisms. Long story short, it tricks the application into thinking that the user supplied well-crafted malicious code is indeed its' own trusted code.

The main objective of Command Injection, relies upon executing arbitrary commands on the host OS through 
a vulnerable application. If successful, the payload injected by an attacker is executed as a system-level command, giving access to any functionality the underlying software offers. At the end of the day, the impact spans from loss of data confidentiality and integrity to gaining unauthorized remote access to the system that hosts the app, which might result in taking any priviledged actions. 

The reason that these attacks are still alive is because of their independency from both, the **OS** and the **programming language**.  

The exact degree of risk is strictly associated with the security context of the given environment, in which the command is executed.

# Remedial measures
In order to avoid the detrimental impact, secure coding conventions and practices must be implemented in advance.

### **Unix:**
```
;id
;id;
|id;
;id|
`id`
```

### **Windows:**
```
`
||
|
;

```
