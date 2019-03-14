---
title: "KIP Lifecycle"
permalink: /docs/kip-lifecycle/
excerpt: "Processes are important concepts in modern society and they help controlling, documenting and standardizing the interactions between businesses, consumers, governments, individuals and other organizations..."
last_modified_at: 2019-03-08T03:00:00-05:00
redirect_from:
  - /theme-setup/
toc: true
---

# Introduction

Processes are important concepts in modern society and they help controlling, documenting and standardizing the interactions between businesses, consumers, governments, individuals and other organizations. Tasks, roles, artifacts, goals, rules and their relationships are central abstractions processes use to determine stepwise recipes used by individuals and systems when navigating through a typical [procedure](), such as _Claiming Insurance_ or _Buying Airline Tickets_. Processes can also be materialized using Process Modeling Languages such as [BPMN]() (Business Process Management Notation), [PetriNets]() or [YAWL]() (Yet Another Workflow Language), which can be fed to a workflow automation platform for (semi-)automatic [execution](), [analysis]() or [simulation](). 

Processes can be found in "simple scenarios" such as in our daily visit to a coffee-shop, where baristas are prepping several different types of Lattes, Cappuccinos, Macchiatos, Iced Coffees, etc., each order following a combination of pre-defined recipes (kind of processes) and user defined customization (process tailoring) based on several types of coffee beans, different types of milk, special shots for flavoring, etc. Processes can also be present in complex scenarios such as being treated for a disease, where doctors, nurses, patient and hospitals collaborate to deal with a sophisticated web of information that relates symptoms, diseases, treatment procedures and resource allocation.

Some processes are perceived as streamlined procedures (Fig.1 - left) that regulate and systematize each individual participation while indicating the required flow of actions and information. However, with the rise of knowledge-based industries such as financial, health care, software development and insurance, process participants are said to be knowledge-workers(KWs) that should be supported by a flexible computational infrastructure  that do not constrain decisions at run-time. In such a modern industry, process execution depends on an intricate combination of context dependent information, emerging actions/tasks and collaboration (Fig.1 - right), where individuals take a special place as they typically use explicit but surely implicit knowledge to make decisions. 

<center>
 <img src="../images/perceived.png" alt="Perceived vs Real Processes"/>
 <b>Fig1. Perceived vs Real Processes</b>
</center>


Literature from process management brings the concepts of [Hybrid Processes](), [Flexible Processes]() and [Knowledge Intensive Processes]() (KIPs) to capture the uncertainties found in collaborative, goal-oriented, knowledge dependent and non-repeatable processes. For example, KIPs can _"range from partially structured processes occurring when the overall workflow is not explicitly defined, but the existence of policies and regulations supports the identification of structured fragments; to unstructured processes appearing when the participants define the activities to be executed."_  Although we believe KIPs are a good fit to capture the complexity imposed by the knowledge-based industries, the unpredictability of modern individual-to-organization interactions aggregates extra complexity. In this scenario, achieving a goal may require KIPs to crosscut, be combined or be partially fulfilled, imposing process management techniques to extrapolate processes' start-event and end-event boundaries to help [process navigation]() and/or discover [process trends]() and [process anomalies]().


