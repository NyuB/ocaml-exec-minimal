.PHONY: default build fmt test test-promote

default: fmt test

# Build the executable then copy it under INSTALL_ROOT
install: fmt build test
	# Copy the executable into installation directory
	cp _build/install/default/bin/{{cookiecutter.main_name}} $(INSTALL_ROOT)/{{cookiecutter.main_name}}
	# Make the installed file writable to allow future deletion or replacement
	chmod +w $(INSTALL_ROOT)/{{cookiecutter.main_name}}

# An existing folder to place the main executable in
# If INSTALL_ROOT is in your PATH, so will be the installed executable
INSTALL_ROOT=~/bin

build:
	dune build

# Format sources, formatting can be configured in .ocamlformat
fmt:
	-dune fmt

test:
	dune test

# Update expected test results with whatever the current output is, run this once you are ok with the current behaviour
test-promote:
	dune test --auto-promote

# Prints this help message
help:
	@echo "======= USAGE ======="
	@echo "make <target> <variable>=<value>"
	@echo "--help"
	@echo "\t# show generic make documentation"
	@echo ""
	@awk '\
	/^##/{ print $$0; doc = 0; next }\
	/^#/{ if (doc != 1) { comments = $$0; doc = 1 } else { comments = comments "\n\t" $$0 } next }\
	/^([^=])+[=]/{ if (doc == 1) { print "(variable) " $$0 "\n\t" comments "\n"; doc = 0 } next }\
	/^([^:])+:/{ if (doc == 1) { print $$1 "\n\t" comments "\n"; doc = 0 } next }\
	/./{ doc = 0 }\
	' Makefile
	@echo "=====================\n"
