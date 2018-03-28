cmake_minimum_required(VERSION 3.9)

LIST(APPEND CMAKE_MODULE_PATH "${CMAKE_SOURCE_DIR}/../")
INCLUDE(pandocology)

set(pr_number "23")

add_document(
    TARGET pr${pr_number}
    OUTPUT_FILE pr${pr_number}.pdf
    SOURCES pr${pr_number}.md
    RESOURCE_FILES pr${pr_number}.bib ../subtitle.tex ../ieee.csl
    PANDOC_DIRECTIVES --filter       pandoc-citeproc
                      --bibliography pr${pr_number}.bib
                      --csl          ieee.csl
                      -H             subtitle.tex
)
