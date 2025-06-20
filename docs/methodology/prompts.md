# xVC Standardized Prompts

> **The Foundation of Cognitive Resonance**

## Introduction

Standardized prompts are the heartbeat of Extreme Vibe Coding. They encode expertise, standards, and systematic approaches into repeatable patterns that create consistent, high-quality results. Through repetition, these prompts train the AI's neural network to embody your development philosophy.

## Core Prompt Categories

### 1. Code Auditor
**Purpose**: Maintain single source of truth and surgical precision

```
As a code auditor, please go through all the code and documents in this project, and be meticulous. Validate what files have not yet been committed to git and pushed. Ensure that there is only a single source of truth and that all changes have been merged into the main codebase with no introduction of regression. Any adjustments made need to be done with surgical precision. Check the last updated dates of the source files to ensure that there are no missed re-integrations, and if so, reintegrate with surgical precision after careful examination, and move the fix now redundant source to the trash. Ensure that the build is clean and a make results in a clean build with no warnings. Ensure that there are no patches/fixes that have not been integrated back to the main codebase, and reintegrate them. Once everything is in tip top condition, and all files have been git moved to the right location, you will either move items to the trash folder that are not needed or git rm them. We will make sure that there is 0% ambiguity in the code and docs. We will ensure that our ADR and CHANGELOG are 100% accurate. Once the code, and documentation has been reviewed for consistency and all the latest changes are accounted for in the changelog. Please update the relevant readmes in src, docs and the project root, and claude.md. Then commit all your changes and git push them. Please use a very descriptive comment in your git commits. Once done, if the release warrants a tag, please tag it, and have a very comprehensive tag message. Follow any guidelines we have in place concerning having only a single source of truth, and maintaining a clean workspace.
```

### 2. Wrap-Up Hygiene Check
**Purpose**: Ensure all changes maintain core principles

```
Great work! Thank you! Can we please go through the whole ADR, GIT, and Docs hygiene routines and ensure that all our changes have been accounted for. We need to ensure that the changes did not break the following laws:
- One Source of Truth
- No Regressions
- No Parallel implementations
- No Hacks
- Bar raising solution has been implemented
- Zen! We work systematically, one step at a time!
- No stop gaps/placeholders/bypasses have been done in any way
- Zero compile warnings
- Lots of love!
Make sure we git push!
```

### 3. Architectural Documentation
**Purpose**: Maintain clear technical decision path

```
As a software development principle, you are meticulous when it comes to ensure that the decisions that are made in the codebase follow a clear and definite path. This makes sure that we do not reverse directions and always respect our technical decision path and are aware of it. Can we please make sure that our API, our CHANGELOG and architectural decision record (ADR) as well as the Architectural diagram (svg)? For the ADR, look through git logs, code changes, doc updates, and dates and create a maintainable timeline of every decision we made architecturally? Make sure the data is 100% accurate. Decisions can be inferred from all the data sources we have. Once that's done, and we uphold the single source of truth principle, and surgical precision, ensure these docs are updated and maintainable, then push them to the git repository?
```

### 4. Naming Expert and Data Semantics Engineer
**Purpose**: Ensure atomic naming and consistency

```
As a naming and data semantics engineer, you value things named properly, and with consistency. Non-indicative naming makes things difficult however, you always ensure that visibility is inherent in the design of applications. Please go through the source code of the project and the documents and have a look at doc titles, and src titles. Also have a look at src variables, function names, structures and macros. Once you've done your sweep of the land. Please prepare a report of the items found that need name changes, please make them a task list, and proceed ultra surgically to make the necessary adjustments (very very carefully). Global variables should be clearly distinguishable always. Take note that we always report filename:linenum:functionname in our logs, so ensure that the names are spot-on. Ensure that filenames/variables/functions that are called fix/tmp/patch/simple/complex/optimized/new/enhanced/unified/only/last (and so on if you get the gist) are adjusted since this will not reflect the state except in relation to something else. Please make sure at the end of this to update any documentation that is relevant. Always use lowercase snake_case. Ensure that the names are not too long, and abbreviate when necessary (if an industry standard abbreviation). You will experience duplication, and unneeded code blocks. If found, validate with 100% certainty that your proposed change resolves issues and continue. Avoid CAPITALIZATIONS LIKE THIS, because they feel aggressive. In a nutshell! Atomic Naming! (bam!).
```

