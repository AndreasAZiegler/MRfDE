cmake_minimum_required(VERSION 3.9)

LIST(APPEND CMAKE_MODULE_PATH "${CMAKE_SOURCE_DIR}/../")
INCLUDE(pandocology)

add_document(
    TARGET pr10
    OUTPUT_FILE pr10.pdf
    SOURCES pr10.md
    RESOURCE_FILES pr10.bib ../subtitle.tex ../ieee.csl
    PANDOC_DIRECTIVES --filter       pandoc-citeproc
                      --bibliography pr10.bib
                      --csl          ieee.csl
                      -H             subtitle.tex
)
