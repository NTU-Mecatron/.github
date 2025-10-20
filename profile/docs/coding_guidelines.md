# Coding Guidelines

**Purpose**
Provide a compact, practical set of coding guidelines for contributors so code in this repository remains readable, consistent, and easy to maintain. These rules are intentionally pragmatic 

For coding guidelines for specific programming language, please refer: https://google.github.io/styleguide/
---

## Principles (keep these first in mind)

* **Consistency over preference.** Follow the existing style and conventions used in the package even if you prefer a different style.
* **Keep it simple.** Implement features in the simplest, most maintainable way that meets requirements. Avoid fancy techniques unless they clearly add value.
* **Iterate quickly.** Prototype and validate ideas early (throwaway prototypes are OK).
* **Communicate.** Discuss the plan with your lead or the person-in-charge before implementation.

---

## File and formatting conventions

* Follow the repository's existing conventions (indent style, file header, license block) before introducing anything new.
* Indentation: match existing code (tabs or spaces — don’t change global style in a single PR).
* Files: add a short file header only if the repository already uses one.

---

## Code style and readability

* Prefer clarity over cleverness.
* Use small helper functions to make intent explicit rather than long comments explaining complex code.
* Add comments to explain *why*, not *what*; write the *what* in clear code or a short docstring.
* Keep unit-testable design in mind (dependency injection where it makes sense).