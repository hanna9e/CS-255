# CS 255: System Analysis and Design – DriverPass

This repository holds my portfolio work from CS 255 at SNHU:

- [`DriverPass_Business_Requirements_Document.docx`](DriverPass_Business_Requirements_Document.docx): Project One, the requirements gathered from the client interview
- [`DriverPass_System_Design_Document.docx`](DriverPass_System_Design_Document.docx): Project Two, the UML diagrams and technical requirements for the system

## Reflection

### Briefly summarize the DriverPass project. Who was the client? What type of system did they want you to design?

The client was DriverPass, a driver-training company owned by Liam. He started it because so many people fail their DMV driving test, mostly because they study old test questions instead of actually learning the rules and getting time behind the wheel. DriverPass wanted a web-based, cloud-hosted system where customers can register, buy one of three training packages, take online classes and practice tests, and book two-hour driving lessons with an instructor. The system also had to support the staff behind the scenes: the secretary booking lessons over the phone, the IT officer managing accounts, and Liam pulling reports on who changed what.

### What did you do particularly well?

I think I did a good job of tracing the client's needs all the way through both documents. Small details from the interview, like the drop-off location defaulting to the pickup location, logging who created or changed a reservation, and not storing the card security code, show up in the requirements and then again in the activity, sequence, and class diagrams. I'm also happy with how the design handles double booking. The availability check is in the activity diagram, the sequence diagram shows the system locking the slot before saving, and the technical requirements explain how the database transaction makes that work.

### If you could choose one part of your work on these documents to revise, what would you pick? How would you improve it?

I'd revise the business requirements around scheduling rules. The interview covered how lessons are booked, but not what happens with late cancellations, no-shows, or a driver calling in sick. I made assumptions to fill some of those gaps, but in a real project I'd go back to Liam with follow-up questions and add specific requirements, for example a cancellation cutoff and a rule for reassigning lessons when a driver is out. Those rules affect the scheduling logic, so leaving them vague would cause problems once developers started building.

### How did you interpret the user's needs and implement them into your system design? Why is it so important to consider the user's needs when designing?

I started with the interview and sorted what each person needed: customers, the secretary, drivers, Ian, and Liam. Then I turned that into functional and nonfunctional requirements. Each requirement then became something concrete in the design: an actor or use case in the use case diagram, a step or decision in an activity diagram, or a class and attribute in the class diagram. For example, Liam wanting to know who canceled a reservation became the ActivityLog class and the "Record Appointment Change Log" use case that every booking change includes. Considering user needs matters because a system can be technically solid and still fail if it doesn't solve the problem people actually have. If you design without the users in mind, you end up building features nobody asked for and missing the ones they really needed.

### How do you approach designing software? What techniques or strategies would you use in the future to analyze and design a system?

I start by understanding the problem before thinking about the solution: who the users are, what they're trying to do, and what constraints exist around time, budget, and technology. After that, I break the system down using a mix of models. Use case diagrams show the big picture, activity and sequence diagrams show how specific processes flow, and class diagrams show what data the system needs. In the future I'd keep using that blended object-and-process approach, along with interviews and follow-up questions, prototypes or UI sketches for early feedback, and a Gantt chart to keep the schedule realistic. I'd also review diagrams with the client and the developers early, since catching a misunderstanding in a diagram is a lot cheaper than catching it in code.
