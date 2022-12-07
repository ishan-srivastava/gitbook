---
coverY: 0
---

# 🍠 Widgets

A widget is an actual entity that produces a **visible output on the webpage**. UI Component represents this interface. It ensures there is a type property that defines what kind of component it is, helping the rendering logic to decide what to load.

Every widget has the freedom to define its own specialised properties which hold some meaning within its own context or some property that can be configured for dynamic rendering rather than hardcoding it in UI.

Currently, these widgets are tightly coupled with **Navi's frontend UI library** which strictly follows our own design systems and patterns

We see widgets as two types-

* **Individual widgets** - These are individual independent widgets that are used to render a specific visual item in UI. Example - `Button`, `Typography`, `Icons`
* **Composite widgets** - Composite widgets are those that house Individual Components in their structure to have a meaning. Example - `Form`, `Table`\
  ``\
  ``For eg `FormComponent` is referred to as a composite type since a form will always be composed of some kind of input or selection components. Configuration of this component is written in such a way that components included within a form can be configured like an individual component as well as on a composite level such as warnings, data model, validation errors as well as selection data (we call it the pincer move  ).
