---
layout: post
title:  "Functional requirements"
date:   2020-05-09
categories: innovation
---
BUILDING EXCEPTIONAL PRODUCTS IS HARD. I have had the good fortune to work with software engineers and data scientists who are some of the smartest, most capable people in their field. On several projects, the team worked together to build an amazing product, only to discover that the final product did not solve the customer's needs. In some instances, the engineering team delivered a product which was different from the solution envisioned by the product team. Occasionally, the product team got what they asked for but the product did not acheive the anticipated results with the customer.

Functional requirements improve communication between the engineering team and the product team. There are numerous ancillary benefits of documenting functional requirements. Below I have laid out a framework for functional requirements which can be used by teams building digital products of any sort. I advocate for the use of functional requirements on both software engineering and data science teams. 

1. **Begin with a user story.**
<br><br>The product exists for the user, and the ultimate motivation for any technical task should be its impact on the user. Any new software engineering features should improve the user experience. Data science projects should also seek to answer questions which will impact the user.
<br><br>It can be difficult to identify the user story for tasks removed from the user interface. While the user impact may not be immediately obvious, the backend infrastructure of your software does have a substantial, and measurable, impact on the user experience. For example, improving the speed of database queries will increase the page load time. Even documenting your code will ultimately have a positive impact on the user experience, by empowering your team to resolve bugs faster.

2. **Include a solution roadmap.**
<br><br>There are a number of benefits to having the product team, and the engineering team, agree on a solution roadmap. A roadmap is simply an abstracted plan of the engineering solution. The roadmap describes the solution, step by step.
<br><br>By laying out a roadmap, engineering teams can anticipate potential obstacles early in the development process. The roadmap also increases communication and understanding between the engineering team and the product team. Data science solutions can yield different results, depending on the implementation. Establishing a development plan ensures that both the product team and the engineering team are in consensus regarding the abstracted implementation.

3. **Document the inputs and outputs, of each step.**
<br><br>Code often starts out as an MVP developed quickly to validate a solution. During the prototyping phase, functions change, files get moved around, and the overall structure is subject to change. Development code is usually messy.
<br><br>Once the solution has been validated, and the team makes the decision to stick with the MVP, it is important to repackage the solution as a production code set. Production code should have ample documentation, and should be as streamlined as possible. Any steps which can be eliminated, should be eliminated. An effective way to identify, and streamline functionality, is to list the inputs and outputs of each step.

4. **Define acceptance criteria.**
<br><br>Acceptance criteria make the solution *measureable*. Once the engineering team has a destination, it is possible measure progress, and anticipate the time remaining to completion. The acceptance criteria empower the engineering team to act with autonomy. Using the acceptance criteria rubric, the engineering team can make design decisions about *how* to implement the solution.

The greatest benefit of formalizing technical requirements is the communication which ensues between the product team and the engineering team. I have found the above framework to work on my team, but each team is unique. Simply establishing the habit of documenting technical requirements will yield tremendous benefits for any team.