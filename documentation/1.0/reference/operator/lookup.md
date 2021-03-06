---
layout: reference
title: '`[]` (lookup) operator'
tab: documentation
unique_id: docspage
author: Tom Bentley
milestone: Milestone 1
doc_root: ../../..
---

# #{page.title}

The *lookup* operator accesses a particular item in a `Correspondence`.

## Usage 

    void m(Integer[] seq) {
        Integer? first = seq[0];
    }

Note that first is `Integer?` rather than `Integer` because of the 
possibility that seq doesn't have a value for the given key.

## Description

The lookup operator gets an item from a 
`Correspondence` according to its key.

### Implementation Note

<!-- M3 -->
Setting an item in an `OpenCorrespondence` may be implemented in Milestone 2,
or possibly Milestone 3.

### Definition

The `[]` operator is defined as follows:

<!-- check:none -->
    lhs.item(index)

See the [language specification](#{page.doc_root}/#{site.urls.spec_relative}#listmap) for 
more details.

### Polymorphism

The `[]` operator is [polymorphic](#{page.doc_root}/reference/operator/operator-polymorphism). 
The meaning of `[]` depends on the 
[`Correspondence`](#{site.urls.apidoc_current}/interface_Correspondence.html) 
interface.

## See also

* [`?[]` (nullsafe lookup)](../nullsafe-lookup) operator used for accessesing 
  a `Correspondence?`
* API documentation for [`Correspondence`](#{site.urls.apidoc_current}/interface_Correspondence.html) 
* [sequence operators](#{page.doc_root}/#{site.urls.spec_relative}#listmap) in the 
  language specification
* [operator precedence](#{page.doc_root}/#{site.urls.spec_relative}#operatorprecedence) in the 
  language specification
* [Operator polymorphism](#{page.doc_root}/tour/language-module/#operator_polymorphism) 
  in the Tour of Ceylon

