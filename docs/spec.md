# Google C++ style — throughline source

This document is **generated from the graph** by `tl docs`; `tl docs --check` gates it in CI. The prose headings are hand-owned — everything between `tl:*` markers is injected from the YAML items, so the published spec can never drift from the graph.

This source re-expresses the **Google C++ Style Guide** as a grounded IDD graph: each major section is a `user_requirement`, and every individual rule is a `system_requirement` that `implements` its section. The guide reference lives in `attrs.source_ref`; the throughline UIDs are this source's own and immutable — a consumer cites a rule as `cpp:SR-0001`, never by section name.

It carries
<!-- tl:count type == 'user_requirement' -->
9
<!-- tl:end --> sections and
<!-- tl:count type == 'system_requirement' -->
67
<!-- tl:end --> style rules.

## Purpose

<!-- tl:item INT-0001 -->
**INT-0001 — C++ is written in one consistent, safe, maintainable style** — `intent`, status `approved`

> The Google C++ Style Guide exists so that C++ across a large codebase reads as though written by one author: consistent header structure, scoping, class design, naming, commenting and formatting, biased towards the safe and predictable subset of a large and dangerous language, so that any engineer can read and change code they did not write and avoid the language's many footguns.

**source_ref**: Google C++ Style Guide
<!-- tl:end -->

## Header Files

<!-- tl:item UR-0001 -->
**UR-0001 — Header Files** — `user_requirement`, status `approved`

> Rules governing self-contained headers, include guards, what to include, forward declarations, inline definitions and the order of includes.

*Derives from:* INT-0001

**source_ref**: Google C++ Style Guide: Header Files
<!-- tl:end -->

<!-- tl:table type == 'system_requirement' and attrs.get('source_ref', '').startswith('Google C++ Style Guide: Header Files') -->
| UID | Type | Status | Title |
|---|---|---|---|
| SR-0001 | system_requirement | approved | Make every header self-contained |
| SR-0002 | system_requirement | approved | Guard every header against multiple inclusion |
| SR-0003 | system_requirement | approved | Include every header you directly use |
| SR-0004 | system_requirement | approved | Avoid forward declarations; include the header |
| SR-0005 | system_requirement | approved | Only define short functions inline in a header |
| SR-0006 | system_requirement | approved | Order and group includes consistently |
<!-- tl:end -->

## Scoping

<!-- tl:item UR-0002 -->
**UR-0002 — Scoping** — `user_requirement`, status `approved`

> Rules governing namespaces, internal linkage, nonmember functions, local variables and static, global and thread-local storage.

*Derives from:* INT-0001

**source_ref**: Google C++ Style Guide: Scoping
<!-- tl:end -->

<!-- tl:table type == 'system_requirement' and attrs.get('source_ref', '').startswith('Google C++ Style Guide: Scoping') -->
| UID | Type | Status | Title |
|---|---|---|---|
| SR-0007 | system_requirement | approved | Place code in a uniquely named namespace |
| SR-0008 | system_requirement | approved | Give .cc-only code internal linkage |
| SR-0009 | system_requirement | approved | Prefer nonmember functions in a namespace to static members |
| SR-0010 | system_requirement | approved | Declare each local variable in the narrowest scope |
| SR-0011 | system_requirement | approved | Forbid non-trivially-destructible static and global objects |
| SR-0012 | system_requirement | approved | Constant-initialise every thread_local at namespace or class scope |
<!-- tl:end -->

## Classes

<!-- tl:item UR-0003 -->
**UR-0003 — Classes** — `user_requirement`, status `approved`

> Rules governing constructors, implicit conversions, copy and move semantics, structs versus classes, inheritance, operator overloading, access control and declaration order.

*Derives from:* INT-0001

**source_ref**: Google C++ Style Guide: Classes
<!-- tl:end -->

