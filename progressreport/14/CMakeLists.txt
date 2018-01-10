cmake_minimum_required(VERSION 3.9)

LIST(APPEND CMAKE_MODULE_PATH "${CMAKE_SOURCE_DIR}/../")
INCLUDE(pandocology)

add_document(
    TARGET pr14
    OUTPUT_FILE pr14.pdf
    SOURCES pr14.md
    RESOURCE_FILES pr14.bib ../subtitle.tex ../ieee.csl
    PANDOC_DIRECTIVES --filter       pandoc-citeproc
                      --bibliography pr14.bib
                      --csl          ieee.csl
                      -H             subtitle.tex
)
