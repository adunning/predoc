# PreDoc
Guidelines for Editing Premodern Manuscripts

If the humanities are to continue flourishing in future years, we need to make it as easy to read a primary source as to watch an online video. Yet the digital texts available do not meet the basic needs of scholars, teachers, students, or the general public. This draft is aimed at identifying the problems we need to solve to fix this, and reaching a consensus on solutions.

## Assumptions

This repository will provide guidelines for applying [EpiDoc](http://epidoc.sourceforge.net) to editions of premodern (antique, medieval, renaissance) Western manuscripts, alongside the [Criteria for Reviewing Scholarly Digital Editions](http://ride.i-d-e.de/reviewers/catalogue-criteria-for-reviewing-scholarly-digital-editions/). It is based on the following assumptions:

1. Scholarship must be [technology-independent](http://neelsmith.github.io/dh101/checklist/) to be sustainable. The [Text Encoding Initiative](http://books.openedition.org/oep/690) (TEI) provides the most developed and stable translation of recent editing theory into a set of encoding guidelines, allowing the recording of complex details of manuscripts, and using these correctly will allow one to create a printed edition alongside an online text, providing appropriate levels of detail to different audiences.
2. Editions cannot be called scholarly unless they have a clear relationship to textual sources and indicate where editors have made emendations. In print, this was achieved through a critical apparatus, but this has never been satisfactory, leading to a lack of consensus as to how we can best enable users of editions to see how editors read a particular witness. Due to the difficulty of writing an apparatus in a consistent manner, it is proposed that [documentary editions](http://scholarlyediting.org/2014/essays/essay.pierazzo.html), recording varying levels of detail based on the research questions they need to answer, represent the most practical and verifiable means of gathering textual data.
3. Editions should bring readers as close to source material as possible without sacrificing readability, and take advantage of manuscript facsimiles whenever possible. Modern translations into the vernacular are the most effective means of making written works accessible to a broader audience, and should be provided wherever possible (sometimes in preference to a reader's edition of a text).

## Aligning editions with research questions

In an ideal world, we would have a library containing full facsimiles and transcriptions of every surviving manuscript, alongside every edition of them produced. This will not be possible before the day (perhaps a century or two from now) that we can teach machines to accurately read and analyse ancient handwriting; but even then, human judgements will never become obsolete.

New users of TEI will often hear that they should encode only the information relevant to their research questions; but editors seek above all to produce work useful to others, and this has not been closely defined for work on premodern texts. This repository proposes four encoding levels for guiding new editors and indicating the intended scope of editions to other researchers (cf. Pierazzo [2011](https://doi.org/10.1093/llc/fqr033)):

1. Transcriptions that provide the bare information necessary to read and search the text of the manuscript, and find significant variants (i.e. those of interest to classical philologists) in a collation with other witnesses. Markup may be light, and not necessarily reflecting the principles of TEI. This may represent computer-generated output from a collation table or the result of an OCRed text from a print edition (perhaps, one day, the result of applying OCR software directly to the manuscript). Spelling may be normalized.
2. Diplomatic editions that can be cited with precision and used to study minor variants between witnesses, and as well as patterns of spelling and punctuation. Scribal modifications to the manuscript should be indicated using the appropriate TEI tags (e.g. `<add>`, `<del>`), and any editorial modifications must be clearly stated (`<corr>`, etc.). The edition should encode the position of line breaks (this makes it much easier to verify one's work against the manuscript), and follow original spelling as far as abbreviations allow. It may be necessary to silently regularize word division to some extent. Punctuation and capitalization should be regularized only if necessary; if one wishes to capitalize proper names for a reader's version (until late in the Middle Ages, it was common to use capitals only for first letter of a sentence), it is easiest to accomplish this by marking the words with `<name>`, `<title>`, etc., which also allows the terms to be compiled in an index. Appropriate tags should be used for indicating quotation (e.g. `<quote>`, `<said>`, `<mentioned>`) rather than inserting quotation marks. Abbreviations may be silently expanded, though it may be helpful to record them in cases of ambiguity.
3. Information necessary to study the exact contemporary reading of the text and precise spelling, together with the scribe's linguistic profile: all of the above, mandating the preservation of the original punctuation, encoding editorial regularizations of hyphenation and word division, and documenting all expansions of abbreviations.
4. Information needed for statistical analysis of a scribe's graphic profile: the above in addition to full encoding of abbreviation markers and unusual letterforms relevant for palaeographical study (e.g. round and long 's').

Work imported from elsewhere would mostly fall into the first category, but these texts would still be of far more use than nothing at all. Indeed, the majority of texts found online at present are essentially documentary editions of printed texts, though many are highly inaccurate. Classicists who only wish to provide an overview of the textual tradition may continue to produce transcriptions that fall under this category.

New digital editions would probably fall into the second category, and would be necessary for accurate editions of texts whose witnesses are contemporary with their authors. This is the point at which the most broadly useful features of the manuscript are recorded before TEI markup starts to become too unwieldy to edit by hand.

The third and fourth categories are more specialized, but represent real and useful research questions, and with better software these levels would become more easily achievable. The idea of 'linguistic' and 'graphic' profiles was promoted by M.B. Parkes, ‘Latin autograph manuscripts: orthography and punctuation’, in *Gli autografi medievali: Problemi paleografici e filologici*, ed. Paolo Chiesa and Lucia Pinelli (Spoleto: Centro italiano di studi sull’alto Medioevo, 1994), 23–36. It is much easier to upgrade a transcription from one level to another than to start afresh, and over time, scholars could build up one another's work through all these stages based on the problems they need to solve.

## Problems facing editors

1. There is no publisher of open editions and translations of premodern texts apart from [Scholarly Editing](http://scholarlyediting.org) (which only covers shorter works). The resulting lack of working examples means that we have not yet formed clear expectations of what needs to be included in online editions.
2. Digital methods for creating an edition are poorly documented. These should cover the entire process, from obtaining manuscript images (and [navigating their legal status](https://doi.org/10.2139/ssrn.2573137)), to transcribing the selected source material, to providing appropriate citations, to rendering editions in a readable format.
3. The present revision of TEI is based on XML, and requires advanced validation mechanisms (RELAX NG, Schematron) that are poorly supported in common software; they are not supported in any cross-platform, open-source packages. Supporting efforts such as [bringing XML validation to the Atom text editor](https://atom.io/packages/linter-xmllint) and [including TEI support in Pandoc](https://github.com/jgm/pandoc/issues/2047) will significantly lower this barrier.
4. Editors have always felt free to base their work off that of their predecessors regardless of licensing concerns, but in the context of new concerns over intellectual property, we need to clarify the copyright status of editions. Many countries consider all scholarly editions to belong to their original authors, rather than their editors. The European Union provides a [special provision for editions](http://eur-lex.europa.eu/legal-content/EN/ALL/?uri=CELEX:32006L0116#d1e362-12-1) that protects them for a maximum of thirty years (see Margoni and Perry [2011](http://ssrn.com/abstract=1961535) for an explanation). The definition of 'critical and scientific publications' in this context is loosely defined: the German copyright act ([German](http://gesetze-im-internet.de/urhg/__70.html), [English](http://gesetze-im-internet.de/englisch_urhg/englisch_urhg.html#p0471)) implements it as only applying when they 'differ substantially from previously known editions of the works or texts' (article 70). In the United States, one cannot obtain copyright for an accurate representation of source material (cf. Bridgeman Art Library v. Corel; Meshwerks v. Toyota Motor Sales). While common wisdom in the digital field indicates that we should apply a Creative Commons licence to our work (either in its [Attribution](https://creativecommons.org/licences/by/4.0/) or [Attribution-ShareAlike](https://creativecommons.org/licences/by-sa/4.0/) forms), we are asserting through this action that we have copyright over our work, and it is not clear whether this is necessarily true. This does not make it any less a scholarly activity; scientific facts are not copyrightable, and this does not discourage us from seeking to understand them.

# Licence

The contents of this repository are provided under a [Creative Commons Attribution licence](https://creativecommons.org/licences/by/4.0/).
