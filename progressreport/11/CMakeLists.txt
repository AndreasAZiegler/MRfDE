cmake_minimum_required(VERSION 3.9)

LIST(APPEND CMAKE_MODULE_PATH "${CMAKE_SOURCE_DIR}/../")
INCLUDE(pandocology)

add_document(
    TARGET pr11
    OUTPUT_FILE pr11.pdf
    SOURCES pr11.md
    RESOURCE_FILES pr11.bib ../subtitle.tex ../ieee.csl
    PANDOC_DIRECTIVES --filter       pandoc-citeproc
                      --bibliography pr11.bib
                      --csl          ieee.csl
                      -H             subtitle.tex
)
