cmake_minimum_required(VERSION 3.9)

LIST(APPEND CMAKE_MODULE_PATH "${CMAKE_SOURCE_DIR}/../")
INCLUDE(pandocology)

add_document(
    TARGET pr15
    OUTPUT_FILE pr15.pdf
    SOURCES pr15.md
    RESOURCE_FILES pr15.bib ../subtitle.tex ../ieee.csl
    PANDOC_DIRECTIVES --filter       pandoc-citeproc
                      --bibliography pr15.bib
                      --csl          ieee.csl
                      -H             subtitle.tex
)
