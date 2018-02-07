cmake_minimum_required(VERSION 3.9)

LIST(APPEND CMAKE_MODULE_PATH "${CMAKE_SOURCE_DIR}/../")
INCLUDE(pandocology)

add_document(
    TARGET pr18
    OUTPUT_FILE pr18.pdf
    SOURCES pr18.md
    RESOURCE_FILES pr18.bib ../subtitle.tex ../ieee.csl
    PANDOC_DIRECTIVES --filter       pandoc-citeproc
                      --bibliography pr18.bib
                      --csl          ieee.csl
                      -H             subtitle.tex
)
