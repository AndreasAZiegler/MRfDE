cmake_minimum_required(VERSION 3.9)

LIST(APPEND CMAKE_MODULE_PATH "${CMAKE_SOURCE_DIR}/../")
INCLUDE(pandocology)

add_document(
    TARGET pr3
    OUTPUT_FILE pr3.pdf
    SOURCES pr3.md
    RESOURCE_FILES pr3.bib ../subtitle.tex ../ieee.csl
    PANDOC_DIRECTIVES --filter       pandoc-citeproc
                      --bibliography pr3.bib
                      --csl          ieee.csl
                      -H             subtitle.tex
)