This website is dedicated to explore the Knowledge Intensive Processes (KIPs) lifecycle and how it can be combined with [Workgraphs](https://www.wired.com/2013/10/its-time-to-focus-on-the-work-graph-not-social-networks-at-work/) to improve process management. Workgraphs _"consists of the units of work (tasks, ideas, clients, goals, agenda items); information about that work (relevant conversations, files, status, metadata); how it all fits together; and then the people involved with the work (who’s responsible for what? which people need to be kept in the loop?)"_, providing a flexible conceptual framework to address modern individual-to-organization interactions.  

This website is supported by several professors and grad students and it is a joint initiative involving the [Federal University of Rio de Janeiro-Brazil]() and the [University of Waterloo-Canada](). We also have sponsorship from COMAP?OWSE?.




# Motivating Examples

Knowledge Intensive Processes are everywhere but sometimes they are recognized as simple prescriptive processes. By prescriptive processes we mean processes that can be executed as is, such as in a car assembly line where parts are fed in one end of the line and cars are deterministically assembled (sometimes with the help of individuals). However modern processes typically support individuals in achieving their goals and typically deviate from the original model to accommodate specific and unplanned needs. In order to better expose the KIP phenomenon this section brings several motivating examples to expose how process are in fact complex and non-deterministic.



<table style="width:100%">
  <tr>
    <th>Process</th>
    <th>Description</th>
  </tr>
  <tr>
    <td><left><a href="./trip_plan/tp_bigpicture.html">Trip Planning</a></left></td>
    <td><justify>The Trip Planning process attempts to support a traveler to plan a trip.</justify></td>
  </tr>
  <tr>
    <td><left><a href="./fracture_clinic/fc_bigpicture.html">Fracture Clinic</a></left></td>
    <td><justify>The Fracture Clinic process ....</justify></td>
  </tr>
  <tr>
    <td><left><a href="./agile_sdp/sdp_bigpicture.html">Agile Software Process</a></left></td>
    <td><justify>The Agile Software Process ....</justify></td>
  </tr>
</table>



# KIP Life cycle

 A process life cycle can be seen as a collection of _stages_ and associated _operations_ that allow intra or inter stages transitions. A _Process Stage_ can be defined as a place sharing common definitions such as a common metamodel or the same representation language. For example a Java program may seen as having two stages, one as the Java source-code and another as the Java byte-code. The Java source-code is defined by the [Java grammar](https://docs.oracle.com/javase/specs/jls/se7/html/jls-18.html) while the Java byte-code has it's own [file format](https://docs.oracle.com/javase/specs/jvms/se7/html/jvms-4.html).
 _Transitions_  can be defined as operations allowing concepts (files) moving from one stage to another (inter stage transition) or staying in the same stage with a different configuration (intra stage transition). Going back to the Java program example we can see the Java compiler as an inter stage transition as it compiles Java source-code into Java byte-code. On the other hand, a Java refactoring tool can be seen as an intra stage transition as the input and output files are both Java source-code.  
 Using stages and transitions abstractions to understand the life cycle for knowledge intensive processes allows us to isolate and dissect concepts according to an specific rationale, and provide a didactic and systematic way to explore the phenomena. Moreover, stages and transitions abstractions are commonly used in Model Driven Engineering so we can leverage on some of its frameworks and tools. 

To understand knowledge intensive processes' life cycle, we first need to walk-through process models. A process model indicates the elements that can be used as abstractions to represent real world scenarios. Process Models can be formal or informal. A _formal process model_ precisely describes a flow of work and is typically executed using a Workflow Management System (WMS) or a Process Aware Information System (PAIS). On the other hand an _informal process model_ is usually interpreted by humans and used as a discussion or documentation tool.


A process model can be represented with several languages such as [YAWL](), [BPMN](), [UML Activity Diagrams]() or [Petri Nets](). Although most languages share some similarities and are capable of representing process abstractions such as activities, sequencing and decisions, we will illustrate most of the process models used in this text with BPMN (Business Process Modeling Notation) as BPMN is recognized as the de facto process modeling language. We will also use CMMN (Case Management Modeling Notation), as CMMN allows representing flexible workflows that can be called from BPMN process or executed standalone. Both notations, BPMN and CMMN, are supported by several tool vendors (SAP, IBM, BizAgi, Signavio, Camunda, etc.) and can describe formal or informal processes. It is important to mention KIPs may require other abstractions than those found in BPMN and CMMN as exposed in [KIPO](https://link.springer.com/article/10.1007/s10270-014-0397-1), but we will annotate the model when required.  


## BPMN
A BPMN model allows representing activities that are organized in a workflow. Activities represent actions that can be executed by humans, external systems or other processes. The workflow indicates the sequence in which activities should be executed. The workflow may also contain gateways to indicate conditional or parallel flows and loops. Fig. 1 represents a simple _Addition Process_  starting with an activity (_Get Numbers_) to obtain the input numbers. Then the process validates those numbers (_Validate Numbers_) and moves on to calculate the sum (_Calculate Sum_) if the numbers are valid; if not valid, the process flow goes back to get new input numbers.

<center>
 <img src="../images/sum.png" alt="Simple Addition Process"/>
 Fig1. Simple Addition Process
</center>


BPMN has several modeling elements to represent complex processes (events, pools, lanes, subprocesses, etc) that we will explain when needed. More information on BPMN models can be found [here](http://www.bpmnquickguide.com/quickguide/index.html?bpmn_examples.htm) and [the official documentation here](https://www.omg.org/spec/BPMN/2.0/).

## CMMN

A CMMN model allows representing flexible processes often called cases. Besides representing activities likewise in BPMN, a case can contain discretionary elements that may or may not be executed. For example, a discretionary activity indicates such action is not mandatory to complete the process and may be skipped depending on the process execution context.
Another important difference between BPMN and CMMN is how they represent sequences. In BPMN sequences are represented as directed edges connecting two model elements whereas in CMMN sequences can be modeled using connections and sentries (entry or exit criteria). For example, Fig2 illustrates the same _Addition Process_ using CMMN where the _Get Numbers_ and _Calculate Sum_ activities are connected using a dashed-dot line and a sentry (shallow diamond). The dashed-dot line is decorated with the term _complete_ and is combined with the sentry to indicate the _Calculate Sum_ activity can only start when the _Get Numbers_ activity is completed, thus representing a sequence.

Fig2 also represents the activity _Validate Numbers_ decorated with a dashed line to indicate such activity is discretionary. Different from the BPMN version of the _Addition Process_ that uses a gateway to represent an optional flow, the CMMN model leaves the decision to apply or not apply validation to the case worker. As a result, when the CMMN version of the _Addition Process_ process starts the _Get Numbers_  activity will be available to execute but _Validate Numbers_ and _Calculate Sum_ will become available only when _Get Numbers_ is completed. Given _Validate Numbers_ is discretionary, the process may execute _Calculate Sum_ without waiting for the validation action.

<center>
 <img src="../images/sum_flex.png" alt="Simple Addition Process in CMMN"/>
 Fig2. Simple Addition Process in CMMN
</center>

CMMN has also several other modeling elements (stages, milestones, case files, etc.) that we will explain when needed. We found a nice explanation for CMMN [here](http://knut.hinkelmann.ch/lectures/bpm2015-16/04_CMMN.pdf) and the [official documentation here](https://www.omg.org/spec/CMMN/About-CMMN/).

## Life cycle

A [life cycle](https://www.merriam-webster.com/dictionary/life%20cycle) is defined as "_a series of stages through which something (such as an individual, culture, or manufactured product) passes during its lifetime._" Processes have life cycles as they are created, executed and in some way finalized. We define the pre-birth stage of a process as the _Conceptual Stage_ where processes are experimented without paying attention to the representation language. Then a process can be _materialized_ using a formal representation language as a process model and move on to the _Process Model Stage_. Representing process models with a formal notation is important as it facilitates using several analytical tools such as model-checkers, quality assessment, workflow management systems, compliance monitoring, process mining, etc. Moreover, using a standard notation such as BPMN and CMMN promotes information sharing among the process community.

The _Working Plan_ is the next stage, when the Process Model can be _instantiated_ into several different instances. These instances can also be seen as each time the process is executed, totally or partially. At this stage, workers can work on specific chunks of tasks that have information such as their own due date, for example, and are part of a bigger project plan. 
_Logs_ are generated for each step of the instance execution, called _enactments_. This is the next stage of the life cycle. Whether each chunk of the instance is created or edited, modifications will be logged. These logs enable future analysis on how much compliant the execution was in regard to the Process Model. 

More details on each of the stages and transitions are below. 

<!-- The process management literature uses extensively the PDCA (plan-do-control-act) cycle to demonstrate 
<!--runtime vs design time vs conception time vs analysis runtime
PDCA
In order to dissect the concepts related to knowledge intensive process one must understand the  -->

## KIP Stages

<center>
 <img src="../images/kip-lifecycle.png" alt="KIP Lifecycle"/>
 Fig3. KIP Lifecycle
</center>

***

### Conceptual

Tacit knowledge is a big asset when performing knowledge-intensive processes. Although not explicitly materialized, tacit knowledge, which can also be seen as the experience of the worker, comprises one of the elements in the Conceptual View. Bodies of knowledge are also part of this Conceptual View. Examples of bodies of knowledge are knowledge bases, wikis, product reference manuals and documentation, and even maturity models or ISO documentations. Conceptual information can be either expressed in Natural Language or Structured Natural Language.


***

### Process Model

Process Model stage is when processes can be modeled and expressed into a set of activities and their dependencies. Processes are extracted (reified) from the available concepts (Conceptual View), and created according to the methodology of the process defined. Processes have information such as the activity name, role, artifact, flow, decision, event, and rule.

- *Activity* is the identification a piece of work that needs to be performed when executing the process.
- *Role* is the identification of which department, person or external parties are responsible for the execution of the activities.
- *Artifact* is the data that can be used as input or is the output of each activity. 
- *Flow* is the direction of the activity. It indicates whatever occurs before and after each activity.
- *Decision* is when there is the need to act upon occurrences that are optional. It can either result in the execution of an activity, or multiple activities, as well as it can lead to another decision or artifact.
- *Events* are instant occurrences in the process. They usually have a cause and an impact.
- *Rules* can be defined as the constraints that processes should consider when executed.

Processes’ activities can be tailored or merged. Tailoring means It is possible to customize a process for a specific instance execution on the next stage - the Work Plan - and merging means it is possible to execute two or more process activities at once. Merging activities also means changes will occur from this stage of the life cycle on. 


***

### Working Plan

The Working Plan stage represents the moment process activities, methodology, technical tacit or explicit knowledge are represented by chunks of work meant to be done. One process generates one or more work plans. One working plan has information such as task, person, milestone, flow, decision, event and iteration. 

- *Task* is a chunk of executable work.
- *Person* is whoever is responsible for working on that task. This person should also be responsible for communicating occurrences while working on each task. 
- *Milestone* is the goal that a set of tasks is supposed to reach. 
- *Flow* is the indication of which task is executed before and which task is executed after a task.
- *Decision* …
- *Event* … 
- *Iteration* is each set of tasks that can produce a minimum deliverable. The tasks to be executed in each iteration are selected at total discretion of the project manager and team, according to what’s been agreed with the client/stakeholders. 

Communications, task length definition in this stage depend on people, which makes the process vary according to decisions made when either planning or executing a task. What information is relevant to a person can also vary. These characteristics of knowledge-intensive processes are evident at this stage. 


***

### Log

When each task is executed at the Working Plan stage, i.e, a person performed the work described in a task, the task is updated with information regarding the execution. Information such as date and hour of completion, who was responsible for completing the task, and all sorts of information can be collected regarding a task and its workflow. 

Logs allow the identification of repetitive patterns during execution, which can become improvements in the process. 

Next, each transformation tasks can undergo will be detailed.

***


## KIP Transitions


Although using standard processes result in positive outcomes such as predictability, performance and reliability, different businesses and environments might have their own specific requirements. To comply with these differentials, a standard process might need to endure minor changes. These changes can be reification, tailoring or merging processes and/or its activities. In other words, a process suffers adaptations in order to comply with specific needs of organizations or projects. 

Each of these adaptations can result in one or multiple process transformations. These transformations are specific and different throughout each stage change. Also, processes can suffer instantiation, enactment and improvements, even when they are not necessarily changed between stages. Read below to understand the differences of each transformation and/or adaptation processes can undergo. 

***

### Reification

This transformation represents when the concepts from the Conceptual View are transformed in processes. This means this process will now have a starting point, a flow, indications of responsibilities for groups of process activities, i.e., will have incorporated the structured elements that belong to the Conceptual View. The figure below illustrate the Conceptual view as a blue cloud with some concepts. All 4 processes (P1, P2, P3 and P4) are reified from the concepts in the cloud. These are definitions coming from and based on extensive research and best-practices on software development. The concepts in the cloud are typically represented in natural language or non-formal representations, which demands an expert to transform these concepts in processes (reification). 

<center>
 <img src="../images/ReificationExample11.png" alt="1st Reification Example"/>
 Fig. Illustration of Reification procedure concepts turning into processes.
</center>

Let's try to make things clear with an example, represented in BPMN. Let's suppose a project manager is defining tasks for a project, and she/he gathered some concepts with the company's VP after a long meeting. The new reified process can be something like: 

<center>
 <img src="../images/ReificationExample2.png" alt="2nd Reification Example"/>
 Fig. Illustration of reified process.
</center>

If at this point you're thinking "this is really hard to predict and it's a very creative procedure", guess what? You're so right!! And I don't mean to be mean, but there's some other aspects to consider such as time, team expertise, budget, technologies... None of these were in the conceptual view, right? That is why there are other transformations that are very likely to happen. Next topic will demonstrate the next one :) 


***

### Tailoring

Processes may need to be modified to comply with business or environment needs. These modifications are called tailoring. In other words, a main established process will be adapted when running certain instances. For example, if one project of a company works with hazardous materials, this project might need to run different steps in order to comply with safety obligations, but at the same time, this project also runs the main established organizational process. 
One of the modification operations a process can experience is Merge. This means two or more process activities can be merged into one. 

As an example, let's suppose a worker has to collect, verify and store measures (e.g., size and weight) of parcels that are supposed to be mailed to clients, so a system can forsee delivery expenses. 

A simple example using a common notation (BPMN) is shown below. 

After posting all parcels in the post office service, some prices may vary. The original process does not consider that measures and prices might have to be updated. A tailored process to include this unforeseen activity is illustrated below. One process activity was added to the original process.

<center>
 <img src="../images/TailoringExample.png" alt="1st Tailoring Example using BPMN"/>
 Fig. 1st Tailoring example using BPMN.
</center>

Another (simpler) example is when an online store starts accepting debit as payment method for centain cases (for example, if a client purchase is over $100). Then, the debit card option has to be added to the process. This can be done using Tailoring. The blue elements below are the elements that were added during this process tailoring. 

<center>
 <img src="../images/TailoringExample2.png" alt="2nd Tailoring Example using BPMN"/>
 Fig. 2nd Tailoring example using BPMN.
</center>

Source: PILLAT, R. (2018). BPMNt: A proposal for flexible process tailoring representation in BPMN. Tese de Doutorado. Universidade Federal do Rio de Janeiro, Brasil. 
https://www.cos.ufrj.br/uploadfile/publicacao/2825.pdf


***

### Instantiation

Instantiation occurs when processes become executable chunks of work and a working plan is materialized. It is the transformation between process and actual work plans. The process is defined and every time the process is executed, entirely or partially, it generates a new instance.

Let's suppose a person works in a lingerie store, which every year showcases products and the most beautiful models of the world takes the catwalk wearing super expensive bras (we're not citing any names here!!). The cashier follows the process below when each customer buys fragrances, purses or any other product(s). 

<center>
 <img src="../images/InstantiationExample.png" alt="Instantiation Example using BPMN"/>
 Fig. Instantiation example using BPMN.
</center>

***

### Execution/Enactment

The execution of the Work plan is called enactment. Through enactment it is possible to generate logs of work plans executions. For every time ~ the very famous lingerie store cashier ~ follows the instantiated process, and a purchase is associated to a number (purchase 002 of March 1st, 2018), and the receptionist at a certain store says "Good morning and welcome!" to each client, this means the processes were enacted. 

Every June (the foundation month of the brand), the main store located in NYC gives away free samples of new fragrances. Although not a formalized process activity, it must be something consistent every June.  

<center>
 <img src="../images/EnactmentExample.png" alt="Enactment Example using BPMN"/>
 Fig. Enactment example using BPMN.
</center>

***

### Improvement

After enactment, logs of each process and instance execution are recorded. Analyzing these logs, looking either for pattern repetition or activities not executed, can be used as input to process Improvement. 

Still on the famous lingerie store example, let's suppose that a certain department noticed the NYC store is the store that sells most of the new fragrances, and when analyzing the logs of the enacted process, they noticed it's the only store giving away free samples in June. Then, the main process can be improved, so every store gives free samples, in an attempt to increase new fragrance sales in every store. 


***