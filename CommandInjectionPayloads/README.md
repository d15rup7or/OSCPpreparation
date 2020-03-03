# OS Command Injection
The general term OSCI relates to a class of critical vulnerabilities in which the un-encoded untrusted input
 is added into a command, due to a lack of proper validation mechanism.
The main objective of OS Command Injection, relies upon executing arbitrary commands on the host operating system through 
a vulnerable application. If successful, the payload injected by an attacker is executed as a system-level command 
(it may occur in various environments such as Windows, Linux, Unix etc.). The impact spans from loss of data confidentiality
 and integrity to gaining unauthorized remote access to the system that hosts the app, which might result in taking priviledged actions.

The reason that these attacks are still alive

The exact degree of risk is strictly associated with the security context of given environment, in which the command is executed.

# Remedial measures
In order to avoid 

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
