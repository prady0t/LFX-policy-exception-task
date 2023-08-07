# LFX-policy-exception-task
# About

***1)*** `limit-containers.yaml`: contains policy for limiting containers per pod upto 2 only. 

***2)*** `should-pass.yaml`: contains manifest to create a pod with **two** containers running in it.

***3)*** `should-fail`: contains manifest to create a pod with **three** containers running in it.

***4)*** `policy-exception.yaml`: contains the policy exception for delta namespace.

---

# Applying ClusterPolicy

---

Applying `limit-containers.yaml`:

<img width="1435" alt="Screenshot 2023-08-07 at 11 16 15 PM" src="https://github.com/prady0t/LFX-policy-exception-task/assets/99216956/6adee10b-2286-4b5f-9436-2de1e823b99f">

---

Creating `should-pass.yaml`:

<img width="1435" alt="Screenshot 2023-08-07 at 11 17 44 PM" src="https://github.com/prady0t/LFX-policy-exception-task/assets/99216956/943a324f-0b5b-4a8c-b895-d2e0524e1c7e">

As we can see resource was successfully created!

---

Creating `should-fail.yaml`:

<img width="1435" alt="Screenshot 2023-08-07 at 11 20 03 PM" src="https://github.com/prady0t/LFX-policy-exception-task/assets/99216956/bbaa2d09-ccf0-4d2f-89f8-36bcd4775529">

As we can see resource creation was blocked due to above policy.

---

# Applying PolicyException

---

Applying `policy-exception.yaml`:

<img width="1435" alt="Screenshot 2023-08-07 at 11 29 22 PM" src="https://github.com/prady0t/LFX-policy-exception-task/assets/99216956/cf1b3c6d-4742-4037-96f4-60541b0b9ab2">
