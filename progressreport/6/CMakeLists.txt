cmake_minimum_required(VERSION 3.9)

LIST(APPEND CMAKE_MODULE_PATH "${CMAKE_SOURCE_DIR}/../")
INCLUDE(pandocology)

add_document(
    TARGET pr6
    OUTPUT_FILE pr6.pdf
    SOURCES pr6.md
    RESOURCE_FILES pr6.bib ../subtitle.tex ../ieee.csl
    PANDOC_DIRECTIVES --filter       pandoc-citeproc
                      --bibliography pr6.bib
                      --csl          ieee.csl
                      -H             subtitle.tex
)
