---
layout: post
title: "What Lisp Surprises Me"
date: 2023-12-10
author: "Jamin Chen"
header-img: "img/post-bg-universe.jpg"
tags: \["Computer Languages", "LISP"]
---

## S-expr and evaluation

A lisp program is a set of s-expressions. The basic of s-expressions are lists and atoms. An atom is a non-list or the empty list. Lists are delimited by parentheses and contain any number of whitespace-separated elements. Each element is itself an s-expression.

Given a bunch of text as input, the lisp reader (compiler) translates text into s-expressions that can be evaluated into Lisp forms. However, not every s-expression is valid to be evaluated into Lisp forms. Lisp evaluation introduces a second-level syntax to determines which s-expression can be treated as Lisp forms. The syntax rule is simple. Any atom or list that has a symbol as its first element is a legal Lisp form.

Atoms can be divided into two categories: symbols and everything else. A symbol, evaluated as a Lisp form, is considered the same of a variable and evaluated to the current value of the variable (*How do variables get their values?*). Certain symbols represents variables that can be evaluated into constant values or the symbols themselves. For example, symbol PI is evaluated to a constant float number. Symbol T and Nil, the canonical truth and falsity, are self-evaluating in the sense that
variables they name can be assigned the value of the symbol itself. Another class of self-evaluating symbols are keyword symbols (whose name starting with `:`). When the reader interns such a name, it automatically defines a constant variable with the name and with the symbol as the value.

Another large category of atoms being self-evaluating are numbers, strings, and numeric expression like ratio. When such an expression is passed to the notional evaluation function, it's simply returned.

All legal list forms start with a symbol, but three kinds of list forms are evaluated in different ways. They are function call forms, macro forms, and special forms.

## Function

Lisp function syntax supports various kinds of parameter-passing methods. These methods which are familiar in other languages are location indexed arguments, optional arguments, named arguments by keywords, and varying length arguments.

The first symbol of the list as Lisp forms is function name. The remaining elements of the list should be well-formed Lisp forms and evaluated one after another into values passed into the first element of function.

In Lisp, RETURN-FROM is not bound to function; it is tied to a code BLOCK. BLOCK is a special operator. When defining a function, DEFUN automatically initiates a new block with the same name of function. So we always return from a function by calling `(RETURN-FROM :funcname :values)`. Note that the function is changed the same time that RETURN-FROM's first argument should be changed as well.

The FUNCTION operator is used to get the function object from function name. The function name is not quoted. A syntax sugar is `#'`.

`lisp (foo 1 2 3) === (funcall #'foo 1 2 3) `

### Special forms

A group of operators defined in Common Lisp to do things that functions can not. For example, the flow control operator IF changes the order of remaining element evaluation orders in function call. Instead IF operator evaluates the first remaining element and performs encoded logic in IF operator of branch controlling. Other special operators are like QUOTE, which takes a single expression and simply returns it, unevaluated; and LET, which is used to create new variable bindings.

**Macro forms** A macro is a function that takes s-expressions as arguments and returns a Lisp form that’s then evaluated in place of the macro form. The macro expansion occurs at compile time when the macro input s-expressions don't need to be well-formed Lisp forms.

### Closure

Lexical scoping var is similar to scoped variables in other languages like Java and C. A common pattern of using lexical var is in *closure*. The key of understanding closure is that it is the binding, not the value of the variables, that's captured. Thus the closure can change and persist the value between calls of the closure.

## Variables

CL is a dynamically typed and strongly typed language in the sense that all type errors will be detected.

All values in CL are conceptually references to objects. Assigning a new value to variable changes what object the variable refers to but has no effect on the previously referenced object. All variable assignment is creating a new *binding* to the assigning object but has no effect on the previously bound object. This is the basic law of CL variable syntax.

Special operators LET and LET\* are usually used to bind variables.

Two types of variables: lexical scoping vars, and dynamic (global) vars.

### Dynamic variable

Operator DEFVAR and DEFPARAMETER are two ways to create dynamic or global variables. Global vars are conventionally with names that start and end with \*. DEFPARAMETER always assigns the initial value to the named variable while DEFVAR does so only if the variable is undefined. If you specifically want to reset a DEFVARed variable, you can either set it directly with SETF or make it unbound using MAKUNBOUND and then reevaluate the DEFVAR form.

Lexical and dynamic vars have different *scope* and *extent* in the sense that scope refers to space while extent refers to time. Lexical vars have lexical scope but indefinite extent. Dynamic vars have indefinite scope since they can be referred to from anywhere by dynamic extent.

LET operator can shadow dynamic var during the execution of the binding form, and recover the original binding to the dynamic var after finishing executing the lexical binding form.

### Constant

DEFCONSTANT, the var name can be used only to refer to the constant; it can't be rebound with any other binding form.

Redefinition of DEFCONSTANT is allowed, but this doesn't change the value.

Conventionally, using names as constant starting and ending with +.

### Assignment

Macro SETF is used to assign a new value to a binding. It can examine the form of the place it's assigning to and expand into appropriate lower-level operations to manipulate that place.

    (seft place form)

Assigning a new value to a binding has no effect on any other bindings of that variable. And it doesn’t have any effect on the value that was stored in the binding prior to the assignment.

## References

*   Forms and functions
    *   Symbols as Forms: http://www.lispworks.com/documentation/HyperSpec/Body/03\_abaa.htm
    *   Function Forms http://www.lispworks.com/documentation/HyperSpec/Body/03\_ababc.htm
*   Data structure
    *   Enhanced data structure and functions:  alexandria https://alexandria.common-lisp.dev/draft/alexandria.html
*   Sharpsign
    *   Syntax: https://mr.gy/ansi-common-lisp/Sharpsign.html
*   CLOS & MOP Spec
    *   https://clos-mop.hexstreamsoft.com/
