cmake_minimum_required(VERSION 3.9)

LIST(APPEND CMAKE_MODULE_PATH "${CMAKE_SOURCE_DIR}/../")
INCLUDE(pandocology)

add_document(
    TARGET pr8
    OUTPUT_FILE pr8.pdf
    SOURCES pr8.md
    RESOURCE_FILES pr8.bib ../subtitle.tex ../ieee.csl
    PANDOC_DIRECTIVES --filter       pandoc-citeproc
                      --bibliography pr8.bib
                      --csl          ieee.csl
                      -H             subtitle.tex
)
