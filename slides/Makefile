# basic tools
LATEX	= xelatex
OPTS	= -shell-escape

# default target
TARGET = main

# sources
TEX_SRC	= $(TARGET).tex
FIG_SRC = $(wildcard fig/*)

# phony targets
.PHONY: all clean

# default target
all: $(TARGET).pdf

# build
$(TARGET).pdf: $(TEX_SRC) $(FIG_SRC)
	# standard boilerplate (2x latex)
	$(LATEX) $(OPTS) $(TEX_SRC)
	$(LATEX) $(OPTS) $(TEX_SRC)

	# cleanup
	$(RM) -r $(addprefix $(TARGET), .aux .bbl .blg .log .out .vrb .nav .snm .toc) _minted-$(TARGET)/ 

# clean
clean:
	$(RM) -r $(addprefix $(TARGET), .aux .bbl .blg .log .out .pdf .vrb .nav .snm .toc) _minted-$(TARGET)/ 
