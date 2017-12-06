cmake_minimum_required(VERSION 3.9)

LIST(APPEND CMAKE_MODULE_PATH "${CMAKE_SOURCE_DIR}/../")
INCLUDE(pandocology)

add_document(
    TARGET pr9
    OUTPUT_FILE pr9.pdf
    SOURCES pr9.md
    RESOURCE_FILES pr9.bib ../subtitle.tex ../ieee.csl
    PANDOC_DIRECTIVES --filter       pandoc-citeproc
                      --bibliography pr9.bib
                      --csl          ieee.csl
                      -H             subtitle.tex
)
