cmake_minimum_required(VERSION 3.9)

LIST(APPEND CMAKE_MODULE_PATH "${CMAKE_SOURCE_DIR}/../")
INCLUDE(pandocology)

add_document(
    TARGET pr19
    OUTPUT_FILE pr19.pdf
    SOURCES pr19.md
    RESOURCE_FILES pr19.bib ../subtitle.tex ../ieee.csl
    PANDOC_DIRECTIVES --filter       pandoc-citeproc
                      --bibliography pr19.bib
                      --csl          ieee.csl
                      -H             subtitle.tex
)
