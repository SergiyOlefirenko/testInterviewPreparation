https://www.softwaretestinghelp.com/software-development-life-cycle-sdlc/

### Software Development Life Cycle
SDLC is a process that define the various stages involed in the development of SW for delivering a high-quality product. SDLC stages cover the complete life cycle of a SW i.e. from inception to retirement of the product.

***SDLC Phases***
- **Requirement gathering and analysis.** During this phase, all relevant information is collected from the customer to develop a product as per their expectation. Any ambiguties must be resolved in this phase only.
- **Design.** In this phase, the requirement gathered in the SRS document is used as an input and SW architecture that is used for implementing system.
- **Implementation or coding.** Implementation/Coding starts once the developer gets the Design document. The SW design is translated into source code. All the components of the SW are implemented in thsi phase.
- **Testing.** Testing starts once the conding is complete and the modules are released for testing. In ths phase, the developed SW is tested thorougly and any defects found are assigned to developers to get them fixed.
- **Deployment.** Once the product is tested, it is deployed in the production env or first UAT is done depending on the customer expectation.
- **Maintenance.** After the deployment of a product on the production environment, maintenance of the product i.e. if any issue comes up and neds to be fixed or any enhancement is to be done is taken care by the developers.

<br>

***SDLC Models***
1. **Waterfall Model** - very first model that is used in SDLC. It is also known as the linear sequential model. In this model, the outcome of one phase is the input for the next phase. Development of the next phase starts only when the previous phase is complete.
    - *Advantages:*
        - waterfall modelis the simple model which can be easily understood and is the one in which all the phases are done step by step.
        - deliverables of each phase are well defined, and this leads ot no complexity and makes the project easily manageable.
    - *Disadvantages:*
        - time-consuming and cannot be used in the short duration projects as in this model a new phase connot be started until the ongoing phase is completed.
        - cannot be used for the projects which have uncertain requirement or wherein the requirement keeps on changing.
2. **V-Shaped Model** is also know as verification and validation model. In this model Verification and Validation go hand in hand i.e. development and testing goes in parallel. V model and waterfall model are the same except that the test planning and testing start at an early stage in V-Model.
    - *Advantages:*
        - is is simple and easily understandable model.
        - V-model approach is good for smaller projects wherein the requirement is defined and it freezes in the early stage.
        - it si a systematic and disciplined model which results in high-quality product.
    - *Disadvatages:*
        - not good for ongoing projects.
        - requirement change at the later stage would cost too high.
3. **Prototype Model** is a model in which the prototype is developed prior to actual SW. Prototype models have limited functional capabilities and inefficient performance when compared to the actual SW. Dummy functions are used to create prototypes. This is a valuable mechanism for understanding the customer's needs. Customer's feedbacks are implemented and the prototype is again reviewed by the customer for any change. This process goes on until the model is accepted by the customer.
    - *Advantages:*
        - prototype model reudces the cost and time of development as the defects are found much earlier.
        - missing feature of functionality or a change in requirement can be identified in the evaluation phase and can be implemented in the refined prototype.
        - involement of a customer from the initial stage reduces any confusion in the requirement or understanding of any functionality.
    - *Disadvantages:*
        - since the customer is involved in every phase, the customer can change the requirement of the end product which increases the complexity of the scope and may increase the delivery time of the product.
4. **Spiral Model** includes iterative and prototype approach. Spiral model phases are followed in the iterations. The loops in the model represent the phase of the SDLC process i.e. the innermost loop is of requirement gathering and analysis which follows the Planning, Risk analysis, development, and evaluation. Next loop is designing followed by implementation and then testing.
    - *Advantages:*
        - risk analysis is done extencively using the prototype models.
        - any enhancement or change in the functionality can be done in the next iteration.
    - *Disadvantages:*
        - the spiral model is best suited for large projects only.
        - the cost can be high as it might take a large number of iterations which can lead to high time to reach the final product.
5. **Iterative Incremental Model** divides the product into small chunks.Each iteration goes through the phases namely Requirement Analysis, Designing, Coding, and Testing. Detailed planning is not required in iterations. Once the iteration is completed, a product is verified and is delivered to the customer for their evaluation and feedback. Customer's feedback is implemented in the next iteration along with the newly added feature.
    - *Advantages:*
        - any change in the requirement can  be easily done and would not cost as there is a scope of incorporating the new requirement in the next iteration.
        - risk is analyzed and identified at an early stage.
        - defects are detected at an early stage.
        - as the product is divided into smaller chunks it is easy to manage the product.
    - * Disadvantages:*
        - complete requirement and undestanding of a product are required to break down and build incrementally.
6. **Agile Model** is a combination of the iterative and incremental model. This model focuses more on flexibility while developing a product rather than on requirement. In Agile, a product is broken into small incremental builds. It is not developed as a complete product in one go. Each build increments in terms of features. The next build is built on previous functionality. In agile iterations are termed as sprints. Each sprint lasts for 2-4 weeks. At the end of each sprint, the product owner verifies the product and after this approval, it is delivered to the customer. Customer feedback is taken for improvement and his suggestions and enhancement are worked on in the next sprint. Testing is done in each sprint to minimize the risk of any failures.
    - *Advantages:*
        - it allows more flexibility to adapt to the changes.
        - the new feature can be added easily.
        - customer satisfaction as the feedback and suggestions are taken at every stage.
    - *Disadvantages:* 
        - lack of documentation.
        - agile needs experienced and highly skilled resources.
        - if a customer is not clear about how exactly they want the product to be, then the project would fail.
