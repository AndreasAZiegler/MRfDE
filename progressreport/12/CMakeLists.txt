cmake_minimum_required(VERSION 3.9)

LIST(APPEND CMAKE_MODULE_PATH "${CMAKE_SOURCE_DIR}/../")
INCLUDE(pandocology)

add_document(
    TARGET pr12
    OUTPUT_FILE pr12.pdf
    SOURCES pr12.md
    RESOURCE_FILES pr12.bib ../subtitle.tex ../ieee.csl
    PANDOC_DIRECTIVES --filter       pandoc-citeproc
                      --bibliography pr12.bib
                      --csl          ieee.csl
                      -H             subtitle.tex
)
