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

<img width="1420" alt="image" src="https://github.com/prady0t/LFX-policy-exception-task/assets/99216956/ed81d217-0480-4a31-a473-327e975984f2">


As we can see resource creation was blocked due to above policy.

---

# Applying PolicyException


---

Applying `policy-exception.yaml` after creating a `delta` namespace:

<img width="1435" alt="Screenshot 2023-08-07 at 11 29 22 PM" src="https://github.com/prady0t/LFX-policy-exception-task/assets/99216956/cf1b3c6d-4742-4037-96f4-60541b0b9ab2">

We first need to set `enablePolicyException` flag to true. We can do it here: https://github.com/kyverno/kyverno/blob/v1.10.2/charts/kyverno/values.yaml#L390

<img width="1424" alt="Screenshot 2023-08-11 at 9 00 54 PM" src="https://github.com/prady0t/LFX-policy-exception-task/assets/99216956/6e624f53-76c2-4e92-9741-3bda01b159e0">

As we can see the warning message is gone!

---

Now applying `should-fail.yaml` again:

<img width="1424" alt="Screenshot 2023-08-11 at 9 03 29 PM" src="https://github.com/prady0t/LFX-policy-exception-task/assets/99216956/7f309a99-aa0d-43c5-8dda-86c95bd89796">

As we can see, `should-fail.yam` was allowed to be created as an exception but only in the `delta` namespace.


