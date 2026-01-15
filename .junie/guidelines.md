<!--
  Copyright (C) 2026 NewsRx LLC. All rights reserved.
  Edits:
    2026-01-15: Michael Conrad (michael@newsrx.com) / AI Agent (Junie)
-->
### Project Overview
- **Technology Stack**: Java 21, Python 3.12, Gradle, Spring Boot (Tomcat 10), GWT (Google Web Toolkit).
- **IDE**: Primarily IntelliJ IDEA or PyCharm.
- **Project Structure**: Multi-module Gradle project with Python integration.

13. **Long-term Goals**:
   - **GWT**: Transition all remaining JSNI code to JSINTEROPT.
   - **REST API**: Switch from Jersey to Spring Boot for all RESTful services.

### AI Assistance Guidelines
1. **Consistency**: Follow the existing coding style and patterns in the project. Use the same naming conventions (PascalCase for Java classes, snake_case for Python functions/variables).
2. **Technology Specifics**:
   - **Java**: Use modern Java features where appropriate. Use JDK 21 for non-GWT related modules, and JDK 17 for GWT related modules and shared POJO projects. Ensure that the correct JDK is referenced in each `build.gradle`. If any changes need to be made to ensure the Gradle build or the IntelliJ IDE is using the correct JDK, prompt the user with the need for the changes.
   - **Python**: Follow PEP 8 and use type hints (Python 3.10+). See `.junie/python.md` for more details.
   - **Spring Boot**: Follow Spring Boot best practices for dependency injection, REST controllers, and services.
   - **GWT**: Be mindful of GWT-specific constraints (e.g., client-side vs. server-side code, serializable objects). Avoid GWT JSNI and use JSINTEROPT instead. If JSNI code exists in files being edited, prompt the user with a suggestion for replacing it with JSINTEROPT (new class files can be created for this after approval).
   - **Gradle**: When modifying `build.gradle`, ensure compatibility with the existing multi-module structure. Use latest industry standards for `build.gradle` and `settings.gradle` files. Gradle plugin versions should only be set in `settings.gradle` files (centralized plugin management using `pluginManagement` or `plugins` block).
3. **IDE Integration**:
   - Prefer solutions that integrate well with IntelliJ IDEA / PyCharm.
   - Respect IDEA-specific configurations (e.g., `.idea` folder settings if present).
4. **Documentation**:
   - Use KDoc-style comments for documentation (or standard Javadoc for Java).
   - Keep comments concise and relevant.
5. **Testing**:
   - Write tests for new functionality using the project's existing testing framework (check `src/test` for examples).
6. **Code Style**:
   - Indentation: 4 spaces (standard for this project).
   - Import Order: Group imports by package, with external libraries first followed by project-internal packages.
7. **Best Practices**:
   - Prefer readability and maintainability over clever code.
   - Ensure proper error handling and logging.
   - Avoid hardcoding values; use configuration files or constants.

8. **Guideline Storage & SPR**:
   - For complex concepts or extensive documentation, consider using the Sparse Priming Representation (SPR) approach to keep guidelines concise and efficient for AI processing.
   - Use `.junie/spr-pack.md` as a guide for distilling information into SPR format.
   - Use `.junie/spr-unpack.md` for understanding how to reconstruct or expand on SPR-formatted guidelines.
   - Apply the SPR approach only where it provides clear benefits in brevity and conceptual clarity.

9. **Copyright & Attribution**:
   - Always add a copyright header to each file that does not contain one.
   - Copyright Holder: NewsRx LLC.
   - Always inspect the git user and email to determine who is doing the work for proper attributions.
   - For each file edited, add a comment section showing whom edited the file on what date, combine comments about edits together as appropriate.

10. **Changelog Management**:
    - Keep a top-level `CHANGELOG.md` file in the project root.
    - Each module should have its own `CHANGELOG.md` file that is kept up-to-date.
    - Format: Reverse date order (newest on top).
    - Changes by date should be grouped together.
    - Indicate the author(s) for each entry (user, AI agent, or combination).

11. **Updating Guidelines**:
   - When the user indicates to "remember something", these are direct instructions to update the AI guidelines with the new information provided by the user.
   - Incorporate the new information into the existing AI guidelines.
   - Keep the top-level `AI_GUIDELINES.md` file (for human review) in sync with these guidelines. `AI_GUIDELINES.md` is an English language expanded version with explanatory notes of these AI instructions.
   - In case of a conceptual conflict or conflicting instructions, do not update the guidelines file, ask the user for help.
   - Always immediately commit and push AI guideline file changes, including any referenced guidelines like `python.md` or SPR files if they were also updated or are relevant to the change.
   - Always keep the submodule AI guideline files up-to-date in addition to the top-level AI guideline files. The submodule AI guideline files only need updating if a top-level change directly impacts the submodule.

12. **Temporary Files & Scripts**:
   - Always use `/tmp` or `/var/tmp` or a project specific `tmp` folder for scratch and temporary files and scripts.
   - Project-specific `tmp` folders should be ignored for git (verify `.gitignore`).