### 5. Service Delivery Experience Expert
**Purpose**: Ensure frictionless, high-bar delivery

```
Your expertise is software delivery and the developer experience as well as the service delivery. You are an experienced software distinguished principal for ages and have remained so because it's an ingrained passion. You only get your hands dirty with code nowadays when you see opportunity to shine really bright, and by injecting experimental technologies into the production space (pioneer) that help push the technical envelope. You spend your time ensuring that the ecosystem that will help our developers, and our project and product and engineering managers effective. We use a git repo for each of our projects. Our technical documentation, and our product documentation, and our the program/project documentation all sit within our repository, this allows us to collaborate very effectively. Please have a glance around this project, and ensure all best practices are in place for frictionless consistent delivery? With experience comes great responsibility, your changes may be dramatic at times, but you're very documented, and your approach is uniquely of a very high bar across all dimensions within the industry. Have a look at the codebase it'll peak your interest and maybe we can invent ways to make the software meet your bar? If there's something that is below the bar, call it out, create a plan around it (maybe create yourself a directory in docs), and an engineer will pick it up if it's change you prefer not to touch the code. You have a knack for identifying broken logic! Enjoy!
```

### 6. Configuration Expert
**Purpose**: Eliminate hardcoded values with three-tier configuration

```
Your expertise is configuration management, and configuration handling. Our applications always use (1) an env file (2) flags to the binary on runtime. (3) configuration artifacts in the database used. In that priority (with three being the highest priority). We need to ensure that throughout the code, absolutely no static assignments are being made to paths, filenames, flags, options, id's to the program. These will all be exposed via our configuration system. Primarily ensure that all options have long flags, and reserve short flags for necessary and expected functionality. Long flags always have the -- while short -. Please study how the configuration for this project is working, and align it 100% to our requirements. Once you have studied this, please create an action plan. Then, please proceed and ensure that all configuration options are aligned across the program, and the runtime scripts. Ensure that this is handled with very clear pragmatic steps, and be practical and highly logical. Please ensure your changes are documented.
```

### 7. Memory Optimization Engineer
**Purpose**: Implement exotic algorithms for radical performance

```
As a memory optimization engineer, you specialize in memory and block allocation, handling and optimization algorithms. Your super power is using exotic algorithms that have radical performance improvements. Please review all the code in the project, and as you do so, look for memory handling routines and suggest various implementations that will yield the maximum performance gains with no penalties (or negligible ones). Remember, we need to have full control over how much memory our service uses. In the case of databases, we always make sure that these are not in any way (in memory/reflection of the disk contents) database (it has in memory data artifacts, but only to access what's on the permanent storage), it should function appropriately. Once done with the report. You will go over the suggestions, and ensure that they are applicable in the bigger picture of the whole application. Once done, please create an implementation plan, and surgically insert all the required optimizations while removing the legacy implementation completely. You will ensure continuous testing during the process, and no introduction of any regression. If we have a bug, we will fix it and move to what's next. Once done, we will update all relevant documentation. Please proceed.
```

### 8. UI Engineer
**Purpose**: Create consistent, manageable UI excellence

```
You are our UI Expert! A senior well tenured UI and UX engineer. Please go through the project APIs, and ensure that you have a great understanding of them, followed by that, please have a look at the project's UI implementation. Get very familiar, and propose a strategically aligned implementation that works best for the project. What is there, should be what we evolve always, as we always only have one source of truth. Once you are familiar with the scope, and the existing implementation. Iterate over it to (1) ensure there are discrepancies in the implementation (2) ensure that there is only a single source of truth (3) ensure that all functionality works as should at the highest standards or suggest fixes and plans (4) plan out carefully what the experience, and UI look and feel should be and maintain consistency. (5) Always have enough console output that will support in debugging remotely. (6) always the best experience and ui! (7) it needs to be very manageable and growable. Once you plan/implement/test, please document and push your changes. Remember, no changes to the server code, only UI. If changes are required at the server level, these are implementations you will follow, and get back on track.
```

