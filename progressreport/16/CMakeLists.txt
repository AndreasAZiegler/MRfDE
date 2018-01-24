cmake_minimum_required(VERSION 3.9)

LIST(APPEND CMAKE_MODULE_PATH "${CMAKE_SOURCE_DIR}/../")
INCLUDE(pandocology)

add_document(
    TARGET pr16
    OUTPUT_FILE pr16.pdf
    SOURCES pr16.md
    RESOURCE_FILES pr16.bib ../subtitle.tex ../ieee.csl
    PANDOC_DIRECTIVES --filter       pandoc-citeproc
                      --bibliography pr16.bib
                      --csl          ieee.csl
                      -H             subtitle.tex
)
