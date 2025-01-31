# Gemini documentation

Gemini web pages, converted from html to asciidoc, and back again!

* [Services](services.html) 
* [Datasets](datasets.html)

The files below have been converted but have not been altered to work using the new workflow. Consequently internal links will go to the agi website and there may be other errors.
* [1037-uk-gemini-standard-and-inspire-implementing-rules](1037-uk-gemini-standard-and-inspire-implementing-rules.html)
* [1048-uk-gemini-encoding-guidance](1048-uk-gemini-encoding-guidance.html)
* [1049-metadata-guidelines-for-geospatial-data-resources-part-2](1049-metadata-guidelines-for-geospatial-data-resources-part-2.html)
* [1051-uk-gemini-v2-2-specification-for-discovery-metadata-for-geospatial-resources](1051-uk-gemini-v2-2-specification-for-discovery-metadata-for-geospatial-resources.html)
* [1052-metadata-guidelines-for-geospatial-data-resources-part-1](1052-metadata-guidelines-for-geospatial-data-resources-part-1.html)
* [1053-common-metadata-errors-uk-location-discovery-metadata-service](1053-common-metadata-errors-uk-location-discovery-metadata-service.html)
* [1054-operational-guide](1054-operational-guide.html)
* [1055-uk-gemini-major-changes-since-1-0](1055-uk-gemini-major-changes-since-1-0.html)
* [1056-glossary](1056-glossary.html)

## Services and Datasets workflow

* These files are generated from [include files](https://docs.asciidoctor.org/asciidoc/latest/directives/include/), one per element, in the [docs/partials](https://github.com/archaeogeek/gemini/tree/main/docs/partials) folder. 
* The xml snippets are in the docs/snippets folder.
* The naming convention for the element files is {element name in lower case without spaces}.asciidoc
* The naming convention for the xml snippets is {optional dataset or service prefix}-{element name in lower case without spaces}-{optional specific example}.xml

Where content differs between datasets and services, an [asciidoctor conditional pre-processor](https://docs.asciidoctor.org/asciidoc/latest/directives/ifdef-ifndef/) is used to determine which content to use, based on the command-line attribute `-a variant-dataset` or `-a variant-service`. 

To generate using the asciidoctor docker container, use the `-a` parameter, from the docs folder:

```
docker run --rm -v $(pwd):/documents/ asciidoctor/docker-asciidoctor asciidoctor -a variant-dataset *.adoc
```

Then repeat for services:

```
docker run --rm -v $(pwd):/documents/ asciidoctor/docker-asciidoctor asciidoctor -a variant-service *.adoc
```

## Styling

All files share a common attributes file, which indicates the basic attributes to be used when processing. This includes a linked reference to the asciidoc html stylesheet rather than the default embedding. Work has begun to integrate the styling from [Gemini.css](https://github.com/archaeogeek/gemini/blob/main/docs/Gemini.css) into [asciidoctor.css](https://github.com/archaeogeek/gemini/blob/main/docs/assets/asciidoctor.css) but this is far from complete.
