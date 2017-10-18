cmake_minimum_required(VERSION 3.9)

LIST(APPEND CMAKE_MODULE_PATH "${CMAKE_SOURCE_DIR}/../")
INCLUDE(pandocology)

add_document(
    TARGET pr2
    OUTPUT_FILE pr2.pdf
    SOURCES pr2.md
    RESOURCE_FILES pr2.bib ../subtitle.tex ../ieee.csl
    PANDOC_DIRECTIVES --filter       pandoc-citeproc
                      --bibliography pr2.bib
                      --csl          ieee.csl
                      -H             subtitle.tex
)
