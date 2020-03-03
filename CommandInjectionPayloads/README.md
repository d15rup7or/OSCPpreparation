# OS Command Injection
The general term OSCI relates to a broad class of critical vulnerabilities, in which the un-encoded, untrusted additional input
 is inserted into a command in a way, that allows for its execution by the target Operating System. Long story short, it tricks the application into thinking that the user supplied, well-crafted malicious code is indeed its own trusted code, and can be passed further to a system shell (even though it may contain token characters or character strings that have special meanings). This attack is possible to perform largely due to a pre-existing lack of sufficient validation & sanitization mechanisms. 

The main objective of this technique, relies upon executing arbitrary commands on the target host-system through 
a vulnerable application. If successful, the payload injected by an attacker is executed as a system-level command, giving access to any functionality the underlying software offers. At the end of the day, the impact spans from loss of data confidentiality and integrity to gaining unauthorized remote access to the system that hosts the app, which might result in taking any priviledged actions. 

The reason that these attacks are still alive is because of their independency from both, the **OS** and the **programming language**.  

The exact degree of risk is strictly associated with the security context of the given environment, in which the command is executed. As appears from above, the maximum impact is hard to measure, although there is a plain possibility of taking over the entire server and destroying all the data.

## Remedial measures & mitigation
In order to avoid the detrimental impact, secure coding conventions and practices must be implemented in advance. Defending
systems from this weakness requires from developers using the library calls, to create the functionality without external inputs.  

## Usage:
#### **Unix**
```
;id
;id;
|id;
;id|
`id`
```

#### **Windows**
```
`
||
|
;

```