<!-- tl:table type == 'system_requirement' and attrs.get('source_ref', '').startswith('Google C++ Style Guide: Classes') -->
| UID | Type | Status | Title |
|---|---|---|---|
| SR-0013 | system_requirement | approved | Do minimal, error-free work in constructors |
| SR-0014 | system_requirement | approved | Mark single-argument constructors and conversion operators explicit |
| SR-0015 | system_requirement | approved | Declare or delete copy and move operations deliberately |
| SR-0016 | system_requirement | approved | Use struct only for passive data carriers |
| SR-0017 | system_requirement | approved | Prefer a named struct to a pair or tuple |
| SR-0018 | system_requirement | approved | Make inheritance public and prefer composition |
| SR-0019 | system_requirement | approved | Overload operators only with obvious meaning |
| SR-0020 | system_requirement | approved | Keep all data members private |
| SR-0021 | system_requirement | approved | Order class declarations by kind and visibility |
<!-- tl:end -->

## Functions

<!-- tl:item UR-0004 -->
**UR-0004 — Functions** — `user_requirement`, status `approved`

> Rules governing inputs and outputs, function length, overloading, default arguments and trailing return types.

*Derives from:* INT-0001

**source_ref**: Google C++ Style Guide: Functions
<!-- tl:end -->

<!-- tl:table type == 'system_requirement' and attrs.get('source_ref', '').startswith('Google C++ Style Guide: Functions') -->
| UID | Type | Status | Title |
|---|---|---|---|
| SR-0022 | system_requirement | approved | Prefer return values to output parameters |
| SR-0023 | system_requirement | approved | Write short, focused functions |
| SR-0024 | system_requirement | approved | Overload only when the call is unambiguous to a reader |
| SR-0025 | system_requirement | approved | Restrict default arguments to non-virtual functions |
| SR-0026 | system_requirement | approved | Use a trailing return type only when it helps |
<!-- tl:end -->

## Ownership and Smart Pointers

<!-- tl:item UR-0005 -->
**UR-0005 — Ownership and Smart Pointers** — `user_requirement`, status `approved`

> Rules governing dynamic allocation, single ownership and the use of smart pointers.

*Derives from:* INT-0001

**source_ref**: Google C++ Style Guide: Ownership
<!-- tl:end -->

<!-- tl:table type == 'system_requirement' and attrs.get('source_ref', '').startswith('Google C++ Style Guide: Ownership') -->
| UID | Type | Status | Title |
|---|---|---|---|
| SR-0027 | system_requirement | approved | Give every dynamic object a single fixed owner |
| SR-0028 | system_requirement | approved | Transfer ownership with std::unique_ptr |
| SR-0029 | system_requirement | approved | Use std::shared_ptr only when sharing is truly needed |
<!-- tl:end -->

## Other C++ Features

<!-- tl:item UR-0006 -->
**UR-0006 — Other C++ Features** — `user_requirement`, status `approved`

> Rules governing rvalue references, exceptions, RTTI, casting, streams, const, constexpr, integer types, macros, nullptr, auto and lambdas.

*Derives from:* INT-0001

**source_ref**: Google C++ Style Guide: Other C++ Features
<!-- tl:end -->

<!-- tl:table type == 'system_requirement' and attrs.get('source_ref', '').startswith('Google C++ Style Guide: Other C++ Features') -->
| UID | Type | Status | Title |
|---|---|---|---|
| SR-0030 | system_requirement | approved | Restrict rvalue references to move and forwarding code |
| SR-0031 | system_requirement | approved | Do not use C++ exceptions |
| SR-0032 | system_requirement | approved | Specify noexcept only when it is accurate and useful |
| SR-0033 | system_requirement | approved | Avoid RTTI in production code |
| SR-0034 | system_requirement | approved | Use C++-style casts, never C-style casts |
| SR-0035 | system_requirement | approved | Use streams only for local human-readable output |
| SR-0036 | system_requirement | approved | Use const wherever it is meaningful |
| SR-0037 | system_requirement | approved | Use constexpr and constinit for compile-time values |
| SR-0038 | system_requirement | approved | Use sized integer types from <cstdint> |
| SR-0039 | system_requirement | approved | Avoid the preprocessor; prefer inline, const and constexpr |
| SR-0040 | system_requirement | approved | Use nullptr for pointers and '\0' for characters |
| SR-0041 | system_requirement | approved | Use auto only where it aids readability |
| SR-0042 | system_requirement | approved | Use lambda expressions judiciously with explicit captures |
<!-- tl:end -->

