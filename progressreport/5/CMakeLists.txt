cmake_minimum_required(VERSION 3.9)

LIST(APPEND CMAKE_MODULE_PATH "${CMAKE_SOURCE_DIR}/../")
INCLUDE(pandocology)

add_document(
    TARGET pr5
    OUTPUT_FILE pr5.pdf
    SOURCES pr5.md
    RESOURCE_FILES pr5.bib ../subtitle.tex ../ieee.csl
    PANDOC_DIRECTIVES --filter       pandoc-citeproc
                      --bibliography pr5.bib
                      --csl          ieee.csl
                      -H             subtitle.tex
)
