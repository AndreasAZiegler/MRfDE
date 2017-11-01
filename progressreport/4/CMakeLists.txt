cmake_minimum_required(VERSION 3.9)

LIST(APPEND CMAKE_MODULE_PATH "${CMAKE_SOURCE_DIR}/../")
INCLUDE(pandocology)

add_document(
    TARGET pr4
    OUTPUT_FILE pr4.pdf
    SOURCES pr4.md
    RESOURCE_FILES pr4.bib ../subtitle.tex ../ieee.csl
    PANDOC_DIRECTIVES --filter       pandoc-citeproc
                      --bibliography pr4.bib
                      --csl          ieee.csl
                      -H             subtitle.tex
)
