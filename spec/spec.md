---
layout: ballerina-no-git-inner-page
title: Ballerina Platform Specifications
intro: Read the Ballerina language spec and other specifications that cover the standard library, built-in language extensions, testing, documentation, and more.
keywords: ballerina, language specification, spec 
permalink: /spec/
redirect_from:
  - /learn/language-specification
  - /learn/language-specification/
---

As a platform designed to have multiple implementations, Ballerina semantics are defined by a series of specifications and not by the implementation. Currently, we have only one implementation (i.e., jBallerina, which compiles Ballerina to Java bytecodes). Others will follow, including a compiler which generates native binaries using LLVM.

The Ballerina platform is specified by a collection of specifications starting with the Ballerina Language Specification. Other specifications (which are yet to be moved to the specification repository or, in some cases, yet to be written) will cover the standard library, built-in language extensions such as security, immutability & deprecation, module and project management, testing, documentation, compiler extensions for cloud, and Ballerina Central.

All Ballerina specifications are maintained in the [ballerina-spec](https://github.com/ballerina-platform/ballerina-spec/) GitHub repository. Designing is also done via clearly-identified issues in this repository. Contributors are encouraged to participate via existing issues or by creating new issues.

## Specification versioning convention

From the start of 2019, Ballerina  specifications are versioned chronologically using the convention `20XYRn`, where `XY` is the 2-digit year (e.g., 19), `R` stands for "Release", and `n` is the release number for that year. Prior to 2019, a semver versioning scheme was used. However, that approach was abandoned when the language specification reached 0.980.

## Ballerina Language specifications and proposals

### Released specifications

The below are the most stable versions of the lanuguage specification, which are in sync with the Ballerina releases.

> **Note:** The `ChangeLog` section of the specification identifies the changes that have occurred in each version of the specification.

| Version | Release Date | Description | Link |
| ------- | ------------ | ----------- | ---- |
| 2020R1 | 2020-03-20 | First release of 2020. This is the basis for jBallerina 1.2.0. | <a target="_blank" href="/spec/lang/2020R1/">Read</a> |
| 2019R3 | 2019-09-07 | Stable release used as the basis for jBallerina 1.0.0 implementation. Mostly a cleanup from 2019R2 | <a target="_blank" href="/spec/lang/2019R3/">Read</a> |
| 2019R2 | 2019-07-01 | Major revised edition of the language | <a target="_blank" href="/spec/lang/2019R2/">Read</a> |
| 2019R1 | 2019-05-01 | First release with new versioning scheme with significant revisions | <a target="_blank" href="/spec/lang/2019R1/">Read</a> |

### Working drafts 

- For working draft language specifications of a Ballerina release, see the <a target="_blank" href="https://ballerina.io/spec/lang/draft/">draft language specification</a>.
- For the latest working draft language specification of a Ballerina release, see the <a target="_blank" href="https://ballerina.io/spec/lang/draft/latest/">latest draft language specification</a>.


### GitHub main

For a current repo snapshot of the language specification including all changes, see the <a target="_blank" href="https://ballerina.io/spec/lang/master/">main language specification</a>.


## Proposals for improvements/enhancements

For the proposals for improving Ballerina, see the <a target="_blank" href="https://github.com/ballerina-platform/ballerina-spec/blob/master/lang/proposals/README.md">work in progress proposals</a>.

<style> 
table {
    width:100%;
}
td {
    padding: 20px; 
}
li.cVersionItem  {display: none !important;}
</style>