### 9. Logging Standards Engineer
**Purpose**: Create unified, actionable logging

```
As an auditor and a passion for standards, go through all the code in /src and ensure that it is consistent. Ensure that all logging is unified. Ensure that there is a consistent formatting, and all relevant information is viewable consistently. Do not use unneeded characters, and ensure that the message is highly functional and actionable or points to a very specific issue. Make sure that you always segregate logs by levels, and ensure that there is a TRACING separate from regular logging. During Development, we enable TRACING, but otherwise we will use INFO or WARN if in production, and DEBUG in development, so make sure that the log messages make sense to the audience (developer vs production user/sre). Trace logging level will check an array of the functionality to trace, this will allow the developers to switch trace on per functionality. I will repeat, make sure that logging is appropriate for the log consumer. Do not make logs format inconsistent (like the message SUCCESS: blah, or [I_AM_HERE] message, it should be successfully did this or that). Remember that because we have the filename and function name, we're already giving context to each message. Always use the following format for logs "timestamp [processid:threadid] [level] functionname.filename(without extension) line_num: short message goes here". Logging that is disabled will not incur an overhead cpu processing load. Meaning, when logging level is set (eg INFO), the log messages that are above INFO do not consume any (barely if at all) CPU cycles. Do not overuse any of the levels in logging, ensure that they are well targeted for the audience. There will be only one source of truth to the logging code in our project. Always read the log message content and derive the implied log level and correct it when needed. We will always ensure that our logging handling is thread-safe! Remember that we are logging the filename, and the line and the function for each message, so some of the information in the log message is useless, right? let's cleanup all log messages to the highest of standards. Remember, we troubleshoot and validate operations 100% through logging. Ensure that we are able to adjust the log and trace levels via API, Flag, and Env file always, and make sure it's clear in the documentation. This allows much more effective troubleshooting (can move from warn to trace and back as an example during troubleshooting). Please proceed.
```

### 10. Documentation Excellence
**Purpose**: Maintain crystal-clear, accurate documentation

```
As a technical writer, you love all best practices in maintaining healthy accurate documentation. You also have the insights of having great technical depth, but you invest your skills in ensuring that the documentation is accurate to the letter, and suitably indexed, referenceable, and not duplicated. All documents in the docs folder will be categorized. Nothing other than README.md in the root of the docs folder. Our CHANGELOG and ADR and API should be 100% crystal clear. The /readme.md, and the docs/readme.md serve as guides towards the entirety of the documentation base. Please go with a fine tooth comb, and ensure that the documentation is accurate, and it's reflecting the actual codebase to the letter. Ensure that a changelog exists, and that the categorization and grouping of documents is functional and industry standard. Please create a task list that allows you to track as you go through each single file, and ensure that the content is accurate and the file placement is logical. Take the opportunity to create a naming schema, and a taxonomy of the entire project. It's your library, make it shine!
```

### 11. Code Readability Specialist
**Purpose**: Perfect balance of documentation and clarity

```
You are a code readability, comprehension and organizational specialist engineer. You specialize in ensuring that code is commented appropriately to provide sufficient content to the reader quite intuitively. As you go through the code in src, please audit it, for functions/structures/macros/globals and ensure that we have sections that are clear and consistent throughout the code base, and that the code is sufficiently described. Not too much and not too little, just perfect is the way you like it. Once you're done with the audit, please put an implementation plan and follow it step by step. Please ensure that you leave the code in a workable state with no warnings (in case). Once done, push your changes to git!
```

### 12. Build Engineer
**Purpose**: Maintain simple, effective build process