## Naming

<!-- tl:item UR-0007 -->
**UR-0007 — Naming** — `user_requirement`, status `approved`

> Rules governing the casing and choice of file, type, variable, constant, function, namespace, enumerator and macro names.

*Derives from:* INT-0001

**source_ref**: Google C++ Style Guide: Naming
<!-- tl:end -->

<!-- tl:table type == 'system_requirement' and attrs.get('source_ref', '').startswith('Google C++ Style Guide: Naming') -->
| UID | Type | Status | Title |
|---|---|---|---|
| SR-0043 | system_requirement | approved | Choose descriptive names over abbreviations |
| SR-0044 | system_requirement | approved | Name files in lowercase with underscores |
| SR-0045 | system_requirement | approved | Name types in UpperCamelCase |
| SR-0046 | system_requirement | approved | Name variables in snake_case with a trailing underscore on members |
| SR-0047 | system_requirement | approved | Name constants and enumerators with a leading k |
| SR-0048 | system_requirement | approved | Name functions in UpperCamelCase |
| SR-0049 | system_requirement | approved | Name namespaces in snake_case, avoiding generic names |
| SR-0050 | system_requirement | approved | Name macros in ALL_CAPS with a project prefix |
<!-- tl:end -->

## Comments

<!-- tl:item UR-0008 -->
**UR-0008 — Comments** — `user_requirement`, status `approved`

> Rules governing comment style, file, class, function and variable comments, implementation comments and TODOs.

*Derives from:* INT-0001

**source_ref**: Google C++ Style Guide: Comments
<!-- tl:end -->

<!-- tl:table type == 'system_requirement' and attrs.get('source_ref', '').startswith('Google C++ Style Guide: Comments') -->
| UID | Type | Status | Title |
|---|---|---|---|
| SR-0051 | system_requirement | approved | Use // comments, and /* */ only for blocks |
| SR-0052 | system_requirement | approved | Begin each file with a copyright and description comment |
| SR-0053 | system_requirement | approved | Comment each class's purpose and invariants |
| SR-0054 | system_requirement | approved | Comment what a function does, its parameters and side effects |
| SR-0055 | system_requirement | approved | Comment tricky or non-obvious variables |
| SR-0056 | system_requirement | approved | Explain why in implementation comments, not what |
| SR-0057 | system_requirement | approved | Mark unfinished work with a TODO and a reference |
<!-- tl:end -->

## Formatting

<!-- tl:item UR-0009 -->
**UR-0009 — Formatting** — `user_requirement`, status `approved`

> Rules governing line length, indentation, the layout of declarations, calls, conditionals, loops, pointers, classes and whitespace.

*Derives from:* INT-0001

**source_ref**: Google C++ Style Guide: Formatting
<!-- tl:end -->

<!-- tl:table type == 'system_requirement' and attrs.get('source_ref', '').startswith('Google C++ Style Guide: Formatting') -->
| UID | Type | Status | Title |
|---|---|---|---|
| SR-0058 | system_requirement | approved | Keep lines within eighty characters |
| SR-0059 | system_requirement | approved | Indent with two spaces and never tabs |
| SR-0060 | system_requirement | approved | Avoid non-ASCII characters in source |
| SR-0061 | system_requirement | approved | Attach the opening brace to conditionals, loops and switches |
| SR-0062 | system_requirement | approved | Attach * and & to the type in pointer and reference expressions |
| SR-0063 | system_requirement | approved | Place |
| SR-0064 | system_requirement | approved | Lay out a class by visibility with two-space indentation |
| SR-0065 | system_requirement | approved | Do not indent the contents of a namespace |
| SR-0066 | system_requirement | approved | Use single spaces around binary operators and after keywords |
| SR-0067 | system_requirement | approved | Separate logical sections with single blank lines |
<!-- tl:end -->

