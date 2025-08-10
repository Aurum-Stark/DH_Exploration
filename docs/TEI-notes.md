**Disclaimer:**  
- All the content in this file is based on material from the [TEI by Example](https://teibyexample.org) website.  
- It has been summarized into bullet points to aid quick reference and personal study.
  
**Note:**  
Some of the text in this document has been generated with the assistance of AI tools.

# 1. Introduction

- Computers process text using **character encoding**, which maps characters to binary codes that computers understand.
- **ASCII** (American Standard Code for Information Interchange) is a common character encoding based on the English alphabet.
- Character encoding enables storage and transmission of text but **does not convey the meaning or structure** of the text.
- To add meaning (meta-information) for computer processing, texts are marked up using **markup languages**, which insert tags into the text.
- The **Text Encoding Initiative (TEI)** is a standard for representing texts digitally through markup.
- TEI was developed by a community of scholars primarily in humanities, social sciences, and linguistics, organized as the **TEI Consortium (TEI-C)**.
- The TEI Consortium is a **non-profit organization** responsible for developing, maintaining, and promoting the TEI Guidelines.
- TEI Guidelines include both the markup language (tag set) and its documentation.
- TEI is based on **XML** and is flexible to adapt to different projects and text types.
- TEI is widely used by **libraries, museums, publishers, and scholars** for research, teaching, and preservation.
- This tutorial covers:
  - The basics of text encoding and markup languages in the humanities
  - TEI encoding principles
  - A brief history of the TEI Guidelines
  - An overview of the TEI Consortium’s organization

# 2. Text Encoding in the Humanities

- **Early computational humanities** (late 1940s onward) required systems to represent data in a form computers could process.
- Computers operate on **binary patterns**, not abstract entities like numbers or texts.
- Early input devices (e.g., punched cards) encoded characters as binary (1/0) based on position in a specific computer’s **character set**.
- Different computers had **different character sets**, so texts had to be transcribed into the specific set before processing.
- Limited character sets meant encoding all letters, punctuation, diacritics, and style changes required **complex “flag” systems**.
- Flags were also used for **textual analysis metadata** (word classes, morphology, syntax, lexicon).
- Each project created its **own encoding conventions**, tailored to its material and technology.
- Conventions were **project-specific** and dependent on available hardware, software, and storage media.
- **Drawback:** Encoded texts and tools were not easily reusable by other projects due to incompatible schemes and non-standard hardware.
- As machine-readable texts increased, **resource efficiency** became a concern.
- In 1967, **Martin Kay** proposed a **standard exchange code** so texts from any source could be read and locally adapted at input/output.

# 3. Markup Languages in the Humanities

## 3.1 Procedural vs. Descriptive Markup

- Humans interpret both *text content* and *meta-information* (e.g., italics as titles, foreign words, emphasis).
- Computers require explicit markup to distinguish and process meta-information.
- **Procedural markup**: tells applications how to present text (e.g., "print in italics").
- **Descriptive markup**: identifies the *meaning* or *role* of text elements (e.g., "this is a book title").
- Descriptive markup separates *content* from *meta-information* and maps logical elements directly to markup.

## 3.2 Early Attempts

- **COCOA encoding scheme** (1960s–70s) used as an input standard in:
  - Oxford Concordance Program (OCP, 1980s)
  - Textual Analysis Computing Tools (TACT, 1990s)
- **Beta-transcription/encoding**: standardized system for classical Greek text transcription.

## 3.3 SGML (Standard Generalized Markup Language)

- Published as ISO standard in 1986, developed by Charles Goldfarb.
- Designed for **reusability, interchange, independence, portability, collaboration**.
- Met seven key requirements: comprehensiveness, simplicity, processability, device independence, analytic system independence, editable form, and network interchange.
- Used ASCII exclusively for platform independence.
- SGML is a *metalanguage*—it defines rules for creating specific markup languages via **Document Type Definitions (DTDs)**.
- HTML is the most popular SGML DTD.
- Widely adopted in the humanities for descriptive encoding, but criticized for:
  - Hierarchical/tree-based text model limitations.
  - Verbose markup.

## 3.4 XML (eXtensible Markup Language)

- Published in 1998 as a W3C recommendation.
- Combines SGML’s strengths (descriptive markup, hierarchical modeling, extensibility, validation via DTD) with HTML’s simplicity and optional DTD usage.
- Technically a subset of SGML, developed by SGML experts (including TEI members).
- Became the preferred metalanguage for TEI descriptive text encoding.

# 4. XML: Ground Rules

## 4.1 Recommendation

- XML is a **metalanguage** for creating specialized markup languages.
- Platform-, software-, and system-independent; no single owner (specific XML languages can be owned).
- Facilitates **data integration, exchange, maintenance, and extraction**.
- **De facto standard** on the web—partly because HTML was rephrased as XML.
- Managed by the **W3C**, specification published as a recommendation in 1998.
- **Text-based**: built on ASCII, editable with any plain text editor (but XML editors are better for validation and error-checking).
- Non-ASCII characters handled via encoding systems like **ISO-8859-1** or **Unicode** (UTF-8, UTF-16).
- Non-ASCII characters are expressed via ASCII-based notation (e.g., à as `agrave` or `00E0`).

## 4.2 Components of XML

**Five main components:**

1. **Processing Instructions** – directives for applications.  
2. **Elements** – main content units (start/end tags).  
3. **Attributes** – additional data inside start tags (name-value pairs).  
4. **Entity References** – predefined strings or characters replaced before parsing.  
5. **(P)CDATA** – parsed or unparsed character data.

### 4.2.1 XML Declaration

- Appears at the top of the document (optional but must be first if used).  
- Declares XML version and character encoding.

### 4.2.2 Elements & Attributes

- Elements contain data; attributes store extra info.  
- Comments use `<!-- ... -->` and are ignored by parsers.

### 4.2.3 Entity References

- Allow representation of reserved characters (`<` as `&lt;`, `&` as `&amp;`).  
- Can represent Unicode characters (e.g., ø as `&#x00F8;` or `&#0248;`).  
- ENTITY declarations define reusable text ("boilerplate") inside a **DOCTYPE** declaration.  
- Useful for repeated content or standard phrases in legal/technical texts.

### 4.2.4 (P)CDATA

- **PCDATA**: parsed by the XML parser, allowing nesting.  
- **CDATA**: unparsed, useful for including code or text containing reserved characters without escaping.  
- CDATA section syntax: `<![CDATA[ ... ]]>`.


## 4.3 Using XML

- Basic authoring possible in plain text editors; professional XML editors add validation, transformation, and tree-structure viewing.  
- **Transformation tools**:  
  - **XSLT** (transform XML into other formats like HTML or PDF).  
  - **XSLFO** (formatting XML for output).  
- XML can be **indexed, queried, excerpted, and analyzed** with specialized tools.

# 5. TEI: Ground Rules

## 5.1 Guidelines

- TEI provides **guidelines** (rules & recommendations), not rigid standards, allowing scholars to encode texts according to their theories.
- TEI Guidelines serve as a **reference manual**, not just a tutorial.
- Mastering full TEI is complex, but most projects use a **subset called TEI Lite**, which includes ~140 elements.
- TEI Lite meets the needs of about 90% of TEI users most of the time.

## 5.2 TEI Modules

- TEI defines about **580 elements and 265 attributes**, organized into **21 modules**.
- Modules group related elements and attributes by function or text type. Some important modules include:

  - **tei (Infrastructure):** Common datatypes and modular classes.
  - **header:** Metadata and revision history for TEI documents.
  - **core:** Elements common to all TEI texts (paragraphs, lists, notes, quotations, editorial marks, etc.).
  - **textstructure:** Describes text divisions like front matter, body, back matter.
  - **gaiji:** For characters without standard Unicode representations.
  - **verse:** Specialized markup for poetic structures.
  - **drama:** Elements for dramatic texts including speeches, stage directions, multimedia.
  - **spoken:** For transcription of speech including pauses, gestures, vocal qualities.
  - **dictionaries:** Elements for dictionary entries and structures.
  - **msdescription:** Manuscript descriptions including physical and historical info.
  - **transcr:** Detailed transcription of primary sources.
  - **textcrit:** Critical apparatus for variant editions.
  - **namesdates:** Detailed markup of names, dates, people, places.
  - **figures:** Tables, formulas, images, music notation.
  - **corpus:** Encoding corpora of texts with metadata.
  - **linking:** Cross-reference and segmentation mechanisms.
  - **analysis:** Simple analytic and linguistic interpretations.
  - **iso-fs:** Complex analytical frameworks.
  - **nets:** Graphs and networks representations.
  - **certainty:** Attribution of certainty and responsibility in encoding.
  - **tagdocs:** Documentation of encoding schemes, element/attribute definitions.

- Each module is explained in a dedicated chapter of the TEI Guidelines.

## 5.3 Using TEI

- XML allows flexible parsing and easy electronic delivery (e.g., via web browsers), helping spread descriptive markup concepts.
- TEI texts must use the TEI namespace (`http://www.tei-c.org/ns/1.0`) and follow TEI text model rules.
- TEI schemas formalize these rules, expressed as DTD, XML Schema, or RELAX NG.
- **No single "TEI schema" exists:** users select modules and customize schemas as needed.
- TEI customizations are documented in **ODD files** ("One Document Does it all") that combine schema and human-readable documentation.
- The TEI offers a tool called **Roma** (https://roma.tei-c.org/) to create/edit ODD files and generate schemas and documentation.
- Validating TEI documents requires schemas including at least `tei`, `core`, `header`, and `textstructure` modules.
- Example of valid TEI documents must include `<teiHeader>` before `<text>`.
- Using elements from modules not included in the schema (e.g., `<orgName>` from `namesdates`) results in invalid documents.

# 6. Further Reading

For more information and the most up-to-date TEI Guidelines, visit the official website:  
https://tei-c.org/guidelines/
