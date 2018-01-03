cmake_minimum_required(VERSION 3.9)

LIST(APPEND CMAKE_MODULE_PATH "${CMAKE_SOURCE_DIR}/../")
INCLUDE(pandocology)

add_document(
    TARGET pr13
    OUTPUT_FILE pr13.pdf
    SOURCES pr13.md
    RESOURCE_FILES pr13.bib ../subtitle.tex ../ieee.csl
    PANDOC_DIRECTIVES --filter       pandoc-citeproc
                      --bibliography pr13.bib
                      --csl          ieee.csl
                      -H             subtitle.tex
)
