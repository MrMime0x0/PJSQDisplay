# QXD11 Desktop Manager

QXD11 is an effort to create a **rootless desktop manager** using **Python, JavaScript (JS), and Qt**. Development is ongoing, and the project may take some time to reach full functionality.  

>  **Root Access:** Only Python requires root access for security purposes. All other modules (JS, Qt) run entirely in **userspace**.

---

# General Info

• Desktop manager is **rootless**, except for Python, which requires root to maintain security.  
• Uses **SELinux, AppArmor, and Auditd** to provide multi-layered protection.  
• Python detects keyloggers and other threats without interrupting the user’s workflow.  
• JS and Qt run in userspace only — no root required.

---

# Architecture Overview

QXD11 is structured to keep root access minimal and maintain a secure, user-level display server:

1. **Python Module**  
   ‣ Backend security module  
   ‣ Handles **keylogger detection** and other security tasks  
   ‣ Requires root to enforce security policies  

2. **JavaScript (JS) Module**  
   ‣ Renders cursor and backend visual elements  
   ‣ Wraps around Python, starting after Python initializes  
   ‣ Runs entirely in userspace  

3. **Qt Module**  
   ‣ Wraps around JS to render the full desktop interface  
   ‣ Displays and interacts with the desktop  
   ‣ Userspace only, no root required  

---

# Security Modules

• **SELinux Module**  
   ➜ First layer of security (Mandatory Access Control)  
   ➜ Protects Python module from malicious actors  
   ➜ Requires root to function  

• **AppArmor Module**  
   ➜ Second layer, path-based rules for JS module  
   ➜ Enhances security on top of SELinux  

• **Auditd Module**  
   ➜ Logs actions for Python, JS, Qt, SELinux, and AppArmor modules  
   ➜ Helps debug issues and maintain transparency  

---

# How it Works

• System boots → Python module initializes (root)  
• JS module starts → renders cursor and backend visuals  
• Qt module launches → displays desktop for user interaction  
• Multi-layered security ensures **keylogger detection and module protection** while keeping the desktop fully functional  

---

# Key Points

• Minimal root usage — only Python & security modules require root  
• Userspace modules (JS, Qt) handle **all rendering** and desktop interaction  
• Multi-layered security: SELinux → AppArmor → Auditd → Python monitoring  
• Designed for **secure, user-level display server** on Qubes OS with KVM  

────────────────────────────
