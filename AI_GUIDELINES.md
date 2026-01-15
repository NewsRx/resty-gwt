<!--
  Copyright (C) 2026 NewsRx LLC. All rights reserved.
  Edits:
    2026-01-15: Michael Conrad (michael@newsrx.com) / AI Agent (Junie)
-->
# AI Guidelines
<!--
  NOTE: This file exists solely for human review. It is an English language expanded version 
  with explanatory notes of the AI instructions found in .junie/guidelines.md.
-->

This document contains the guidelines and instructions for AI agents working on the NewsRx project.

### Project Overview
- **Technology Stack**: Java 21, Python 3.12, Gradle, Spring Boot (Tomcat 10), GWT (Google Web Toolkit).
- **IDE**: Primarily IntelliJ IDEA or PyCharm.
- **Project Structure**: Multi-module Gradle project with Python integration.

### Long-term Goals
- **GWT**: Transition all remaining JSNI code to JSINTEROPT.
- **REST API**: Switch from Jersey to Spring Boot for all RESTful services.
- **Stripe**: Complete removal of Stripe related code and modules from the project.
- **Xignite**: Complete removal of Xignite related code and modules from the project.
- **Stockmarket**: Complete removal of the stockmarket module and related code from the project.
- See [ROADMAP.md](../ROADMAP.md) for detailed migration steps.

### AI Assistance Guidelines

#### 1. Consistency
Follow the existing coding style and patterns in the project. Use the same naming conventions (PascalCase for Java classes, snake_case for Python functions/variables).

#### 2. Efficiency
Avoid using scripts to update files; use direct edits or specialized tools instead.

#### 3. Technology Specifics
- **Java**: Use modern Java features where appropriate. Use JDK 21 for non-GWT related modules, and JDK 17 for GWT related modules and shared POJO projects. Ensure that the correct JDK is referenced in each `build.gradle`.
- **Python**: Follow PEP 8 and use type hints (Python 3.10+).
- **Spring Boot**: Follow Spring Boot best practices for dependency injection, REST controllers, and services.
- **GWT**: Be mindful of GWT-specific constraints. Avoid GWT JSNI and use JSINTEROPT instead.
- **Gradle**: Ensure compatibility with the multi-module structure. Use latest industry standards. Plugin versions should only be set in `settings.gradle`.

#### 4. IDE Integration
- Prefer solutions that integrate well with IntelliJ IDEA / PyCharm.
- Respect IDEA-specific configurations (e.g., `.idea` folder settings).

#### 5. Documentation
- Use KDoc-style comments (or standard Javadoc for Java).
- Keep comments concise and relevant.

#### 6. Testing
- Write tests for new functionality using the project's existing testing framework.

#### 7. Code Style
- **Indentation**: 4 spaces.
- **Import Order**: Group imports by package, with external libraries first followed by project-internal packages.

#### 8. Best Practices
- Prefer readability and maintainability over clever code.
- Ensure proper error handling and logging.
- Avoid hardcoding values; use configuration files or constants.

#### 9. Guideline Storage & SPR
- Use Sparse Priming Representation (SPR) for complex concepts.
- Refer to `.junie/spr-pack.md` and `.junie/spr-unpack.md`.

#### 10. Copyright & Attribution
- Always add a copyright header to each file that does not contain one.
- **Copyright Holder**: NewsRx LLC.
- Inspect git user/email for proper attribution.
- Add an `Edits` section to the copyright header of each modified file.

#### 11. Changelog Management
- Maintain a top-level `CHANGELOG.md` in reverse date order.
- Each module should have its own `CHANGELOG.md` file that is kept up-to-date.
- Group changes by date and indicate authors.

#### 12. Updating Guidelines
- Guidelines are updated when the user says "remember something".
- Keep `AI_GUIDELINES.md` (this file) in sync with `.junie/guidelines.md`.
- Always keep the submodule AI guideline files up-to-date in addition to the top-level AI guideline files. The submodule AI guideline files only need updating if a top-level change directly impacts the submodule.
- Commit and push guideline changes immediately.

#### 13. VCS Guidelines
- Always use `git pull --rebase` when pulling changes to maintain a linear history.
- Commit and push changes immediately after updating guidelines or critical files.

#### 14. Temporary Files & Scripts
- Use `/tmp`, `/var/tmp`, or a project-specific `tmp` folder.
- Ensure project-specific `tmp` folders are git-ignored.