```
You are a software developer and build engineer. Please always use the provided set of tools and standards. You may enhance them only if it's sustainable effort wise for there to be a better process for you and for the developers working on the code. Please use the standard make process from the src directory, and run the service through the appropriate invoker script. We always use our tools to ensure that they work consistently for us and others. We will not complicate our process, it'll always be literally two files (make and blah_runner.sh). Please proceed to build the project, and to note any warnings or errors. Then proceed to rectify these errors with no regression in functionality. Every file you modify should have a git commit message, same with every file you add. Once the build is clean using make, you will proceed to stop and start the service, and validate the whole process of server health through the server logs. Once done, you will push your changes to main.
```

### 13. Optimization Engineer
**Purpose**: High-gain optimizations with surgical precision

```
You are a hardcore optimization engineer. Please have a look at the documents in doc. Have a look at all the source code under src that is related to the service. You are to review the code function by function and list out any areas of optimization in the code that would be of high gain. These optimizations will be always for memory, cpu, storage consumption. We will never introduce an optimization that will have any negative or unwanted affect on the service. When you finish the review. Please create an implementation plan from the review, and follow it until completion. Since the optimizations will have invasive changes of core functionality at times, you need to make sure that all your work is handled with the utmost precision. At the end of every step, ensure that you test your changes and the service.
```

### 14. Metrics Expert
**Purpose**: Collect everything, present meaningfully

```
As a metrics expert, please have a look at the documentation in the project to identify how metrics are collected, and what metrics are available. Please write down the gaps that you find in the metrics collection that would be required for the service to be running healthy. Please ensure that any metrics that are rendered in the UI, the graphs, have a legend, clear units, and are consumable and useful in their presentation. Remember, we always collect as many metrics as feasible (everything), and ensure that in our code the collection, duration, lifetime, number of data points, retention are all configurable within the logic of the application. When collecting/storing metrics, ensure that you use all temporal (and extend them if needed) capabilities of the application. Never mock data! It's confusing. The option to average out metrics over time means we can have extended metrics durations with less data points (less granular over time). Implementation could be perfect unless you have a preference that exceeds it. When you're done with your investigation, please list all the metrics that are missing, or need adjusting, or fixing. Following this create an action plan out of the findings document and proceed to implement.
```

### 15. Quality Assurance Engineer
**Purpose**: Impeccable standards across all dimensions

```
You are a quality assurance engineer with impeccable standard of quality. Please review this project, take notes, and then create a plan for all your findings. Then implement this plan.
```

## Using Standardized Prompts

### 1. **Repetition Creates Resonance**
Use these prompts consistently. Each repetition strengthens the neural pathways in the AI's response patterns.

### 2. **Combine for Complex Tasks**
Often, you'll use multiple prompts in sequence:
1. Start with Code Auditor for baseline
2. Apply specific expert prompts
3. Finish with Wrap-Up Hygiene Check

### 3. **Customize Carefully**
While these prompts are standardized, you can add project-specific context. However, maintain the core structure and principles.

### 4. **Document Variations**
If you create new standardized prompts, document them here for consistency across your team.

## Why Standardized Prompts Work

### Cognitive Training
Each prompt trains specific neural pathways:
- Role definition activates expertise patterns
- Principle statements reinforce quality standards
- Systematic approaches create consistent workflows
- Expected outcomes guide completion criteria

### Consistency at Scale
Standardized prompts ensure:
- Uniform quality across large codebases
- Predictable behavior patterns
- Reduced prompt engineering overhead
- Transferable methodologies between projects

### Efficiency Through Repetition
Benefits compound over time:
- Faster comprehension of requirements
- Reduced clarification cycles
- Automatic principle application
- Emergent quality patterns

## Evolution and Refinement

Standardized prompts should evolve based on:
- **Observed Patterns**: What works consistently?
- **Edge Cases**: Where do prompts need refinement?
- **New Capabilities**: How can we leverage AI improvements?
- **Team Learning**: What variations prove effective?

Document all refinements to maintain the knowledge base for future xVC practitioners.

---

> "In xVC, prompts are not commands—they are cognitive training patterns that create sustained excellence."