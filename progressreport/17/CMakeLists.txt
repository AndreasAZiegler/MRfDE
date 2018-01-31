cmake_minimum_required(VERSION 3.9)

LIST(APPEND CMAKE_MODULE_PATH "${CMAKE_SOURCE_DIR}/../")
INCLUDE(pandocology)

add_document(
    TARGET pr17
    OUTPUT_FILE pr17.pdf
    SOURCES pr17.md
    RESOURCE_FILES pr17.bib ../subtitle.tex ../ieee.csl
    PANDOC_DIRECTIVES --filter       pandoc-citeproc
                      --bibliography pr17.bib
                      --csl          ieee.csl
                      -H             subtitle.tex
)
