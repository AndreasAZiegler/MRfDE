cmake_minimum_required(VERSION 3.9)

LIST(APPEND CMAKE_MODULE_PATH "${CMAKE_SOURCE_DIR}/../")
INCLUDE(pandocology)

add_document(
    TARGET pr22
    OUTPUT_FILE pr22.pdf
    SOURCES pr22.md
    RESOURCE_FILES pr22.bib ../subtitle.tex ../ieee.csl
    PANDOC_DIRECTIVES --filter       pandoc-citeproc
                      --bibliography pr22.bib
                      --csl          ieee.csl
                      -H             subtitle.tex
)
