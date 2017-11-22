cmake_minimum_required(VERSION 3.9)

LIST(APPEND CMAKE_MODULE_PATH "${CMAKE_SOURCE_DIR}/../")
INCLUDE(pandocology)

add_document(
    TARGET pr7
    OUTPUT_FILE pr7.pdf
    SOURCES pr7.md
    RESOURCE_FILES pr7.bib ../subtitle.tex ../ieee.csl
    PANDOC_DIRECTIVES --filter       pandoc-citeproc
                      --bibliography pr7.bib
                      --csl          ieee.csl
                      -H             subtitle.tex
)
