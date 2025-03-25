> [!NOTE]
> **Broken Access Control** occurs when an application **fails to enforce proper restrictions** on user actions. This allows unauthorized users to access, modify, or delete data they shouldn’t have access to.
> ### **Why is it dangerous?**
> 
> - Attackers can **view or modify sensitive data** (e.g., personal info, admin settings).
> - Can lead to **data breaches**, privilege escalation, or system takeover.
> - Commonly ranks **#1 in the OWASP Top 10 vulnerabilities**.


___

> [!quote]
> ## **How to Prevent Broken Access Control**
> 
> > [!success]- **Enforce Role-Based Access Control ([[RBAC]])**
> > 
> > - Assign proper **roles and permissions** (e.g., user, admin, moderator).
> > - Restrict access based on roles in **both frontend and backend**.
> 
> > [!success]- **Secure API Endpoints**
> > 
> > - Check user permissions **server-side** (don't rely only on the frontend).
> > - Ensure **every request is authenticated** before serving data.
> 
> > [!success]- **Use Secure Session Management**
> > 
> > - Prevent **session hijacking** by implementing **short session timeouts**.
> > - Use **JWT (JSON Web Token)** or secure cookies **with HttpOnly & Secure flags**.
> 
> > [!success]- **Deny by Default**
> > 
> > Restrict **all access by default** and explicitly allow specific roles to access resources.
> 
> > [!success]-  **Perform Security Testing**
> >
> > - Use **automated security scanners** or **manual pentesting** to detect vulnerabilities.
> > - Conduct **role-based testing** to ensure users can’t access unauthorized data.


---

